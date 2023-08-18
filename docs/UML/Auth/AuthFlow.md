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

' Color settings for the "Registration" split
skinparam Activity {
  BackgroundColor #E6B0AA
  BorderColor #943126
}

' Level 2: Initial Actions
split
    :User Chooses to Register;
    ' Level 3: Registration Flow
    start
    :User Accesses Registration Page;
    :User Accesses Register Form;
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
    :User is redirected to site;
    :Prompted to Download Private Key (ONE TIME DOWNLOAD AND VIEW);
    :Downloads Private Key;
    :Private Key is then checked and Passphrase confirmed;
    :Registration Complete;

' Color settings for the "Login" split
skinparam Activity {
  BackgroundColor #AED6F1
  BorderColor #2874A6
}

split again
    :User Chooses to Login;
    ' Level 3: Login Flow
    start
    :User Accesses Login Page;
    :User Accesses Login Form;
    fork
        :User Provides Email;
        :System validates along with zkSNARK Proof;
    fork again
        :User Inputs Private Key Passphrase;
        :System Decrypts Private Key Using Passphrase;
        :User Inputs zkSNARK Proof Derived from Private Key;
        :System Verifies zkSNARK Proof;
    end fork
    :Login Complete;
end split

:System Grants Session Token;
:User is Redirected to Dashboard;

@enduml
