# MAT Studio Data Models

## Components

```javascript
{
   "name": "button",
   "html": "<button class='uk-button uk-button-default uk-button-small'></button>"
}
```

## Orchestration Atoms

#### Karvy Push

```javascript
{
    "initEvent": "blueBtnClicked", // String
    "process": {
        "processName": "pushToKarvy",
        "mapping": {
            "input": [{
                "key1": {
                    "thingId": "1", // Int
                    "traitNumber": "1" // Int
                }
            }],
            "output": [{
                "key1": {
                    "thingId": "1", // Int
                    "traitNumber": "1" // Int
                }
            }]
        }
    },
    "exitEvent": {
        "success": "blueClickEventProcessed", // String (255)
        "failure": "blueBtnClickedFailed", // String (255)
    }
}
```

## User

```javascript
{
   "username": "",
   "password": "",
   "access": [{
       "org": "",
       "apps": [{
           "appID": "",
           "grant": ""
       }]
   }],
}
```

## Pages

```javascript
{
   "pageName": "",
   "description": "",
   "elements": [{
       "element_id": "nav",
       "element_parent": "0",
       "element_tag": "nav",
       "inner_html": "",
       "class": "uk-navbar-container",
       "style": {
           "box-shadow": "0px 2px 11px #888888",
           "padding": "5px",
           "margin-bottom": "50px",
           "background": "#FFF"
       },
       "interaction":{
           "interactionType": "click",
           "orchEmission":"blueBtnClicked"
       }
   }]
}
```

## Templates

```javascript
[
    {
        "templateName": "aadhaar",
        "templateDescription": "",
        "things": [
            {
                "thingName": "",
                "thingDescription": ""
            }
        ],
        "traits": [
            {
                "thingName": [
                    {
                        "traitName": "",
                        "isIndexed": "",
                        "triatNumber": ""
                    }
                ]
            }
        ],
        "orchAtoms": [
            {
                "initEvent": "blueBtnClicked", // String
                "process": {
                    "processName": "pushToKarvy",
                    "mapping": {
                        "input": [
                            {
                                "key1": {
                                    "thingId": "1", // Int
                                    "traitNumber": "1" // Int
                                }
                            }
                        ],
                        "output": [
                            {
                                "key1": {
                                    "thingId": "1", // Int
                                    "traitNumber": "1" // Int
                                }
                            }
                        ]
                    }
                },
                "exitEvent": {
                    "success": "blueClickEventProcessed", // String (255)
                    "failure": "blueBtnClickedFailed", // String (255)
                }
            }
        ],
        "uiConfig": [
            {
                "element_id": "nav",
                "element_parent": "0",
                "element_tag": "nav",
                "inner_html": "",
                "class": "uk-navbar-container",
                "style": {
                    "box-shadow": "0px 2px 11px #888888",
                    "padding": "5px",
                    "margin-bottom": "50px",
                    "background": "#FFF"
                },
                "interaction": {
                    "interactionType": "click",
                    "orchEmission": "blueBtnClicked"
                }
            }
        ]
    }
]
```

