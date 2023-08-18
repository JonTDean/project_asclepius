<div align="center">
  <a name="logo" href="https://github.com/JonTDean/project_asclepius"><img src="media/logo.svg" alt="Project Asclepius" width="50"></a>
  <div>
    <!-- Title -->
    <h2>Project Asclepius</h2>
    <!-- Subtitles -->
    <div>
      <h3>A PK/PD Data Visualization & Analysis Platform</h3>
      <h4 align="center">🔬 Real-time collaboration for bio-analysis data 📊</h4>
    </div>
  </div>
</div>
<p align="center">
  <a href="https://github.com/JonTDean/project_asclepius/commits/main">
    <img src="https://img.shields.io/github/last-commit/JonTDean/project_asclepius.svg?style=plastic" alt="Last Commit" />
  </a>
  <a href="https://github.com/JonTDean/project_asclepius/commits/main">
    <img src="https://img.shields.io/github/commit-activity/y/JonTDean/project_asclepius.svg?style=plastic" alt="Commit Activity" />
  </a>
</p>

<div align="center">
  <h4>
    <a href="#overview">Overview</a> |
    <a href="#features">Features</a> |
    <a href="#installation">Installation</a> |
    <a href="#contribute">Contribute</a>
  </h4>
</div>

---

## Overview

The PK/PD Data Visualization & Analysis Platform is designed for bio companies to facilitate in-depth analysis of pharmacokinetic and pharmacodynamic data. With integrated real-time collaboration features, researchers and analysts can work synchronously, ensuring seamless data interpretation and faster decision-making. The platform supports both gRPC and GraphQL to accommodate various data access and manipulation needs.

![Screenshot or Visual representation of platform](URL_TO_SCREENSHOT)

## Features

- **Data Visualization:** Interactive charts and graphs to visualize PK/PD data.
- **Real-time Collaboration:** Collaborate with peers in real-time, ensuring synchronous data analysis.
- **Next-Gen Access Control:** Implementing NGAC for advanced authorization and access control.
- **GraphQL & gRPC Support:** Flexible querying with GraphQL for visualization and efficient real-time collaboration using gRPC.

## Installation

Instructions on how to set up and run the platform. Include necessary commands, environmental setup, etc.

```bash
# Clone the repository
git clone https://github.com/JonTDean/project_asclepius.git

# Navigate to directory
cd project_asclepius

# Install dependencies and setup
... [other necessary commands]
```

## Technologies Used

### Frontend:
- **NextJS:** 
  - **Modern React Framework:** Built atop React, NextJS offers server-side rendering and static site generation, ensuring faster page loads—a crucial feature for data-intensive applications.
  - **API Routes:** An API-first approach allows developers to create dedicated API routes within the application with ease.
  - **Built-in CSS & SASS Support:** This integration streamlines the styling process, ensuring a consistent and visually appealing user interface.
  - **Fast Refresh:** A feature ensuring rapid development by instantly refreshing upon code changes without losing the component's state.

### Backend:
- **Rust:** 
  - **Safety & Performance:** Rust, a systems programming language, offers memory safety without sacrificing performance, ensuring a robust and efficient backend service.
  - **Concurrency Management:** The ownership model in Rust prevents data races, making it apt for concurrent processing—a necessity for real-time data handling.
  - **Ecosystem:** The Cargo package manager and a growing library set provide Rust with the necessary tools for swift backend development.
- **Go & Fiber:** 
  - **Performance:** Go, a statically typed, compiled language, boasts of impressive performance, apt for real-time operations.
  - **Concurrency:** Goroutines in Go ensure efficient concurrent processing, crucial for managing multiple real-time collaboration sessions.
  - **Fiber Framework:** Built on Fasthttp, Fiber is designed for creating web applications with optimal performance.

### Database Systems:
- **Rust Visualization Database with GraphQL:** 
  - **Flexible Querying:** GraphQL enables clients to request only required data, thus reducing over-fetching and under-fetching.
  - **Strongly Typed Schema:** This feature ensures data consistency and validation.
  - **Real-time Subscriptions:** With GraphQL subscriptions, users receive real-time updates when data changes.
- **Rust Authorization Database & Go Collaboration Database with gRPC:** 
  - **Efficient Data Streaming:** Built atop HTTP/2, gRPC provides bi-directional streaming, facilitating real-time data communication.
  - **Protocol Buffers:** Serving as the interface definition language, it ensures efficient serialization of structured data.

### Protocols:
- **gRPC:** 
  - **Language Agnostic:** Supporting multiple programming languages, gRPC ensures seamless communication between different stack components.
  - **Deadlines/Timeouts:** Clients can specify their waiting duration for an RPC to complete. Servers can check this to decide if they should complete or abort operations that might take longer.
- **GraphQL:** 
  - **Declarative Data Fetching:** Clients can determine the exact data they need, reducing network data transfers.
  - **Strongly Typed:** Ensures data consistency and validation—vital for dependable data visualization and analysis.

### Authorization:
- **Next Generation Access Control (NGAC):** 
  - **Fine-grained Access Control:** Unlike traditional models, NGAC provides detailed and contextual access control. Users can only access data they're authorized to view.
  - **Policy-based:** NGAC, being policy-centric, offers more flexibility in defining access rules compared to the role-centric RBAC.
  - **Dynamic Attributes:** NGAC can utilize dynamic attributes (like time of day, location, etc.) in its access decisions.


## Future Milestones

### Enhanced Collaboration Features
- **What:** Introduce document sharing, whiteboarding, and annotation functionalities.
- **How:** Implement a real-time collaboration layer using WebSocket or similar technologies. Use libraries like [TogetherJS](https://togetherjs.com/) or [yjs](https://y-js.org/) for collaborative editing.
- **Why:** To offer users a seamless experience in sharing and jointly analyzing data without switching between tools.

### Advanced Data Analysis Tools
- **How:** Integrate machine learning libraries or platforms like TensorFlow or PyTorch. Develop models tailored for bio-analysis data.
- **Why:** To provide users with deeper insights, predictive analytics, and guided interpretation of complex data.

### User Profiles and Customization
- **What:** Allow users to customize their dashboard, save visualization templates, and set preferences.
- **How:** Create a user profile system with settings that impact the UI/UX. Use a database to store user preferences and templates.
- **Why:** To give users a personalized experience and save time by using previously saved visualization templates.

### Integration with External Data Sources
- **What:** Facilitate data import from popular bio-analysis tools and platforms.
- **How:** Develop connectors or use APIs provided by popular bio-analysis platforms to fetch data into the system.
- **Why:** To reduce manual data entry, streamline workflows, and support a wider range of data sources for users.

### Mobile Support
- **What:** Develop a responsive design or mobile application for on-the-go access.
- **How:** Optimize the existing web application using frameworks like Bootstrap for responsiveness or consider building native apps using Flutter or React Native.
- **Why:** To provide users with access to their data and collaboration tools from any device, anywhere.

### API Development
- **What:** Offer public APIs for third-party integrations and extensions.
- **How:** Use tools like Swagger for API documentation. Ensure APIs follow the RESTful principles and are secured using OAuth or similar protocols.
- **Why:** To foster a developer community around the platform and allow for broader integrations and extensions, enhancing the platform's capabilities.


## Contribute

We welcome contributions! Whether it's improving documentation, adding new features, or providing feedback, your input is valuable. Please see `CONTRIBUTING.md` for details on how you can help out.