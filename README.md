🚆 Rail Sathi

Your AI companion for Indian Railways — smarter travel, less stress.

🌟 Overview

Rail Sathi is an AI-powered application designed to improve the Indian Railways travel experience. It solves real-world problems faced by millions of passengers daily — from ticket uncertainty to crowded coaches and lack of guidance during delays.

🚨 The Problem

Every day, over 13 million passengers travel via Indian Railways, facing issues like:

⏳ Endless IRCTC refresh for waitlist confirmation
👁️ No visibility into coach crowd levels
🔤 Need to remember station codes (NDLS, BCT, etc.)
🕰️ No guidance during train delays
🌐 Poor usability in low/no network areas
🗣️ Language barriers for non-English users

No single solution addresses all these — Rail Sathi does.

🚀 Features
🎫 Smart Seat Allocation (Split-Seat Algorithm)
Finds partial seat availability across stations
Combines them into a complete journey
Eliminates dependency on full-route confirmation

Example:

Seat A → Station 1 to 2
Seat B → Station 2 to 3
→ You get a full journey plan

📊 Real-Time Coach Crowd Detection
Users report crowd levels: LOW / MEDIUM / HIGH
Real-time sync using WebSockets
Smart validation:
📍 GPS speed lock (>25 km/h)
✅ Verified users = higher weight
📴 Offline support with auto-sync
🗣️ AI-Powered Search

Search naturally without station codes:

Input	Output
"Mumbai to Delhi tomorrow"	BCT → NDLS
"Bangalore Chennai weekend"	SBC → MAS
Supports voice + text
Handles:
Nicknames
Misspellings
Relative dates
🏟️ AI Station Guide

During delays, get:

🍽️ Food suggestions
🛋️ Waiting areas
🛍️ Shops & essentials
💡 Practical tips (ATM, charging, etc.)
🎙️ Voice-Based Travel Updates
AI reads:
Current station
Next stop
ETA
Works even without server (fallback to device TTS)
📡 Offline-First Experience
Works in:
Tunnels
Rural areas
Data is:
Stored locally
Synced automatically when online
🛠️ Tech Stack
📱 Frontend
React Native
Expo
TypeScript
⚙️ Backend
Node.js
Express
Socket.IO
🤖 AI & Voice
Groq (LLaMA + Whisper)
ElevenLabs (Text-to-Speech)
🔐 Auth
Auth0
🧠 System Design Highlights
Real-time architecture using WebSockets
Offline-first design with local persistence
AI-driven parsing for natural language queries
Fault-tolerant systems for unreliable networks
🧱 Challenges & Solutions
1. 🎙️ Voice Recording Bug
Issue: Recording stopped but no output
Cause: Race condition (object cleared too early)
Fix: Store reference before clearing
2. 📁 Audio Format Mismatch
Issue: Android requests failed (400 error)
Cause: .3gp sent as .m4a
Fix: Dynamic MIME type detection
3. 🔑 Environment Variables Issue
Issue: API key not detected
Cause: Wrong .env path
Fix: Use absolute path with dotenv
4. 📡 Lost Votes on Poor Network
Issue: Votes disappeared
Cause: Fire-and-forget WebSocket emit
Fix: Local storage + retry queue
5. 🐞 Silent Error Handling
Issue: Failures had no feedback
Cause: Generic catch block
Fix: Proper error handling + user feedback
📦 Installation
# Clone the repo
git clone [https://github.com/your-username/rail-sathi.git](https://github.com/manav-singhal12/RailSathi)

# Install dependencies
cd RailSathi
npm install

# Start development server
npm start
