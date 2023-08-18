@startuml

package "Frontend (NextJS)" {
  [User] --> [Frontend]
}

database "Rust Visualization Database (GraphQL)" as DB1 {
  [Data & Visualization Service (Rust)] --> DB1
  [Frontend] --> [Data & Visualization Service (Rust)]
}

database "Rust Authorization Database (gRPC)" as DB2 {
  [Authorization Service (NGAC, Rust)] --> DB2
  [Frontend] --> [Authorization Service (NGAC, Rust)]
}

database "Go Collaboration Database (gRPC)" as DB3 {
  [Real-time Collaboration Service (Go)] --> DB3
  [Frontend] --> [Real-time Collaboration Service (Go)]
}

[Frontend] --> [gRPC Service]
[Data & Visualization Service (Rust)] --> [gRPC Service]
[Authorization Service (NGAC, Rust)] --> [gRPC Service]
[Real-time Collaboration Service (Go)] --> [gRPC Service]

@enduml
