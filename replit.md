# Groovlee - Music Streaming Application

**Developer**: Ashutosh Anand  
**Project Type**: Full-Stack Web Application for College Placement  
**Development Period**: 2024  

## Overview

Groovlee is a modern music streaming application built with a full-stack TypeScript architecture by Ashutosh Anand. It features a Spotify-like interface with playlist management, music playback controls, search functionality, and a responsive design. The application demonstrates advanced full-stack development skills and modern web development practices. The application uses a monorepo structure with separate client and server directories, sharing types and schemas through a common `shared` folder.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **UI Components**: Radix UI primitives with shadcn/ui component library
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: React hooks with TanStack Query for server state
- **Build Tool**: Vite for fast development and optimized builds

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon serverless PostgreSQL
- **API Style**: RESTful API endpoints
- **Development**: Hot module replacement with Vite middleware

### Data Storage
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Schema**: Type-safe database schemas with Zod validation
- **Migrations**: Drizzle Kit for database migrations
- **Session Storage**: PostgreSQL-based session storage with connect-pg-simple

## Key Components

### Database Schema
The application defines three main entities:
- **Playlists**: User-created collections with songs stored as JSON arrays
- **Songs**: Individual tracks with metadata (title, artist, album, duration, cover art)
- **Albums**: Album information with artist and release details

### API Endpoints
- `GET /api/playlists` - Fetch user playlists
- `GET /api/playlists/:id` - Get specific playlist details
- `POST /api/playlists` - Create new playlist
- `PATCH /api/playlists/:id` - Update playlist
- `DELETE /api/playlists/:id` - Delete playlist
- `POST/DELETE /api/playlists/:id/songs/:songId` - Manage playlist songs
- Song and album search endpoints with query parameters

### Frontend Pages
- **Home**: Featured content, recently played, and personalized recommendations
- **Search**: Real-time search for songs and albums
- **Library**: User's personal playlists and saved content
- **Playlist**: Individual playlist view with track management
- **404**: Error page for unmatched routes

### UI Components
- **Sidebar**: Navigation menu with responsive mobile support
- **TopBar**: Search functionality and navigation controls  
- **MusicPlayer**: Global music playback controls with progress tracking
- **AlbumCard**: Reusable component for displaying music content

## Data Flow

1. **Client Requests**: React components use TanStack Query for API calls
2. **API Layer**: Express routes handle HTTP requests with validation
3. **Storage Layer**: Abstract storage interface with in-memory implementation (designed to be replaced with database)
4. **Database**: Drizzle ORM manages PostgreSQL interactions
5. **Response**: JSON data flows back through the same layers

The application uses optimistic updates and caching through TanStack Query for smooth user experience.

## External Dependencies

### Core Framework Dependencies
- React 18 ecosystem (react-dom, react-hooks)
- Express.js with TypeScript support
- Vite build system with React plugin

### Database & Validation
- Drizzle ORM with PostgreSQL adapter
- Neon serverless database
- Zod for runtime type validation
- Drizzle-Zod for schema validation

### UI & Styling
- Tailwind CSS with PostCSS
- Radix UI component primitives
- Lucide React icons
- Class Variance Authority for component variants

### Development Tools
- TypeScript compiler
- ESBuild for server bundling
- tsx for TypeScript execution
- Replit-specific plugins for development

## Deployment Strategy

### Development
- Uses Vite dev server with Express middleware
- Hot module replacement for fast development
- TypeScript compilation with strict mode
- Automatic server restart with tsx

### Production Build
1. **Client Build**: Vite builds React app to `dist/public`
2. **Server Build**: ESBuild bundles Express server to `dist/index.js`  
3. **Assets**: Static files served from build directory
4. **Environment**: Production mode serves pre-built static files

### Database Setup
- Environment variable `DATABASE_URL` required for PostgreSQL connection
- Drizzle migrations stored in `./migrations` directory
- Schema changes managed through `npm run db:push`

The application is designed for deployment on Replit with automatic environment provisioning and includes development-specific features like error modals and cartographer integration.