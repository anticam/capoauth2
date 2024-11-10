# Getting Started

Welcome to your new project.

It contains these folders and files, following our recommended project layout:

File or Folder | Purpose
---------|----------
`app/` | content for UI frontends goes here
`db/` | your domain models and data go here
`srv/` | your service models and code go here
`package.json` | project metadata and configuration
`readme.md` | this getting started guide


## Next Steps

- Open a new terminal and run `cds watch`
- (in VS Code simply choose _**Terminal** > Run Task > cds watch_)
- Start adding content, for example, a [db/schema.cds](db/schema.cds).


## Learn More

Learn more at https://cap.cloud.sap/docs/get-started/.

### Steps

login to CF space

```shell

cf login -a https://api.cf.us10-001.hana.ondemand.com --sso
```

create and show service key

```shell

cf create-service-key capoauth2-auth capoauth2-auth-sk
cf service-key capoauth2-auth capoauth2-auth-sk


{
  "credentials": {
    "apiurl": "https://api.authentication.us10.hana.ondemand.com",
    "clientid": "sb-capoauth2-c73260a3trial-dev!t342080",
    "clientsecret": "PkE0nnnnnnnnnnnnnnnnnnnR5c=",
    "credential-type": "instance-secret",
    "identityzone": "c73260a3trial",
    "identityzoneid": "32c86c6c-nnnn-nnnn-nnnn-4bc0fcc55b1a",
    "sburl": "https://internal-xsuaa.authentication.us10.hana.ondemand.com",
    "serviceInstanceId": "32c86c6c-nnnn-nnnn-nnnn-4bc0fcc55b1a",
    "subaccountid": "32c86c6c-nnnn-nnnn-nnnn-4bc0fcc55b1a",
    "tenantid": "32c86c6c-nnnn-nnnn-nnnn-4bc0fcc55b1a",
    "tenantmode": "dedicated",
    "uaadomain": "authentication.us10.hana.ondemand.com",
    "url": "https://c73260a3trial.authentication.us10.hana.ondemand.com",
    "verificationkey": "-----BEGIN PUBLIC KEY-----\nMIIBIjANB...VcQ+WQiZc\nKQIDAQAB\n-----END PUBLIC KEY-----",
    "xsappname": "capoauth2-c73260a3trial-dev!t342080",
    "zoneid": "32c86c6c-nnnn-nnnn-nnnn-4bc0fcc55b1a"
  }
}
```

in .env file store the clientid, clientsecret, url and application URL:

```shell

clientid=sb-capoauth2-c73260a3trial-dev!t342080
clientsecret=PkE0nnnnnnnnnnnnnnnnnnnR5c=
authurl=https://c73260a3trial.authentication.us10.hana.ondemand.com
srvurl=https://c73260a3trial-dev-capoauth2-srv.cfapps.us10-001.hana.ondemand.com

```

login to BTP

```shell

btp login --sso
```

list security details:

```shell

❯ btp get security/app cf-application!t342080 --subaccount 32c86c6c-nnnn-nnnn-nnnn-nnnnnnn55b1a
appid: cf-application!t342080
xsappname: cf-application
planName: application
description: <null>
orgId: <null>
spaceId: <null>
userName: <null>
planId: ThGdx5loQ6XhvcdY6dLlEXcTgQD7641pDKXJfzwYGLg=
serviceinstanceid: dc892363-b5a1-nnnn-nnnn-nnnnnnnn804f
masterAppId: <null>
tenant-mode: <null>
scopes:
  - description: Change grant type Excercise - Scope 1
    name: cf-application!t342080.Excercise_User_Scope_1
  - description: Change grant type Excercise - Scope 1
    name: cf-application!t342080.Excercise_System_Scope_1
foreign-scope-references: <null>
authorities:
  - cf-application!t342080.Excercise_System_Scope_1
attributes:

role-templates: <null>
capability-types: <null>
instance-authorization: <null>
oauth2-configuration: <null>

OK
```

### References

[Blog - How to call protected app with scope](https://community.sap.com/t5/technology-blogs-by-sap/how-to-call-protected-app-from-external-app-as-external-user-with-scope/ba-p/13440813)

[bookhsop-demo](https://github.com/gregorwolf/bookshop-demo#allow-api-access)  

[xs-security-json](https://help.sap.com/docs/btp/sap-business-technology-platform/application-security-descriptor-configuration-syntax)  

- Granting Scopes to Another Application  
- authorities  
- oauth2-configuration  
