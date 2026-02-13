# Socially 📱

**Socially** is a high-performance, native Android social media ecosystem. Unlike simple wrappers, Socially implements a hybrid architecture combining a **PHP REST API** for data persistence, **Firebase** for real-time signaling, and **Agora SDK** for carrier-grade voice and video communication. 

<p align="center">
  <img src="./assets/app-mockup.png" alt="Socially App Mockup" width="80%" />
</p>

---

## 🚀 Key Features

### 📸 Content & Engagement
- **Dynamic Feed:** Supports image posts with full like/comment functionality.
- **Stories:** Ephemeral image sharing with automated expiration logic.
- **Offline Mode:** Comprehensive caching via a local SQLite database, allowing users to browse content without an active connection.

### 💬 Advanced Messaging
- **Real-Time Chat:** Powered by a mix of PHP polling and Firebase Cloud Messaging (FCM).
- **Vanish Mode:** Ephemeral messaging where content disappears after being viewed.
- **Privacy First:** Native screenshot detection that alerts users when a conversation is captured.

<p align="center">
  <img src="./assets/chat-features.png" alt="Chat UI and Vanish Mode" width="45%" />
  <img src="./assets/video-call.png" alt="Agora Video Call Interface" width="45%" />
</p>

### 📞 Real-Time Communication
- **Voice & Video Calls:** Integrated **Agora RTC SDK** for high-quality, low-latency calling.
- **Call Orchestration:** Intelligent channel naming and signaling via Firebase.

---

## 🛠 Tech Stack

- **Client:** Kotlin (Native Android), Glide, Volley, SQLite.
- **Backend:** PHP (REST API), Node.js (Cloud Functions).
- **Real-Time:** Firebase (RTDB, FCM, Auth).
- **Media:** Agora RTC SDK.

---

## 🏗 Architecture & Data Flow

1. **REST Flow:** Standard CRUD operations (Login, Signup, Post Creation) are handled by PHP endpoints.
2. **Real-Time Flow:** Messaging triggers a Node.js Cloud Function (`onCreate`) that watches the Realtime DB to push instant FCM notifications.
3. **Hybrid Sync:** The app uses a `NetworkMonitor` to toggle between the live API and the `LocalDatabase` cache.

---
