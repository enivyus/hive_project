# Hive Community Platform

A full-stack community platform with real-time voice chat, posts, communities, and more.

![Hive Community](https://images.unsplash.com/photo-1522071820081-009f0129c71c?w=1200)

## Features

### Frontend
- 🔐 **Authentication** - Login/Signup with JWT
- 🏠 **Feed** - View and interact with posts (like, comment, share)
- 📝 **Create Post** - Upload images and add captions
- 👥 **Communities** - Browse and join communities
- 👤 **Profile** - View and edit user profiles with animated stats
- 🎙️ **Voice Chat Rooms** - Real-time voice chat with WebRTC
- 💬 **Text Chat** - Real-time messaging in rooms
- 🎨 **Dark Theme** - Beautiful purple glow design

### Backend
- 🔑 **JWT Authentication** - Secure login/register
- 📝 **Posts API** - CRUD operations, likes, comments
- 👥 **Communities API** - Join/leave communities
- 💬 **Socket.io** - Real-time chat and WebRTC signaling
- 🎙️ **WebRTC Support** - Voice chat signaling server

## Tech Stack

### Frontend
- React 18 + TypeScript
- Vite (build tool)
- Tailwind CSS
- shadcn/ui components
- Zustand (state management)
- React Router
- Socket.io Client

### Backend
- Node.js
- Express.js
- Socket.io (WebSockets)
- JWT Authentication
- CORS enabled

## Project Structure

```
/mnt/okcomputer/output/
├── app/                    # Frontend React app
│   ├── src/
│   │   ├── components/     # Reusable components
│   │   ├── layouts/        # Page layouts
│   │   ├── lib/            # Utilities & API client
│   │   ├── pages/          # Page components
│   │   ├── store/          # Zustand stores
│   │   └── App.tsx         # Main app component
│   ├── dist/               # Build output
│   └── package.json
│
├── backend/                # Node.js backend
│   ├── server.js           # Main server file
│   ├── package.json
│   ├── railway.toml        # Railway deployment config
│   └── README.md
│
└── README.md               # This file
```

## Local Development

### Prerequisites
- Node.js 18+
- npm or yarn

### 1. Start the Backend

```bash
cd backend
npm install
npm run dev
```

Backend will run on `http://localhost:3001`

### 2. Start the Frontend

```bash
cd app
npm install
npm run dev
```

Frontend will run on `http://localhost:5173`

### 3. Open in Browser

Navigate to `http://localhost:5173` and enjoy!

## Deployment

### Backend to Railway

1. **Install Railway CLI** (optional):
```bash
npm install -g @railway/cli
```

2. **Create Railway Account**:
   - Go to [railway.app](https://railway.app)
   - Sign up with GitHub

3. **Deploy via GitHub** (Recommended):
   - Push your code to GitHub
   - In Railway dashboard: New Project → Deploy from GitHub repo
   - Select your repository
   - Railway will auto-deploy

4. **Set Environment Variables**:
   In Railway dashboard, add these variables:
   ```
   JWT_SECRET=your-super-secret-key-here
   FRONTEND_URL=https://your-frontend-url.com
   NODE_ENV=production
   ```

5. **Get Backend URL**:
   - After deployment, Railway provides a URL
   - Copy it for frontend configuration

### Frontend to Vercel/Netlify

1. **Build the frontend**:
```bash
cd app
npm run build
```

2. **Deploy to Vercel**:
```bash
npm install -g vercel
vercel --prod
```

3. **Set Environment Variable**:
   In Vercel dashboard, add:
   ```
   VITE_API_URL=https://your-railway-backend-url.up.railway.app
   ```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user

### Posts
- `GET /api/posts` - Get all posts
- `POST /api/posts` - Create new post
- `POST /api/posts/:id/like` - Like a post
- `POST /api/posts/:id/unlike` - Unlike a post
- `POST /api/posts/:id/comments` - Add comment

### Communities
- `GET /api/communities` - Get all communities
- `POST /api/communities/:id/join` - Join community
- `POST /api/communities/:id/leave` - Leave community

### User
- `GET /api/users/me` - Get current user
- `PATCH /api/users/me` - Update user profile

### Health
- `GET /health` - Server health check

## WebSocket Events

### Client → Server
- `join-room` - Join a voice/chat room
- `leave-room` - Leave a room
- `send-message` - Send chat message
- `offer` - WebRTC offer
- `answer` - WebRTC answer
- `ice-candidate` - WebRTC ICE candidate
- `speaking` - Update speaking status

### Server → Client
- `user-joined` - New user joined room
- `user-left` - User left room
- `room-users` - List of room users
- `new-message` - New chat message
- `offer` - WebRTC offer
- `answer` - WebRTC answer
- `ice-candidate` - WebRTC ICE candidate
- `user-speaking` - User speaking status changed

## Environment Variables

### Frontend (.env)
```
VITE_API_URL=http://localhost:3001
```

### Backend (.env)
```
PORT=3001
JWT_SECRET=your-secret-key
FRONTEND_URL=http://localhost:5173
NODE_ENV=development
```

## Customization

### Colors
Edit `app/src/index.css` to change the color scheme:
- Primary Purple: `#7C3AED`
- Dark Background: `#0A0A0A`
- Card Background: `#141414`

### Fonts
The app uses:
- **Inter** - Main font for text
- **Space Grotesk** - Numbers and stats

## Troubleshooting

### Backend won't start
- Check if port 3001 is available
- Verify all dependencies are installed
- Check `.env` file exists

### Frontend can't connect to backend
- Verify `VITE_API_URL` is correct
- Check CORS settings in backend
- Ensure backend is running

### WebRTC not working
- Both users need to be in the same room
- Check browser permissions for microphone
- Use HTTPS in production (required for WebRTC)

## License

MIT License - feel free to use this project for your own community platform!

## Credits

Built with ❤️ using:
- [React](https://react.dev)
- [Vite](https://vitejs.dev)
- [Tailwind CSS](https://tailwindcss.com)
- [shadcn/ui](https://ui.shadcn.com)
- [Socket.io](https://socket.io)
- [Railway](https://railway.app)
"# hive_project" 
"# hive_project" 
