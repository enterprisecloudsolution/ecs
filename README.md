# Avoiding Software Complexity

## Software = Behaviour (ware) that can change easily (soft). 
As opposed to Hardware: 
- Software yields functionality fast (no heavy atoms, just weightless bits)
- Encourages More Change (because you can, you will, and you should)
- Unless managed via a closed loop process, operational Complexity emerges (order => disorder => chaos)
- Complex Systems are Inherently unmanageable => Inability to see the system in its entirety


## Software Engineering is the:
- Recursive process of Ordering & Assembling the
- Universal building blocks of digital execution (Category theory => Composable Structures => Structure => Architecture)
- Subject to the universal software rules of coupling (text files that reference other text files)

## Software Architecture is a property of every software system
- Regardless of whether it is managed of not
- Left unmanaged, your software system will drift into complexity => disorder & chaos

## The role of Software Architecture Management is to continually strive for:
- Minimising the cost profile of the Software System (TCO & Margin Cost)
- Maximizing the Changeability of Software Systems
- Cost optimised Scaling of software engineering processes
- Partitioning the system into fail safe change zones to contain the impacts of breaches and bugs
- By solving for Inherent Structural Composition through the application of 
- Black box abstractions (Lego brick Shapes) and 
- Standard impedances (Lego brick Connectors)

# Structural Integrity

## Files, Folders and Git

The prime directive in ECS is to only depend on Files, Folders and Git. This is so that we can invert the details and change everything that the Enterprise Cloud Framework abstraction operates within.

## Files & Folders

The ecs folder structer is intended to be simple and intuitive to navigate.

Each folder should serve a specific funciton and the usage of ecs should be zero based - meaning - you begin at the top of the tree and work your way down. 

At each step in the tree-folder structure - there is a job that must be done. Each job is autonomous - it must be self validating and independently lifecycle managed.

Each job builds on the previous one - until the ecs is fully operational

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

```

## Git

When knowledge and know-how are codified - the code represents extremely powerful kinetic potential. 

Code must be transformed:
- **FROM:** Text in a file, in a folder structure  
- **TO:** bits running on a disk powered (*ultimately*) by a physical machine

This process is the source of all problems in software.

The impact that can occur from malicious or unintended change - can be catastrophic.

Git provides a strong governing mechanism that - when used effectively - significantly reduces the error rate that is inherent in change. When this process is coupled with a "change workflow" that gradually propagates changes across fail safe nodes - the impact of change related errors becomes a function of the **Value at risk** that is contained within the **blast radius of the fail safe zone**
