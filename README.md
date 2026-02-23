# 🎒 Lost & Found Portal

A modern, production-ready Lost & Found Portal for college students. Built with a focus on UX, smart matching, and seamless authentication.

![Project Status](https://img.shields.io/badge/Status-Ready-brightgreen)
![Tech Stack](https://img.shields.io/badge/Tech%20Stack-Firebase%20%7C%20HTML%20%7C%20CSS%20%7C%20JS-blue)

## 📌 Problem Statement

College campuses often face challenges with lost and found items:
- Items get lost frequently but there's no systematic way to find them
- Students don't know where to check for found items
- Manual notice boards are ineffective and hard to maintain
- No way to automatically match lost items with found ones

## 💡 Solution

A digital Lost & Found Portal that:
- Allows students to report lost/found items with photos
- Provides a searchable database with filters
- Uses smart matching to suggest potential matches
- Integrates with Firebase for secure authentication

## ✨ Features

### 🔐 Authentication
- Google Login with Firebase Authentication
- Protected report page (requires login)
- User session management

### 📝 Report Items
- Report lost or found items
- Upload images with preview
- Select category (ID Card, Wallet, Phone, etc.)
- Add location and date details
- Automatic smart matching after submission

### 🔍 Browse & Search
- Card-based grid layout
- Search by item name, description, location
- Filter by category (Electronics, Books, etc.)
- Filter by status (Lost/Found)
- Sort by latest/oldest/name
- Detailed modal view for each item

### ⚡ Smart Matching
- Automatically detects potential matches
- Based on category + location similarity
- Shows alerts for matched items
- Click to view match details

### 🎨 UI/UX
- Premium glassmorphism design
- Smooth animations and transitions
- Fully responsive (mobile + desktop)
- Toast notifications
- Loading states

## 🛠 Tech Stack

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Backend**: Firebase (Firestore)
- **Authentication**: Firebase Auth (Google Sign-In)
- **Storage**: Firebase Storage (for images)
- **No frameworks** - Pure, clean vanilla code

## 📁 Project Structure

```
lost-found-portal/
├── index.html          # Landing page
├── report.html         # Report lost/found item
├── browse.html         # Browse items
│
├── css/
│   ├── style.css       # Main styles
│   └── animations.css  # Animation utilities
│
├── js/
│   ├── firebase.js     # Firebase configuration
│   ├── auth.js         # Authentication module
│   ├── utils.js        # Shared utilities
│   ├── report.js       # Report form handling
│   └── browse.js       # Browse & search
│
├── assets/
│   └── images/         # Static assets
│
└── README.md           # This file
```

## 🚀 How to Run Locally

### Prerequisites
- A Google account
- Node.js installed (optional, for local server)

### Setup Steps

1. **Clone or Download**
   
```
bash
   git clone <repository-url>
   cd lost-found-portal
   
```

2. **Set Up Firebase**
   - Go to [Firebase Console](https://console.firebase.google.com/)
   - Create a new project
   - Enable **Authentication** → Google Sign-in
   - Enable **Firestore Database**
   - Enable **Storage**
   - Copy your Firebase config

3. **Configure Firebase**
   - Open `js/firebase.js`
   - Replace the `firebaseConfig` object with your own config

4. **Set Firestore Rules** (for development)
   
```
   rules_version = '2';
   service cloud.firestore {
     match /databases/{database}/documents {
       match /{document=**} {
         allow read, write: if true;
       }
     }
   }
   
```

5. **Set Storage Rules** (for development)
   
```
   rules_version = '2';
   service firebase.storage {
     match /b/{bucket}/o {
       match /{allPaths=**} {
         allow read, write: if true;
       }
     }
   }
   
```

6. **Run the Project**
   
   Option A: Using a local server
   
```
bash
   # If you have Python installed
   python -m http.server 8000
   
   # Or if you have Node.js
   npx serve
   
```
   
   Option B: Using VS Code
   - Install "Live Server" extension
   - Right-click `index.html` → "Open with Live Server"

7. **Open in Browser**
   - Navigate to `http://localhost:8000`

## 📸 Screenshots

### Landing Page
- Hero section with animated background
- Live statistics
- Feature highlights
- Call-to-action buttons

### Report Page
- Glassmorphism form
- Image upload with preview
- Category dropdown
- Smart match notifications

### Browse Page
- Responsive card grid
- Search and filter bar
- Category badges
- Modal detail view

## 🔒 Security Notes

For production deployment:
1. Update Firestore rules to restrict public access
2. Add proper validation on the server side
3. Configure Firebase Auth domain in console
4. Enable Firebase App Check
5. Set up proper CORS policies

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License.

## 👨‍💻 Developed By

Lost & Found Portal Team

---

⭐ If you found this useful, please star the repository!
