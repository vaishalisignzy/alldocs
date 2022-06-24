# Concepts

Every Decision made by the system is done through two structures -- Check & CheckBox. As you'll see, this has been done to make the system as extensible as possible.

### Check

A model which stores the `operation` required to be done on the data provided by the associated CheckBox. It processes the data and accordingly assigns the results. 1 Check can be associated with only 1 CheckBox.

A Check accepts data from the CheckBox, processes it, and stores the result in the Merchants data so that it can be used in other Checks if required.

A Check is highly configurable in terms of what processing should be done on the data it receives from a CheckBox. Currently, supported operations are `boolean`, `checkpoints`, and `truthtable`. A Boolean operation can be used to compare any two variables of type `api`, `check`, `hardcoded`, and `pageVariable`. A CheckPoints operation can be used to specify a custom result for a floating point number (eg. 0.5) depending on its closeness to 1.0. A TruthTable operation can be used to generate Decisions, as described in `Decision` section below, and in the `Inserting Checks into Decision Engine` document.

A Check's structure differs depending on which operation it is configured for.

#### Common Structure

```
Check:
    Name: // Name of the check
    CheckBoxId: // Associated CheckBox
    PageId: // Where to store the result
    Level: // The Level of this Check (explained below)
    Tags: {
        "passed": "Safe",
        "failed": "Unsafe",
        "error": "Uncertain"
    } // Custom tags to summarise the result of this check
    Disabled: // Dictates if the Check should be run
    
    // Operation differs based on type of Check
    // For Score type Checks
    Operation: CheckPoints,
    Fact: [ ApiOutputParameter ],
    CheckPoints: {
        "0.2": "customAssignedTag1",
        "0.5": "customAssignedTag2",
        "0.8": "customAssignedTag3",
        "1.0": "customAssignedTag4"
    } // Fact will be a floating point number, and will be evaluated against this
    
    // For General
    Operation: Boolean,
    Fact: [ PageId, PageVariable ],
    Value: "hardcodedString" or [ PageId, PageVariable ],
    Boolean: "greaterThan", // Fact Boolean Value (eg. PanDOB greaterThan 14/04/2000)
    
    // For Decisions
    Operation: TruthTable,
    Fact: [[ CheckId1 ], [ CheckId2 ], [ CheckId3 ]],
    TruthTable: {
        [ CheckId1 ]: {
            [ CheckId2 ]: "customAssignedTag"
        }
    }
```

### CheckBox

A model which stores the data sources required for the check, what Checks to run, and what page a Check's result should be tagged to. The CheckBox's role is to fetch data from stored data sources, and forward that data to Checks. Has a 1:many mapping to Checks.

Currently, a CheckBox can source data from three places - Signzy's APIs, Merchant Data, and results of Checks of levels lower than this CheckBox.

#### Structure

```
CheckBox:
    // These properties together form a unique key for CheckBox
    // There can be one CheckBox for one level of one combination of widgets of one page of one flow
    FlowId:
    PageId:
    Level:
    WidgetNames:
    // For getting Data
    DataSource: {
        // Singular API allowed per CheckBox
        "api": [
            {
                "apiId": "",
                "type": "",
                "mapping": "",
                "outputParams": ""
            }
        ]
        // Get as many page variables as required
        "pageVariables": {
            PageId: VariableName,
            ...
        }
        // Get as many check results (of a lower level) as required
        "checks": [ CheckId, CheckId, ... ],
        "hardcoded": ""
    } // This has been designed keeping extensibility in mind
    // Data collected from DataSource fed here
    Checks: [
        CheckId,
        ...
    ]
```

### Level

A Check of level $$n$$ will be run after all Checks for level $$n-1$$ are run. It can be imagined as a reverse priority. All Checks of level $$n$$ will have access to the results of checks of level $$n - 1$$ and below.

### Decision

A Decision is a type of Check the result of which is highly configurable. While configuring it, a truth table is generated with results

| CheckId1  | CheckId2 | CheckId3  | Result |
| --------- | -------- | --------- | ------ |
| Safe      | Unsafe   | Uncertain | Safe   |
| Safe      | Safe     | Unsafe    | Safe   |
| Uncertain | Safe     | Safe      | Safe   |

Row 1 of this table means that the result of Decision will be `Safe` if the value of CheckId1's result is `Safe`, the value of CheckId2's result is `Unsafe`, and the value of CheckId3's result is `Uncertain`.
