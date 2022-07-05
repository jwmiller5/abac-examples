# Setup sample attribute store

1. [Create a new attribute set](https://docs.microsoft.com/en-us/graph/api/directory-post-attributesets?view=graph-rest-beta&tabs=http#examples)
    * Change the action in Graph Explorer to POST
    * Change the endpoint to beta
    * Change the URL to https://graph.microsoft.com/beta/directory/attributeSets
    * Request Body : { "id": "BMTN", "description": "Initial Attributes for Hackathon" } 

![Graph Explorer create new attribute set](/new-attributeset.png)

2. Create new attribute definitions
    * Change the URL to https://graph.microsoft.com/beta/directory/customSecurityAttributeDefinitions
    * Request Body : { "attributeSet":"BMTN", "description":"Citizenship", "isCollection":false, "isSearchable":true, "name":"Citizenship", "status":"Available", "type":"String", "usePreDefinedValuesOnly": false }
    * Request Body : { "attributeSet": "BMTN", "description": "Clearance", "isCollection": false, "isSearchable": true, "name": "Clearance", "status":  "Available", "type": "String", "usePreDefinedValuesOnly": false }
    * Request Body : { "attributeSet": "BMTN", "description": "Has the user received BEAST briefing", "isCollection": false, "isSearchable": true, "name": "BeastBriefed", "status": "Available", "type": "Boolean", "usePreDefinedValuesOnly": false }

