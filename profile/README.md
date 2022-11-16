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
classDef green fill:#111, color:#fff

subgraph worlds[ ]
    w_A[[worlds<br/> ]]
    w_B[Robot models]
end
class w_A borderless
class worlds,w_A brightBlue
click w_B "https://github.com/brianmechanisms/concepts" _blank



subgraph robotsPrivate[ ]
    rPr_A[[Private Robots<br/> ]]
    rPr_B[github.com/FarmbotSimulator/robotsprivate]
end
class rPr_A borderless
click rPr_B "https://github.com/FarmbotSimulator/robotsprivate" _blank
class robotsPrivate,rPr_A brightBlue
subgraph robotsPublic[ ]
    rPu_A[[Public Robots<br/> ]]
    rPu_B[farmbotsimulator.github.io/web]
end
click rPu_B "https://github.com/FarmbotSimulator/robots" _blank
class rPu_A borderless
class robotsPublic,rPu_A red
subgraph robotsAssets[ ]
    rA_A[[Robots Assets<br/> ]]
    rA_B[farmbotsimulator.github.io/robots]
end
class rA_A borderless
class robotsAssets,rA_A gray
click rA_B "https://farmbotsimulator.github.io/robots" _blank

subgraph webApp[ ]
    pU_A[[webApp<br/> ]]
    pU_B[farmbotsimulator.github.io/app]
end
class pU_A borderless
class webApp,pU_A gray
click rA_B "https://farmbotsimulator.github.io/app" _blank

subgraph webAppCode[ ]
    wAC_A[[webApp Code<br/> ]]
    wAC_B[github.com/FarmbotSimulator/farmbotSimulator]
end
class webAppCode,wAC_A brightBlue
click rPr_B "https://github.com/FarmbotSimulator/farmbotSimulator" _blank
class wAC_A borderless
webAppCode-->webApp

subgraph webAppAssets[ ]
    wAA_A[[webAppAssets<br/> ]]
    wAA_B[farmbotsimulator.github.io/web]
end
click rPr_B "https://farmbotsimulator.github.io/web" _blank
class wAA_A borderless
class webAppAssets,wAA_A gray

subgraph webAppAssetsCode[ ]
    wAAC_A[[webAppAssets Code<br/> ]]
    wAAC_B[github.com/FarmbotSimulator/web]
end
click wAAC_B "https://farmbotsimulator.github.io/web" _blank
class wAAC_A borderless
class webAppAssetsCode red
webAppAssetsCode-->webAppAssets
webAppAssets---->webApp



subgraph site[ ]
    s_A[[Site<br/> ]]
    S_B[farmbotsimulator.github.io]
end
click S_B "https://farmbotsimulator.github.io" _blank
class s_A borderless
class site,s_A gray
subgraph siteCode[ ]
    sC_A[[Website Code<br/> ]]
    SC_B[farmbotsimulator.github.io]
end
click SC_B "https://github.com/FarmbotSimulator/FarmbotSimulator.github.io" _blank
class sC_A borderless
class siteCode,sC_A red
worlds-->robotsPrivate-->robotsPublic-->robotsAssets-->webApp-->site
robotsAssets-->webAppCode
siteCode-->site

subgraph farmbotProxy[ ]
    A3[[farmbot Proxy]]
    B3[github.com/FarmbotSimulator/farmbotProxy]
end
click B3 "https://github.com/FarmbotSimulator/farmbotProxy" _blank
class A3 borderless
class farmbotProxy,A3 red

subgraph billingServer[ ]
    bs_A[[Billing Server]]
    bs_B[...]
end
class bs_A borderless
class billingServer,bs_A green

webApp<---->farmbotProxy
farmbotProxy<--Rest API-->billingServer
```

```mermaid
flowchart TB
classDef darkBlue fill:#00008B, color:#fff
classDef brightBlue fill:#6082B6, color:#fff
classDef gray fill:#62524F, color:#fff
classDef gray2 fill:#4F625B, color:#fff
classDef red fill:#f00, color:#fff
classDef green fill:#111, color:#fff

subgraph Legend[Legend]
    Legend1[Public Site]
    Legend2[Public Repo]
    Legend3[Private Repo]
    Legend4[Not implemented]
end
class Legend1 gray
class Legend2 red
class Legend3 brightBlue
class Legend4 green
```
