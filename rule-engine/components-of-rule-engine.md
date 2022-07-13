# Components of Rule Engine

A rule engine consists primarily of **Conditions** and **Rules**. Conditions are defined and weaved together using rules, which ultimately define the navigation to be followed across pages.

### Conditions

1. Conditions are basically the parameters/ constraints that will drive the navigation.
2. Condition lays the foundation to define rules.
3.  Conditions can be either:

    **a). API Based         :** Implies definition of variables which are linked to a certain API and tied with operators. Aids inputting various types of checks as well in place.\
    **b). Logical Based :** Implies definition using various variables available in pages tied with       logical operators. It also enables the performing of logical comparisons/computations as well.\
    **c). No Conditions :**&#x20;



![Condition Type: API based condition](https://lh6.googleusercontent.com/HEPFOt-PlSVbsG8BJkAI903Dgj\_oONUBJYmVZLzjTnxRIT6El0RtQlpq6jqjiWIhhDHpOG248l5pRGq1h9w0G-BSeVADPRGhGai2RdDRXzVybe-ahLm7GPDCacfJwXAvbtTF9mHoO7zqwgwaEQ)

![Condition Type: Logical Condition](https://lh3.googleusercontent.com/FQ2-EpcUy3LNjk4jnEA-lx9Hvoh9x3FGoYDmCUpsE3PaZpFOZBKbDubhMN8AG0xXXUm\_Wc41q0WWi4wRONyZ-9vQBIHkFB5TEi6dKdteHUSVEeYh6q9BMLP1ZRh6rbzJ9Q6mDv1I0iN1PA3ygQ)

### Rules&#x20;

1. There are various types of logic operators that can weave various conditions together to form different types of navigation.&#x20;
2. A rule is the result of the assignment of conditions that results in a defined type of navigation.&#x20;
3. (TRUE/FALSE/UNCERTAIN) The ultimate driver of navigation is determined by the output of the conditions associated with the rule.&#x20;
4. As an example, if "condition 1" is TRUE then go to PAGE 2, if it's FALSE then go to PAGE 3.

![Adding Rules](../.gitbook/assets/Rule.gif)
