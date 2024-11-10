# Getting Started

Welcome to your new project.

It contains these folders and files, following our recommended project layout:

File or Folder | Purpose
---------|----------
`app/` | content for UI frontend goes here
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

create and show service key for the xsuaa service instance:

```shell

cf create-service-key capoauth2-auth capoauth2-auth-sk
cf service-key capoauth2-auth capoauth2-auth-sk


{
  "credentials": {
    "apiurl": "https://api.authentication.us10.hana.ondemand.com",
    "clientid": "sb-capoaunnnnnnnnnnnntrial-dev!t342080",
    "clientsecret": "PkE0nnnnnnnnnnnnnnnnnnnR5c=",
    "credential-type": "instance-secret",
    "identityzone": "c7326nnnnnnnn",
    "identityzoneid": "32c86c6c-nnnn-nnnn-nnnn-4bc0fcc55b1a",
    "sburl": "https://internal-xsuaa.authentication.us10.hana.ondemand.com",
    "serviceInstanceId": "32c86c6c-nnnn-nnnn-nnnn-4bc0fcc55b1a",
    "subaccountid": "32c86c6c-nnnn-nnnn-nnnn-4bc0fcc55b1a",
    "tenantid": "32c86c6c-nnnn-nnnn-nnnn-4bc0fcc55b1a",
    "tenantmode": "dedicated",
    "uaadomain": "authentication.us10.hana.ondemand.com",
    "url": "https://c7326nnnnnnnn.authentication.us10.hana.ondemand.com",
    "verificationkey": "-----BEGIN PUBLIC KEY-----\nMIIBIjANB...VcQ+WQiZc\nKQIDAQAB\n-----END PUBLIC KEY-----",
    "xsappname": "capoauth2-cnnnnnnnnnnnnnnnnn!t342080",
    "zoneid": "32c86c6c-nnnn-nnnn-nnnn-4bc0fcc55b1a"
  }
}
```

in .env file store the clientid, clientsecret, url and application URL:

```shell

clientid=sb-capoauth2-c73260a3trial-dev!t342080
clientsecret=PkE0nnnnnnnnnnnnnnnnnnnR5c=
authurl=https://c7326nnnnnnnn.authentication.us10.hana.ondemand.com
srvurl=https://c7326nnnnnnnn-dev-nnnnnnnnn-srv.cfapps.us10-001.hana.ondemand.com

```

from test.http run `Get Access Token` then `Read metadata` scripts.

login to BTP

```shell

btp login --sso
```

list security details:

```shell

❯ btp get security/app capoauth2-c73260a3trial-dev!t342080 --subaccount 32c86c6c-xxxx-xxxx-xxxx-4bc0fcc55b1a
appid: capoauth2-c73260a3trial-dev!t342080
xsappname: capoauth2-c73260a3trial-dev
planName: application
description: <null>
orgId: <null>
spaceId: <null>
userName: <null>
planId: ThGdx5lxxxxxxxxxxxxxxxxxQD7641pDKXJfzwYGLg=
serviceinstanceid: 3eadc2a6-xxxx-xxxx-xxxx-fcfb7589462c
masterAppId: <null>
tenant-mode: <null>
scopes:
  - description: admin
    name: capoauth2-c73260a3trial-dev!t342080.admin
foreign-scope-references: <null>
authorities:
  - capoauth2-c73260a3trial-dev!t342080.admin
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

Blog 2022 - [How grant-types keep your application secure - lab setup](https://community.sap.com/t5/technology-blogs-by-sap/how-grant-types-keep-your-application-secure-lab-setup/ba-p/13525346)  
Blog 2022 - [How grant-types keep your application secure?](https://community.sap.com/t5/technology-blogs-by-sap/how-grant-types-keep-your-application-secure/ba-p/13523970)  
- [How grant-types keep your application secure – Exercise 1](https://community.sap.com/t5/technology-blogs-by-sap/how-grant-types-keep-your-application-secure-exercise-1/ba-p/13525435)  
- [How grant-types keep your application secure – Exercise 2](https://community.sap.com/t5/technology-blogs-by-sap/how-grant-types-keep-your-application-secure-exercise-2/ba-p/13525481)  
- [How grant-types keep your application secure – Exercise 3](https://community.sap.com/t5/technology-blogs-by-sap/how-grant-types-keep-your-application-secure-exercise-3/ba-p/13525513)  
