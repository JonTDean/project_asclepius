@startuml

' Styles
skinparam package {
  BackgroundColor #FFFFFF
  BorderColor #5B9BD5
}

skinparam component {
  BackgroundColor #A9DFBF
  BorderColor #196F3D
  FontColor #34495E
}

package "Authentication Service" {

  [Registration (/register)] #F9E79F
  [Authentication (/authenticate)] #F9E79F
  
  note right of [Registration (/register)]
    Method: POST
    Input: Email
    Generates: Key pair, zkSNARK parameters
    Stores: Public key, email, zkSNARK parameters
    Returns: Private key
  end note
  
  note right of [Authentication (/authenticate)]
    Method: POST
    Input: zkSNARK proof
    Validates: zkSNARK proof
    Returns: Session token
  end note
}


@enduml
