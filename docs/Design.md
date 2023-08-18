# Project Asclepius

## System Components
1. **Frontend (NextJS)**: Handles UI/UX, user input, data visualization, and real-time collaboration features.

2. **Backend (Rust)**:
    - **Data & Visualization Service**: Manages data storage, PK/PD calculations, and visualization.

    - **Authorization Service (NGAC)**: Manages user registration, login, and enforces next-generation access control and permissions.

3. **Backend (Go & Fiber)**:
    - **Real-time Collaboration Service**: Manages real-time collaboration logic, chat, and collaboration room metadata.
    
4. **Databases**:
    - **Rust Visualization Database**: Stores datasets and visualization metadata.
    
    - **Rust Authorization Database**: Stores user information and permissions.
    
    - **Go Collaboration Database**: Stores Collaboration Room metadata, chat logs, annotations, and real-time collaboration data.
    
    - **gRPC Service**: Facilitates real-time communication between the frontend and backend.

## User Flow

1. **User Registration/Login**: User accesses the platform and either logs in or registers.

2. **Dashboard Access**: Post-authentication, the user is presented with a dashboard showing available datasets, active Collaboration Rooms, and notifications.

3. **Data Upload**: User uploads a PK/PD dataset.

4. **Visualization & Analysis**: Once uploaded, the dataset is visualized, and basic PK/PD analysis tools are available.

5. **Collaboration Room Creation/Join**: User can create a new Collaboration Room or join an existing one.

6. **Real-time Collaboration**: Inside the Collaboration Room, users can annotate data, chat, and run shared analyses.

7. **Feedback & Polling**: Polls can be created for decision-making, with real-time results displayed.

8. **Data Archiving & Retrieval**: Users can archive datasets and retrieve past data.

