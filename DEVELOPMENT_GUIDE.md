# Groovlee Development Guide
**Developer: Ashutosh Anand**

## 🛠️ Project Structure & Technologies

### Overview
Groovlee is a full-stack TypeScript application with separate frontend and backend, sharing common types.

```
groovlee/
├── client/                 # React Frontend
│   ├── src/
│   │   ├── components/     # UI Components (Sidebar, MusicPlayer, etc.)
│   │   ├── pages/          # App Pages (Home, Search, Library)
│   │   ├── hooks/          # Custom React Hooks
│   │   ├── lib/            # Utilities & Data
│   │   └── contexts/       # React Context Providers
│   └── index.html         # Main HTML file
├── server/                # Express Backend
│   ├── index.ts          # Server entry point
│   ├── routes.ts         # API endpoints
│   ├── storage.ts        # Data management
│   └── vite.ts           # Development server
├── shared/               # Shared TypeScript types
│   └── schema.ts        # Database schemas & types
└── Configuration files
```

## 🎯 Technologies Explained

### Frontend Stack
1. **React.js** - Component-based UI framework
   - Creates reusable UI components
   - Manages component state and lifecycle
   - Handles user interactions

2. **TypeScript** - Type-safe JavaScript
   - Catches errors during development
   - Provides better code completion
   - Makes code more maintainable

3. **Tailwind CSS** - Utility-first CSS framework
   - Pre-built CSS classes
   - Responsive design utilities
   - Consistent design system

4. **Wouter** - Lightweight routing
   - Client-side navigation
   - URL management
   - Page routing without page refresh

5. **TanStack Query** - Server state management
   - Caches API responses
   - Handles loading states
   - Automatic data synchronization

### Backend Stack
1. **Node.js** - JavaScript runtime
   - Runs JavaScript on the server
   - Handles HTTP requests
   - Manages file system operations

2. **Express.js** - Web framework
   - Creates REST API endpoints
   - Handles middleware
   - Manages HTTP routing

3. **In-Memory Storage** - Data management
   - Stores data in JavaScript Maps
   - Fast read/write operations
   - Perfect for development/demo

## 🚀 Running in VS Code

### Prerequisites
1. **Install Node.js** (v18 or higher)
   ```bash
   # Check if installed
   node --version
   npm --version
   ```

2. **Install VS Code Extensions**
   - TypeScript and JavaScript Language Features
   - ES7+ React/Redux/React-Native snippets
   - Tailwind CSS IntelliSense
   - Auto Rename Tag
   - Bracket Pair Colorizer

### Setup Instructions

1. **Download/Clone Project**
   ```bash
   # If using Git
   git clone <repository-url>
   cd groovlee

   # Or download ZIP and extract
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Development Commands**
   ```bash
   # Start development server (runs both frontend & backend)
   npm run dev

   # Build for production
   npm run build

   # Start production server
   npm start

   # Type checking
   npm run check
   ```

### VS Code Configuration

Create `.vscode/settings.json`:
```json
{
  "typescript.preferences.importModuleSpecifier": "relative",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "emmet.includeLanguages": {
    "typescript": "html",
    "typescriptreact": "html"
  },
  "tailwindCSS.experimental.classRegex": [
    "class:\\s*[\"']([^\"']*)[\"']"
  ]
}
```

Create `.vscode/launch.json` for debugging:
```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Launch Server",
      "type": "node",
      "request": "launch",
      "program": "${workspaceFolder}/server/index.ts",
      "runtimeArgs": ["-r", "tsx/cjs"],
      "env": {
        "NODE_ENV": "development"
      }
    }
  ]
}
```

## 🔧 Project Management

### File Organization
1. **Components** (`client/src/components/`)
   - Reusable UI pieces
   - Each component in its own file
   - Props interface defined for each

2. **Pages** (`client/src/pages/`)
   - Full page components
   - Handle routing and layout
   - Import and use smaller components

3. **Hooks** (`client/src/hooks/`)
   - Custom React logic
   - Reusable stateful logic
   - Business logic separation

4. **API Routes** (`server/routes.ts`)
   - REST endpoints
   - HTTP method handlers
   - Data validation

### Development Workflow

1. **Frontend Development**
   ```bash
   # Component creation pattern
   client/src/components/NewComponent.tsx
   
   # Page creation pattern
   client/src/pages/new-page.tsx
   
   # Hook creation pattern
   client/src/hooks/use-new-feature.tsx
   ```

2. **Backend Development**
   ```bash
   # Add new API endpoint in server/routes.ts
   # Update storage interface in server/storage.ts
   # Add new types in shared/schema.ts
   ```

3. **Styling**
   ```bash
   # Tailwind classes in components
   # Custom CSS in client/src/index.css
   # CSS variables for theming
   ```

## 📊 Key Features Explained

### Music Player Hook (`use-music-player.tsx`)
- Manages current song, play state, volume
- Handles play/pause, next/previous functionality
- Simulates audio playback with timer

### Data Flow
1. **Frontend requests data** → TanStack Query
2. **API call to backend** → Express routes
3. **Data retrieval** → Storage layer
4. **Response back to frontend** → Component updates

### State Management
- **Local state**: useState for component-specific data
- **Global state**: Custom hooks for shared functionality
- **Server state**: TanStack Query for API data

## 🎨 Styling System

### Tailwind Classes
```css
/* Common patterns used */
bg-gray-800        /* Dark backgrounds */
text-green-500     /* Accent colors */
hover:bg-gray-700  /* Hover states */
sm:block md:hidden /* Responsive utilities */
```

### Custom CSS Variables
```css
/* Defined in index.css */
--groovlee-bg: hsl(0, 0%, 7%)
--groovlee-green: hsl(141, 76%, 48%)
--groovlee-text: hsl(0, 0%, 100%)
```

## 🐛 Common Issues & Solutions

### Port Already in Use
```bash
# Kill process on port 5000
npx kill-port 5000
# Or change port in server/index.ts
```

### TypeScript Errors
```bash
# Check for type errors
npm run check
# Fix import paths in tsconfig.json
```

### Missing Dependencies
```bash
# Reinstall node_modules
rm -rf node_modules package-lock.json
npm install
```

## 📚 Learning Resources

### React.js
- Official React docs: https://react.dev
- React TypeScript cheatsheet
- Component patterns and best practices

### Node.js/Express
- Express.js guide: https://expressjs.com
- RESTful API design principles
- Middleware concepts

### TypeScript
- TypeScript handbook
- Type definitions and interfaces
- Generic types usage

### Tailwind CSS
- Tailwind documentation
- Responsive design utilities
- Custom component creation

## 🚀 Next Steps for Enhancement

1. **Add Real Audio**
   - Integrate Web Audio API
   - Handle audio file uploads
   - Implement actual playback

2. **Database Integration**
   - Replace in-memory storage
   - Add PostgreSQL/MongoDB
   - Implement data persistence

3. **Authentication**
   - User registration/login
   - JWT token management
   - Protected routes

4. **Testing**
   - Unit tests with Jest
   - Component testing
   - API endpoint testing

5. **Deployment**
   - Production build optimization
   - Environment configuration
   - Cloud deployment (Vercel, Netlify)

---

**Happy Coding!**  
*Ashutosh Anand - Full-Stack Developer*