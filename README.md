# Finding Your Way in ECS

ECS consists of a Framework, Methodology and Tooling. 

The repository structure is outlined below with links to respective locaitons.

## Simplicity & Ease

The ecs folder structer is intended to be simple and intuitive to navigate 

It is important that no prior knowledge of the ecs concepts nor ecs know-how is required.

Each folder serves a specific funciton and the usage of ecs is intended to be zero based - meaning - you begin at the top of the tree and work your way down. 

At each step in the tree-folder structure - there is a job that must be done. 

The job within each folder must be autonomous - it must be self validating and independently lifecycle managed.

Job are composable - ECS has service/job layers that are plugged together until the ecs is fully operational

## ECS Repository Structure

```
ecs/                           --> Start here
|-- docs/                      --> all documentation
    |-- tellMeMore/            --> All FAQ's and concepts are to be located here - How-To's are in Onboard/ & Operate/ folders
    |-- EIP                    --> ECP Improvement Proposals are locted here 
|-- src/                       --> All executable know how is located here
    |-- ec.genesis/            --> This is where all ECS implementations MUST originate 
    |-- ec.root/               --> This establishes the macro structure and root level identities and their privileges
    |-- ec.state/              --> For implementations that maintains state in the cloud environment (e.g. pulumi, terraform)
    |-- ec.control/            --> Control plane machinery for vending out GRC and ECP primitives 
    |-- ec.modules/            --> The details/opinions that can be vended by ECP
        |-- grc/               --> Governance, Risk and Compliance
        |   |-- capio/         --> Cloud API Observer - ingest API specs, diff, generate docs and recommend improvements
        |   |-- eco/           --> Enterprise Cloud Observer - No Ops lifecycle management for Continuous Assurance
        |       |-- producers/ --> Extensible Data driven event/poll based Producers of facts
        |       |-- consumers/ --> Expressions of measurements that assert an opinion over facts
        |-- ecp/               --> Enterprise Control Plane Primitives
            |-- teams/         --> Single Purpose: User action Controls at both pre-runtime & runtime
            |-- policy/        --> Single Purpose: Resource & Resource Property Controls at both deploy time & runtime
            |-- nodes/         --> The node that hosts “potential & kinetic” digital agency – has a reason to exist and no reason to change - It will hold base networking and telemetry service endpoints
                |-- cores/     --> 
                |-- hubs/
                |-- tenants/
            |-- services/      --> These are the codified instances of specialization that – once combined with the node, becomes and instance of digital agency
                |-- cores/     --> Services that are globally fault tolerant in nature - e.g. networking and identity
                |-- hubs/      --> Services that are dependant on the fault tolerance of a Region
                |-- spokes/    --> Services that are dedicated to a spedific Tenant
                |-- tenant/    --> Reusable services that accelerate time to value - codifying knowledge and know-how
        |-- templates          --> Registration of templates for use by the ECP
    |-- ec.config/             --> Multiple instances of ECP and GRC can be mantained in parallel (versioning)
        |-- %INSTANCE_ONE%     --> first instance
        |-- %INSTANCE_TWO%     --> second instance ...
|-- onboard/                   --> Step by step guide and commands for onboarding to ECS
|-- operate/                   --> Operating Model for managing the lifecycle of ECS
|-- improve/                       --> ECS Improvement proposals

```
