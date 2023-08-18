@startuml

' Styles and Colors
skinparam package {
  BackgroundColor #FFFFFF
  BorderColor #5B9BD5
}

skinparam actor {
  BackgroundColor #D6EAF8
}

skinparam artifact {
  BackgroundColor #FCF3CF
  BorderColor #F39C12
}

actor User

package "Frontend" {
  ["Frontend"]
  artifact "Language: JavaScript/TypeScript\nPlatform: NextJS" as A1
  A1 -[dashed]-> ["Frontend"]
}

User --> "Frontend" : Accesses

cloud "Data & Visualization Service" #A9DFBF {
  [Visualization Service]
  database "Visualization Database" as DB1 #F9E79F {
  }
  [Visualization Service] --> DB1 : Uses
  artifact "Language: Rust\nProtocol: GraphQL" as A2
  A2 -[dashed]-> [Visualization Service]
}

cloud "Auth Service" #F5B7B1 {
  [Auth]
  database "Auth Database" as DB2 #D7BDE2 {
  }
  [Auth] --> DB2 : Uses
  artifact "Language: Rust\nProtocol: gRPC" as A3
  A3 -[dashed]-> [Auth]
}

cloud "Real-time Collaboration Service" #D6EAF8 {
  [Collaboration Service]
  database "Collaboration Database" as DB3 #D5F5E3 {
  }
  [Collaboration Service] --> DB3 : Uses
  artifact "Language: Go\nProtocol: gRPC" as A4
  A4 -[dashed]-> [Collaboration Service]
}

cloud "Logging & Monitoring Service" #D5DBDB {
  [Logging & Monitoring]
  artifact "Language: TBD\nPlatform/Service: TBD" as A5
  A5 -[dashed]-> [Logging & Monitoring]
}

["Frontend"] <-[dashed]-> [Visualization Service] : GraphQL
["Frontend"] <-[dashed]-> [Auth] : gRPC
["Frontend"] <-[dashed]-> [Collaboration Service] : gRPC

[Visualization Service] --> [Logging & Monitoring] : Logs
[Auth] --> [Logging & Monitoring] : Logs
[Collaboration Service] --> [Logging & Monitoring] : Logs

@enduml
