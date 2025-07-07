---
date: 2025-07-07
categories:
  - ENVIRO
tags:
  - WX
---
# Current State of Envirotron Web
Most Major features functional (Alerts, mostly functional outlooks, data storage)

<!-- more -->
![alt text](ENV_Map.png)

## Recent Features
- All ECCC Icon Codes now work

### Additional Data on outlooks
![alt text](funnels.png)
/// caption
Thunderstorm Outlook funnel cloud region
///

![alt text](tornados.png)
/// caption
Thunderstorm Outlook High Tornado Risk Region
///

### Aditional styling on some alerts
some Alerts have a caption that displays on them

![alt text](heatWarning.png)
/// caption
Heat Warning
///

#### Warnings
some severe warnings(currently Tornados and waterspouts) have additional stripes on them

![alt text](Torn_warn.png)
/// caption
Tornado Warning - has stripes and text
///


#### Watches and Advisories
Watches and Advisories have a dashed outline instead of a solid outline.

![alt text](SAQS.png)
/// caption
Special Air Quality Statement
///

## Current Bugs/Missing features
- ECCC Outlooks not auto loading (onto server)
- NWS Outlooks past Day1
- Components dont auto restart
- Extra symbols show up
    - ![alt text](extraSymbol.png)
- Timezones?
- local alerts getting frozen until webserver reboot

## Untested
- Extreme Risk ECCC TSO

## Project Layout
### Alerts
``` mermaid
sequenceDiagram
  autonumber
  participant Web Server
  destroy DL
  DL->>Alerts Exchange: CAP
  activate Alerts Exchange
  
  Alerts Exchange->>+AX: CAP
  deactivate Alerts Exchange
  AX->>+Feed Exchange: Feed Message Json<br/>AX.queue.{event}
  create participant Distributor
  Feed Exchange->>-Distributor: Feed Message Json
  activate Distributor
  Note left of Distributor: Immediately Queues <br/>or schedules message for later<br/><br/>depends on attached timestamp
  AX->>-Alerts Exchange: Alert Json <br/>alerts.{event}.{urgency}.{certainty}
  activate Alerts Exchange
  Alerts Exchange->>Web Server: Alert Json
  deactivate Alerts Exchange
  
  Distributor->>+Feed Exchange: Feed Message Json<br/>BRODCAST.active.{event}
  deactivate Distributor
  Feed Exchange->>Web Server: Feed Message Json
  #Feed Exchange->>Bsky: Feed Message Json
  deactivate Feed Exchange 
```
### Outlooks
``` mermaid
sequenceDiagram
  autonumber
  Outlook->>+Outlooks Exchange: ECCC TSO Json<br/>outlook.ECCC.{day}
  Outlooks Exchange->>-Web Server: ECCC TSO Json
  Outlook->>+Outlooks Exchange: NWS Outlook Json<br/>outlook.NWS.d{day}_{type}
  Outlooks Exchange->>-Web Server: NWS Outlook Json
```