# Farmbot Simulator

We are building a simulator for the [Farmbot Agricultural Robot](https://farm.bot) for use in both education and research. You can now learn to program and control the robot without a physical robot present and test your sequences before deploying them to a real robot.

It is especially useful in education where several students may require to program a robot yet it is neither feasible to have a robot per student nor can the students all test certain functions like irrigation on a single real garden.

We have implemented the following features:
- [ ] Basic movement
- [ ] Different robots
- [ ] Tool handling
- [ ] Plant growth
- [ ] Day and night simulation

```mermaid
flowchart TB
classDef borderless stroke-width:0px
classDef darkBlue fill:#00008B, color:#fff
classDef brightBlue fill:#6082B6, color:#fff
classDef gray fill:#62524F, color:#fff
classDef gray2 fill:#4F625B, color:#fff
classDef red fill:#f00, color:#fff

subgraph webApp[ ]
    pU_A[[webApp<br/> ]]
    pU_B[farmbotsimulator.github.io/app]
end
class webApp,pU_A gray

subgraph webAppCode[ ]
    wAC_A[[webApp Code<br/> ]]
    wAC_B[github.com/FarmbotSimulator/farmbotSimulator]
end
class webAppCode,wAC_A gray2
class wAC_A borderless
webAppCode-->webApp

subgraph webAppAssets[ ]
    wAA_A[[webAppAssets<br/> ]]
    wAA_B[farmbotsimulator.github.io/web]
end
class wAA_A borderless
subgraph webAppAssetsCode[ ]
    wAAC_A[[webAppAssets Code<br/> ]]
    wAAC_B[github.com/FarmbotSimulator/web]
end
class wAAC_A borderless
webAppAssetsCode-->webAppAssets
webAppAssets---->webApp


subgraph robotsPrivate[ ]
    rPr_A[[Private Robots<br/> ]]
    rPr_B[farmbotsimulator.github.io/web]
end
subgraph robotsPublic[ ]
    rPu_A[[Public Robots<br/> ]]
    rPu_B[farmbotsimulator.github.io/web]
end
subgraph robotsAssets[ ]
    rA_A[[Robots Assets<br/> ]]
    rA_B[farmbotsimulator.github.io/robots]
end
subgraph worlds[ ]
    w_A[[worlds<br/> ]]
    w_B[Robot models]
end
class w_A borderless
click wb "https://github.com/brianmechanisms/concepts" "Robot models"

subgraph site[ ]
    s_A[[Site<br/> ]]
    S_B[farmbotsimulator.github.io]
end
subgraph siteCode[ ]
    sC_A[[Website Code<br/> ]]
    SC_B[farmbotsimulator.github.io]
end
worlds-->robotsPrivate-->robotsPublic-->robotsAssets-->webApp-->site
robotsAssets-->webAppCode
siteCode-->site




subgraph farmbotProxy[ ]
    A3[[farmbot Proxy]]
    B3[Creates a persistent session]
end
class farmbotProxy,A3 brightBlue

subgraph billingServer[ ]
    bs_A[[Billing Server]]
    bs_B[...]
end
class billingServer,bs_A red

webApp<---->farmbotProxy
farmbotProxy<--Rest API-->billingServer
```
