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

package "Authorization Service" {

  [Access Resource (/resource/:resource_id)] #F5CBA7
  [Update User Attributes (/user/attributes)] #F5CBA7
  [Manage Policies (/policies)] #F5CBA7
  [View User Attributes (/user/attributes)] #F5CBA7
  [Delete User (/user/delete)] #F5CBA7
  
  note right of [Access Resource (/resource/:resource_id)]
    Method: GET
    Validates: Session token
    Checks: User attributes and Policies
    Returns: Resource data or error
  end note
  
  note right of [Update User Attributes (/user/attributes)]
    Method: PUT
    Validates: Session token
    Updates: User's attributes
  end note
  
  note right of [Manage Policies (/policies)]
    Method: POST/PUT
    Validates: Session token
    Checks: User privilege
    Manages: Insert/Update policy
  end note
  
  note right of [View User Attributes (/user/attributes)]
    Method: GET
    Validates: Session token
    Returns: User's attributes
  end note
  
  note right of [Delete User (/user/delete)]
    Method: DELETE
    Validates: Session token
    Deletes: User data
  end note

}



@enduml
