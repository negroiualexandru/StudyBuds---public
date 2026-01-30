# StudyBuds 📍
### *Real-Time Campus Study Group Finder*

[![Android](https://img.shields.io/badge/Android-3DDC84?style=flat&logo=android&logoColor=white)](https://developer.android.com/) [![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat&logo=firebase&logoColor=black)](https://firebase.google.com/) [![Google Maps](https://img.shields.io/badge/Google_Maps-4285F4?style=flat&logo=google-maps&logoColor=white)](https://developers.google.com/maps) 

**StudyBuds** is a centralized platform designed to connect college freshmen with classmates to form spontaneous study groups. Built in just 24 hours at **DubHacks 2024**, the native Android application utilizes **Google Maps** and **Firebase** to provide a real-time view of where students are studying on campus, eliminating the isolation of studying alone.

---

## 🏗️ System Architecture

```mermaid
%%{init: {'theme': 'base', 'themeVariables': { 'background': '#ffffff', 'primaryColor': '#ffffff', 'edgeLabelBackground':'#ffffff', 'tertiaryColor': '#ffffff', 'clusterBkg': '#fafafa', 'clusterBorder': '#e5e7eb', 'lineColor': '#4285F4', 'fontSize': '14px'}}}%%
graph LR
    %% --- NODES & SUBGRAPHS ---
    
    subgraph Client ["Client Device"]
        App["Android App<br/>(Java / XML)"]
    end

    subgraph Google_Services ["Google Cloud Services"]
        MapsAPI["Google Maps SDK<br/>(Map Visualization)"]
        Firestore[("Firebase Firestore<br/>(Real-Time DB)")]
    end

    %% --- CONNECTIONS ---
    
    %% 1. Map Flow
    App -- "1. Render Map" --> MapsAPI
    
    %% 2. Data Flow (Real-time)
    App -- "2. Create Group" --> Firestore
    Firestore -. "3. Live Sync Updates" .-> App

    %% --- STYLING ---
    
    %% Arrow Styling (Google Blue)
    linkStyle default stroke:#4285F4,stroke-width:2px,fill:none

    %% Node Colors
    style App fill:#3DDC84,stroke:#3DDC84,color:#fff
    style MapsAPI fill:#4285F4,stroke:#4285F4,color:#fff
    style Firestore fill:#FFCA28,stroke:#FFCA28,color:#333
    
    %% Background Colors
    style Client fill:#ffffff,stroke:#e5e7eb,color:#333
    style Google_Services fill:#f9fafb,stroke:#d1d5db,color:#333
```
---
## 🚀 Key Features

* **Interactive Campus Map:** integrated **Google Maps API** to display pins for active study groups nearby. Clicking a pin reveals the specific course (e.g., *"CSE 142"*) and location.
* **Real-Time Feed:** Powered by **Firebase Firestore**, the study groups list updates instantly. As soon as a student creates a group in the library, it appears on everyone else's feed without needing to refresh.
* **Group Management:** Users can browse detailed listings—including class name, exact location, and group size—and join with a single click or broadcast their own study session to the campus.

---

## 🛠️ Tech Stack

| Component | Technology | Role |
| :--- | :--- | :--- |
| **Database** | Firebase Firestore | Enabled real-time cloud syncing so students see new groups instantly. |
| **Maps** | Google Maps API | Provided the geolocation interface for visualizing study groups on the campus map. |
| **Context** | DubHacks 2024 | Built by a team of 3 in a 24-hour hackathon environment. |

---

## 📱 Interface Preview

<div align="center" style="display: flex; justify-content: center; flex-wrap: wrap; gap: 10px;">
  <img src="https://github.com/user-attachments/assets/2ffa40d2-ac3d-419b-a382-0ddc37926865" alt="Home Screen" width="18%" />
  <img src="https://github.com/user-attachments/assets/ceb55ed9-f33d-4fdd-b2d2-772aabed19f6" alt="Map View" width="18%" />
  <img src="https://github.com/user-attachments/assets/d37ac4a6-ecc2-4995-b482-4c3f7cb91223" alt="Group List" width="18%" />
  <img src="https://github.com/user-attachments/assets/02b41484-4865-4975-ab97-ce4279244749" alt="Create Group" width="18%" />
  <img src="https://github.com/user-attachments/assets/23146177-70c4-4311-8dfd-256dfc911c36" alt="Group Details" width="18%" />
</div>
