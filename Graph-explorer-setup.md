# Graph explorer setup

Follow these steps to configure an Azure AD user with the proper permissions to manage custom security attributes in Azure AD and configure the attribute catalog using Graph Explorer.

1. Make sure that the Azure AD User that you are using has 
    * [Attribute Definition Administrator](https://docs.microsoft.com/en-us/azure/active-directory/roles/permissions-reference#attribute-definition-administrator) role if you are going to configure the attribute catalog. 
    * [Attribute Assignment Administrator](https://docs.microsoft.com/en-us/azure/active-directory/roles/permissions-reference#attribute-assignment-administrator) if you are going to assign attribute values to users. 
    * You can confirm that this is working by opening the [Custom Security Attributes](https://portal.azure.com/#view/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/~/CustomAttributesCatalog) pane in Azure Active Directory. If the options are greyed out of the blade does not load, you do not have proper permissions setup. In this example, there is an existing attribute set visible. ![Custom Security Attributes in Azure portal](/attrbutesets-portal.png)

2. Go to [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer), sign in as the user that was setup and confirmed in step 1.
    * Click on your user icon and choose Consent to Permissions. Search for "attributedef" to find CustomSecAttributeDefinition and consent. ![CustomSecAttributeDefinition permissions consent](/graphConsent.png)
    * The Azure AD tenant admin must explicitly grant consent for the requested permissions to the Graph Explorer application. [Authorization and the Microsoft Graph Security API](https://docs.microsoft.com/en-us/graph/security-authorization)
    * The user must be a member of the Security Reader Limited Admin role in Azure AD (either Security Reader or Security Administrator).

3. Now you should be setup to run your first query. 
    * Change the endpoint dropdown to beta
    * Change the url to https://graph.microsoft.com/beta/directory/attributeSets
    * Press Run query

You should get a 200 response if you have consented to permissions correctly. In this case, we see the demo attribute set from the portal in step 1. ![Graph Explorer Attribute Sets query](/attributeSets-query.png)

If you didn't consent to permissions first, you might see this ![Attribute Set query denied](/attributeSets-query-denied.png)
