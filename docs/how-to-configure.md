- Add the defaults
- Add the overrides for the defaults
- Add the scopes override required
- Add the mapping to the feild required
- Add a section about add certs to the jenkins ca that will required for authentication with the on-prem service
- Add a section about integration with Hashicorp vault and external-secrets

# Configuration Keycloak

- Keycloak specific configuration for this plugin can be tedious and PITA, considering different teams are  managing keycloak and jenkins
- Below is the basic configuration which works

## keycloak setup
- setup OIDC client
- you will need to pass the user profile along with emailID and open_id profile for it to work smoothly.
- If your keycloak is signed with Org specific certs, then you will have to add your own certs to the jenkins CA certs.

 -- docs on how to do that. 

 - Although automcation works fine, you still need to do some bits to get this working

 - you need to override the scope to email, open_id in the plugin configuration  

 - Also you will be required to pass the below values of below in order for the correct mapping of user data to the auth and for things to work properly

 -  emailFieldName
 - fullNameFieldName: "fullName" 
 - groupsFieldName: "groups"
- userNameField: "preferred_username"
