# Envirotron Web
## Features
- Colored ECCC alerts
- Thunderstorm outlooks from ECCC and NWS
- ECCC Wether radar
- AHSP WMI forecasts integrated
- All alerts and outlooks are saved to a database

## How It works
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