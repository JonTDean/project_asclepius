@startuml

package "Frontend (NextJS)" {
  [User] --> [Frontend]
}

[Frontend] <..> [Data & Visualization Service (Rust)] : GraphQL
[Frontend] --> [Authorization Service (NGAC, Rust)]
[Frontend] --> [Real-time Collaboration Service (Go)]

database "Rust Visualization Database" as DB1 {
}

database "Rust Authorization Database" as DB2 {
}

database "Go Collaboration Database" as DB3 {
}

[Data & Visualization Service (Rust)] --> DB1
[Authorization Service (NGAC, Rust)] --> DB2
[Real-time Collaboration Service (Go)] --> DB3

[Data & Visualization Service (Rust)] --> [gRPC Service]
[Authorization Service (NGAC, Rust)] --> [gRPC Service]
[Real-time Collaboration Service (Go)] --> [gRPC Service]

@enduml
