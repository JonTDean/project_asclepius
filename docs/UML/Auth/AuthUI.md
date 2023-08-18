@startwbs
' Styles for WBS
<style>
    wbsDiagram {
        LineColor #333
        ArrowColor #333
        RoundCorner 15
        BackgroundColor #F8F8F8
        FontName Arial
        LineStyle curved

        arrow {
            LineColor #666
        }

        :depth(0) {
            BackgroundColor #F6E58D
            LineColor #D35400
            FontColor #000
        }

        :depth(1) {
            BackgroundColor #FFD1C1
            LineColor #E74C3C
            FontColor #000
        }

        :depth(2) {
            BackgroundColor #A29BFE
            LineColor #6C5CE7
            FontColor #000
        }

        :depth(3) {
            BackgroundColor #92C3F1
            LineColor #1A73E8
            FontColor #000
        }
        
        :depth(4) {
            BackgroundColor #81ECEC
            LineColor #00B2CC
            FontColor #000
        }

        :depth(5) {
            BackgroundColor #1A73E8
            LineColor #92C3F1
            FontColor #FF
        }

        :depth(6) {
            BackgroundColor #FFD3BA
            LineColor #FF9B54
            FontColor #000
        }
    }
    .success {
        LineColor #27AE60;
        BackgroundColor #27AE60

    }
    .fail {
        LineColor #E74C3C;
        BackgroundColor #E74C3C
    }
    .logText {
        FontColor #000
    }
</style>

* User Accesses Hygieia Vision

** "Homepage (/)" as Home
*** LandingPage
**** "LoginButton" as LoginBtn
***** "Login Form (/login)" as LoginForm
****** "Authentication Successful <<success>>" as LoginSuccess
****** "Authentication Failed <<fail>>" as LoginFail
**** "RegisterButton" as RegisterBtn
***** "Registration Form (/register)" as RegForm
****** "Registration Successful <<success>>" as RegisterSuccess
****** "Registration Failed <<fail>>" as RegFail


** "Authorized (/authorize)" as Authorized
*** "User is authenticated via zkSNARKs" as AuthCheck
**** "Admin Dashboard (/admin/dashboard)" as AdminDash
***** AdminControls
****** "User Management" as UserManager
*******_ User Role Assignments
*******_ User Activity Logs
****** "System Monitoring" as SysMonitor
*******_ Site Statistics
*******_ System Health and Status
****** "Data Management" as DataManager
*******_ Data Backups
*******_ Data Upload for PK/PD Analysis
****** "Configuration & Feedback" as ConfigFeedback
*******_ System Configuration
*******_ Feedback Management

**** "User Dashboard (/dashboard)" as UserDash
***** DashboardMainView
****** UserDashboardActions
*******_ RecentDashboardActivity
*******_ Notifications and Alerts
*******_ Tasks or To-Do Lists
*******_ Calendar or Schedule Views
*******_ User-created Widgets or Panels
****** "Collaboration Rooms" as CollabRooms
*******_ Real-time Chat
*******_ Real-time Polling

**** "Account (/account)" as Account
***** "Profile (/account/profile)" as ProfilePage
****** UserProfile
*******_ Edit Profile
*******_ View Profile
***** "Settings (/account/settings)" as SettingsPage
****** UserSettings
*******_ Notification Preferences
*******_ Security Settings
***** "History (/account/history)" as HistoryPage
******_ User Activity Log <<logText>> 

LoginSuccess --> Authorized #Green
RegisterSuccess --> Authorized #Green
LoginFail --> LoginForm #Red
RegFail --> RegForm #Red

@endwbs