# 🎵 Groovlee - Music Streaming Platform

A modern, full-stack music streaming web application built with React.js, TypeScript, and Tailwind CSS. Groovlee features a Spotify-like interface with playlist management, music playback controls, search functionality, and a responsive design.

**Developer**: Ashutosh Anand  
**Development Period**: 2024  

## ✨ Features

- 🎶 **Music Playback**: Full-featured music player with play/pause, skip, shuffle, and repeat
- 📱 **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- 🔍 **Search Functionality**: Real-time search for songs and albums
- 📂 **Playlist Management**: Create, edit, and manage personal playlists
- 🎨 **Modern UI**: Clean, dark-themed interface inspired by modern music apps
- ⚡ **Fast Performance**: Built with Vite for lightning-fast development and builds

## 🛠️ Tech Stack

### Frontend
- **React 18** - Modern UI framework with hooks
- **TypeScript** - Type-safe JavaScript development
- **Tailwind CSS** - Utility-first CSS framework
- **Wouter** - Lightweight client-side routing
- **TanStack Query** - Server state management and caching
- **Radix UI** - Accessible component primitives
- **Lucide React** - Beautiful icon library

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **TypeScript** - Type-safe server development
- **Drizzle ORM** - Type-safe database toolkit
- **PostgreSQL** - Robust relational database
- **Zod** - Schema validation library

### Development Tools
- **Vite** - Next-generation build tool
- **ESBuild** - Fast JavaScript bundler
- **PostCSS** - CSS transformation tool
- **tsx** - TypeScript execution engine

## 🚀 Getting Started

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn package manager

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/groovlee.git
   cd groovlee
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your database configuration
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

5. **Open your browser**
   Navigate to `http://localhost:5000`

## 📁 Project Structure

```
groovlee/
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/         # Application pages
│   │   ├── hooks/         # Custom React hooks
│   │   ├── lib/           # Utilities and helpers
│   │   └── contexts/      # React contexts
├── server/                # Backend Express application
│   ├── routes.ts          # API route definitions
│   ├── storage.ts         # Data storage interface
│   └── index.ts           # Server entry point
├── shared/                # Shared types and schemas
│   └── schema.ts          # Database schemas
└── Configuration files
```

## 🎯 API Endpoints

- `GET /api/playlists` - Fetch user playlists
- `GET /api/playlists/:id` - Get specific playlist
- `POST /api/playlists` - Create new playlist
- `PATCH /api/playlists/:id` - Update playlist
- `DELETE /api/playlists/:id` - Delete playlist
- `POST/DELETE /api/playlists/:id/songs/:songId` - Manage playlist songs
- `GET /api/songs` - Fetch all songs
- `GET /api/songs/search` - Search songs
- `GET /api/albums` - Fetch all albums
- `GET /api/albums/search` - Search albums

## 📱 Pages

- **Home** (`/`) - Featured content and recommendations
- **Search** (`/search`) - Search for music content
- **Library** (`/library`) - Personal playlists and collections
- **Playlist** (`/playlist/:id`) - Individual playlist view

## 🎨 Key Components

- **MusicPlayer** - Global music playback controls
- **Sidebar** - Navigation menu with responsive design
- **TopBar** - Search and navigation controls
- **AlbumCard** - Reusable content display component

## 🔧 Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm start` - Start production server
- `npm run check` - Run TypeScript type checking
- `npm run db:push` - Push database schema changes

## 🌟 Features in Detail

### Music Player
- **Playback Controls**: Play, pause, next, previous
- **Progress Tracking**: Real-time playback progress
- **Volume Control**: Adjustable volume with mute functionality
- **Shuffle & Repeat**: Multiple playback modes
- **Queue Management**: Dynamic playlist queuing

### Responsive Design
- **Mobile-First**: Optimized for mobile devices
- **Adaptive Layout**: Smooth transitions between screen sizes
- **Touch-Friendly**: Optimized touch interactions
- **Fast Loading**: Optimized performance across devices

### Data Management
- **Type Safety**: Full TypeScript integration
- **Caching**: Intelligent data caching with TanStack Query
- **Real-time Updates**: Live data synchronization
- **Error Handling**: Comprehensive error management

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Developer

**Ashutosh Anand**
- LinkedIn: [https://www.linkedin.com/in/ashutosh-anand-1651841b6/]
- GitHub: [https://github.com/ashutosh2287]

## 🙏 Acknowledgments

- Design inspiration from Spotify and modern music streaming platforms
- UI components built with Radix UI and shadcn/ui
- Icons provided by Lucide React
- Built with love using modern web technologies

---

**Built with ❤️ for college placement demonstration**
