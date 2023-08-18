@startuml

' Styles for WBS
skinparam handwritten true
skinparam wbsDiagram {
  BackgroundColor #FCF3CF
  ArrowColor #F39C12
}

' User Flow for Authentication System
' Level 1: Starting Point
start

:User Accesses Website;

' Level 2: Initial Actions
split
    :User Chooses to Register;
    ' Level 3: Registration Flow
    start
    :User Accesses Registration Page;
    fork
        :Inputs Email;
        :System Validates Email Format;
    fork again
        :Chooses Private Key Passphrase;
        :System Checks Passphrase Strength;
        :Confirms Private Key Passphrase;
    end fork

    :System Generates Key Pair and zkSNARK Params;
    :System Stores Public Key, Email, zkSNARK Params in DB;
    :Sends Email with Verification & Private Key Download Link;
    :Prompt user to verify email and download Private Key;
    :User Clicks Verification Link in Email;
    :Prompted to Download Private Key (ONE TIME DOWNLOAD AND VIEW);
    :Downloads Private Key;
    :Registration Complete;
    :User is Redirected to Dashboard;


split again
    :User Chooses to Login;
    ' Level 3: Login Flow
    start
    :User Accesses Login Page;
    :User Provides Email;
    fork
        :User Inputs Private Key Passphrase;
        :System Decrypts Private Key Using Passphrase;
    fork again
        :User Inputs zkSNARK Proof Derived from Private Key;
        :System Verifies zkSNARK Proof;
    end fork
    :System Grants Session Token;
    :User is Redirected to Dashboard;
end split

end
@enduml
