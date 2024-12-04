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

## Remote debug

| Database | Workflow     | Authorization | Testing with .http files | Testing with UI          | Debug              |
|----------|--------------|---------------|--------------------------|--------------------------|--------------------|
| Hana     | BTP instance | XSUAA         | :x:                      | with BTP Fiori Launchpad | :white_check_mark: |

#### Process

Described in [SAP Article](https://blogs.sap.com/2021/06/11/set-up-remote-debugging-to-diagnose-cap-applications-node.js-stack-at-runtime-running-on-sap-btp-cloud-foundry-environment/)

#### TL;DR

1. `cf ssh test-app-srv`
2. `ps aux`
find a CAP process, copy processId
3. `kill -usr1 processId`
4. `exit` or open another terminal
5. `cf ssh -N -L 9229:127.0.0.1:9229 test-app-srv`
6. launch debug configuration which attach the IDE to the port to be able to debug

#### VSCode / BAS debug configuration
```
{
    "name": "Attach to a Cloud Foundry Instance on Port 9229",
    "port": 9229,
    "request": "attach",
    "type": "node",
    "localRoot": "${workspaceFolder}",
    "remoteRoot": "/home/vcap/app"
},
```


## Learn More

Learn more at https://cap.cloud.sap/docs/get-started/.

http://localhost:4004/main-service/ProcessRequests?$expand=SubTickets($expand=TicketDetails($expand=PurchaseOrder,Items($expand=PurchaseOrderItem)))
