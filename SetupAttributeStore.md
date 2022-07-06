# Setup sample attribute store

1. [Create a new attribute set](https://docs.microsoft.com/en-us/graph/api/directory-post-attributesets?view=graph-rest-beta&tabs=http#examples)
    * Change the action in Graph Explorer to POST
    * Change the endpoint to beta
    * Change the URL to https://graph.microsoft.com/beta/directory/attributeSets
    * Request Body : { "id": "DEMO", "description": "Demo Attribute set" } 

![Graph Explorer create new attribute set](/new-attributeset.png)

2. Create new attribute definitions
    * Change the URL to https://graph.microsoft.com/beta/directory/customSecurityAttributeDefinitions
    * Request Body : { "attributeSet":"DEMO", "description":"Citizenship", "isCollection":false, "isSearchable":true, "name":"Citizenship", "status":"Available", "type":"String", "usePreDefinedValuesOnly": false }
    * Request Body : { "attributeSet": "DEMO", "description": "Has the user successfully privacy training", "isCollection": false, "isSearchable": true, "name": "PrivacyTraining", "status": "Available", "type": "Boolean", "usePreDefinedValuesOnly": false }
    * Request Body : { "attributeSet": "DEMO", "description": "Active projects for user", "isCollection": true, "isSearchable": true, "name": "Project", "status": "Available", "type": "String", "usePreDefinedValuesOnly": true, "allowedValues": [ {  "id": "Alpine", "isActive": true }, { "id": "Baker", "isActive": true }, { "id": "Cascade", "isActive": true } ] }