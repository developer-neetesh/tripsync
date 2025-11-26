<div align="center">

# ✈️ TripSync

**Your All-in-One Trip Management Companion**

*Plan, collaborate, and share memories seamlessly with your travel companions*

[![React Native](https://img.shields.io/badge/React%20Native-0.79.1-61DAFB?logo=react&logoColor=white)](https://reactnative.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-6.16.0-47A248?logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![License](https://img.shields.io/badge/License-ISC-blue.svg)](LICENSE)

</div>

---

## 🌟 Overview

**TripSync** is a comprehensive mobile application designed to simplify group travel planning and coordination. Whether you're organizing a weekend getaway or a month-long adventure, TripSync keeps everyone in sync with real-time updates, offline support, and seamless collaboration features.

### 🎯 Key Features

#### 📅 **Trip Management**
- Create and organize multiple trips with detailed information
- Set start and end dates for better planning
- Invite participants via email or deep links
- Manage trip participants with role-based access

#### 🗺️ **Itinerary Planning**
- Build detailed day-by-day itineraries
- Drag-and-drop reordering for easy adjustments
- Add locations, activities, and notes
- View itinerary on interactive maps

#### 💬 **Real-Time Chat**
- Instant messaging with Socket.io
- Share photos, locations, and documents
- Typing indicators and read receipts
- Message forwarding and deletion
- Online/offline status indicators

#### 💰 **Expense Tracking & Splitting**
- Track all trip expenses in one place
- Automatically split costs among participants
- View individual and group spending summaries
- Export expense reports

#### 📄 **Document Management**
- Upload and share trip documents
- Store important files (passports, tickets, reservations)
- PDF generation and viewing
- Cloud storage integration with Cloudinary

#### 📍 **Location Sharing**
- Share and view locations on maps
- Interactive map viewer with React Native Maps
- Location-based itinerary items

#### 🔄 **Offline-First Architecture**
- Full functionality without internet connection
- Automatic sync when connection is restored
- WatermelonDB for local data persistence
- Conflict resolution and data integrity

#### 🔔 **Push Notifications**
- Real-time notifications for trip updates
- Invitation alerts
- Message notifications
- Firebase Cloud Messaging integration

#### 🔐 **Secure Authentication**
- JWT-based authentication
- Google Sign-In integration
- Secure token storage
- Protected API routes

---

## 🏗️ Architecture

### **Client (React Native)**
- **Framework**: React Native 0.79.1
- **State Management**: WatermelonDB (offline-first database)
- **Navigation**: React Navigation v7
- **Real-time**: Socket.io Client
- **UI Components**: React Native Paper
- **Maps**: React Native Maps
- **Notifications**: Firebase Cloud Messaging

### **Server (Node.js)**
- **Runtime**: Node.js 18+
- **Framework**: Express.js 5.1.0
- **Database**: MongoDB with Mongoose
- **Real-time**: Socket.io Server
- **Authentication**: JWT
- **File Storage**: Cloudinary
- **Email**: Nodemailer

---

## 📱 Screenshots

*Add your app screenshots here*

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** 18 or higher
- **npm** or **yarn**
- **MongoDB** (local or cloud instance)
- **React Native** development environment
  - For iOS: Xcode and CocoaPods
  - For Android: Android Studio and JDK
- **Firebase** project (for push notifications)
- **Cloudinary** account (for media storage)

### Installation

#### 1. Clone the Repository

```bash
git clone https://github.com/developer-neetesh/tripsync.git
cd tripsync
```

#### 2. Server Setup

```bash
cd server
npm install
```

Create a `.env` file in the `server` directory:

```env
PORT=3000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
EMAIL_HOST=your_email_host
EMAIL_PORT=587
EMAIL_USER=your_email_user
EMAIL_PASS=your_email_password
FIREBASE_PROJECT_ID=your_firebase_project_id
```

Start the server:

```bash
npm start
# or for development with auto-reload
npm run dev
```

#### 3. Client Setup

```bash
cd client
npm install
```

For iOS:

```bash
cd ios
pod install
cd ..
npm run ios
```

For Android:

```bash
npm run android
```

#### 4. Firebase Configuration

1. Create a Firebase project
2. Add iOS and Android apps to your Firebase project
3. Download configuration files:
   - iOS: `GoogleService-Info.plist` → `client/ios/client/`
   - Android: `google-services.json` → `client/android/app/`
4. Enable Firebase Cloud Messaging in your Firebase console

#### 5. Configure API Endpoint

Update `client/src/config.js` with your server URL:

```javascript
export const API_BASE_URL = 'http://your-server-url:3000';
```

---

## 📂 Project Structure

```
TripSync/
├── client/                 # React Native mobile app
│   ├── src/
│   │   ├── apis/          # API clients and services
│   │   ├── assets/        # Images, fonts, etc.
│   │   ├── components/    # Reusable UI components
│   │   ├── config.js      # App configuration
│   │   ├── hooks/         # Custom React hooks
│   │   ├── models/        # WatermelonDB models
│   │   ├── screen/        # Screen components
│   │   └── services/      # Business logic services
│   ├── android/           # Android native code
│   ├── ios/               # iOS native code
│   └── package.json
│
└── server/                # Node.js backend
    ├── config/            # Configuration files
    ├── configs/           # Database and service configs
    ├── controllers/       # Route controllers
    ├── middleware/        # Express middleware
    ├── models/            # Mongoose models
    ├── routes/            # API routes
    ├── utils/             # Utility functions
    └── app.js             # Express app entry point
```

---

## 🔧 Key Technologies

### Frontend
- **React Native** - Cross-platform mobile framework
- **WatermelonDB** - Offline-first database
- **React Navigation** - Navigation library
- **Socket.io Client** - Real-time communication
- **React Native Paper** - Material Design components
- **React Native Maps** - Map integration
- **Firebase** - Push notifications and authentication

### Backend
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Socket.io** - WebSocket server
- **JWT** - Authentication tokens
- **Cloudinary** - Media storage and processing
- **Nodemailer** - Email service

---

## 🎨 Features in Detail

### Offline Support
TripSync uses WatermelonDB to provide a seamless offline experience. All data is stored locally and automatically synced when connectivity is restored. Users can create trips, send messages, and manage expenses even without internet access.

### Real-Time Synchronization
Powered by Socket.io, TripSync provides instant updates across all connected devices. Changes to trips, messages, or expenses are reflected immediately for all participants.

### Deep Linking
Invite participants seamlessly with deep links. Users can join trips directly from email invitations or shared links, with automatic navigation to the correct screen.

### Smart Sync Service
The sync service intelligently manages data synchronization, handling conflicts and ensuring data integrity across devices and network conditions.

---

## 🔐 Security

- JWT-based authentication
- Secure token storage using AsyncStorage
- Protected API routes with middleware
- Input validation and sanitization
- Secure file upload handling

---

## 📝 API Documentation

### Authentication
- `POST /api/users/register` - Register new user
- `POST /api/users/login` - User login
- `GET /api/users/profile` - Get user profile

### Trips
- `GET /api/trips` - Get all trips
- `POST /api/trips` - Create new trip
- `GET /api/trips/:id` - Get trip details
- `PUT /api/trips/:id` - Update trip
- `DELETE /api/trips/:id` - Delete trip

### Chat
- `GET /api/chat/:tripId/messages` - Get messages
- `POST /api/chat/:tripId/messages` - Send message
- `DELETE /api/chat/messages/:messageId` - Delete message

### Expenses
- `GET /api/trips/:tripId/expenses` - Get expenses
- `POST /api/trips/:tripId/expenses` - Create expense
- `PUT /api/expenses/:id` - Update expense

*For complete API documentation, see the [API Documentation](./docs/API.md)*

---

## 🧪 Testing

```bash
# Client tests
cd client
npm test

# Server tests
cd server
npm test
```

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the ISC License.

---

## 👥 Authors

**Neetesh** - [@developer-neetesh](https://github.com/developer-neetesh)

---

## 🙏 Acknowledgments

- React Native community
- WatermelonDB team
- All contributors and testers

---

## 📞 Support

For support, email support@tripsync.app or open an issue in the [repository](https://github.com/developer-neetesh/tripsync/issues).

---

## 🔗 Repository

**GitHub**: [https://github.com/developer-neetesh/tripsync](https://github.com/developer-neetesh/tripsync)

---

<div align="center">

**Made with ❤️ for travelers everywhere**

[Report Bug](https://github.com/developer-neetesh/tripsync/issues) · [Request Feature](https://github.com/developer-neetesh/tripsync/issues) · [Documentation](https://github.com/developer-neetesh/tripsync/wiki)

</div>

