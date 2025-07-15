# VS Code Setup for Groovlee
**Quick Setup Guide by Ashutosh Anand**

## 🚀 Step-by-Step VS Code Setup

### 1. Prerequisites Installation

**Install Node.js:**
```bash
# Download from: https://nodejs.org
# Choose LTS version (v18 or higher)

# Verify installation
node --version
npm --version
```

**Install VS Code:**
- Download from: https://code.visualstudio.com

### 2. Essential VS Code Extensions

Open VS Code Extensions (Ctrl+Shift+X) and install:

```
1. TypeScript and JavaScript Language Features (built-in)
2. ES7+ React/Redux/React-Native snippets
3. Tailwind CSS IntelliSense
4. Auto Rename Tag
5. Bracket Pair Colorizer 2
6. Prettier - Code formatter
7. ESLint
8. GitLens
9. Thunder Client (for API testing)
10. Material Icon Theme
```

### 3. Project Setup Commands

**Open Terminal in VS Code (Ctrl+`):**

```bash
# 1. Navigate to your project folder
cd path/to/groovlee

# 2. Install all dependencies
npm install

# 3. Start development server
npm run dev
```

### 4. VS Code Workspace Settings

Create `.vscode/settings.json`:
```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "typescript.preferences.importModuleSpecifier": "relative",
  "emmet.includeLanguages": {
    "typescript": "html",
    "typescriptreact": "html"
  },
  "tailwindCSS.experimental.classRegex": [
    "class:\\s*[\"']([^\"']*)[\"']",
    "className:\\s*[\"']([^\"']*)[\"']"
  ],
  "files.exclude": {
    "node_modules": true,
    "dist": true,
    ".git": true
  }
}
```

### 5. Debugging Setup

Create `.vscode/launch.json`:
```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Server",
      "type": "node",
      "request": "launch",
      "program": "${workspaceFolder}/server/index.ts",
      "runtimeArgs": ["-r", "tsx/cjs"],
      "env": {
        "NODE_ENV": "development"
      },
      "console": "integratedTerminal"
    }
  ]
}
```

### 6. Useful VS Code Shortcuts

```
Ctrl + `          - Open/close terminal
Ctrl + Shift + P  - Command palette
Ctrl + P          - Quick file search
Ctrl + Shift + F  - Search across files
Ctrl + /          - Comment/uncomment
Alt + Shift + F   - Format document
F12               - Go to definition
Ctrl + Space      - Trigger IntelliSense
```

### 7. Development Workflow

**Daily Development:**
1. Open VS Code
2. Open terminal (Ctrl + `)
3. Run `npm run dev`
4. Open http://localhost:5000
5. Edit files and see changes in real-time

**File Structure Navigation:**
- `client/src/components/` - UI components
- `client/src/pages/` - App pages
- `client/src/hooks/` - Custom React hooks
- `server/` - Backend code
- `shared/` - Common types

### 8. Common VS Code Features for This Project

**Auto-completion:**
- TypeScript provides intelligent code completion
- Tailwind CSS classes auto-complete
- React component props suggestions

**Error Detection:**
- Red squiggly lines show TypeScript errors
- Problems panel (Ctrl+Shift+M) lists all issues
- Hover over errors for quick fixes

**Refactoring:**
- Right-click → Rename Symbol (F2)
- Right-click → Extract to function
- Auto-import missing modules

### 9. Testing Your Setup

**Verify everything works:**
```bash
# 1. Dependencies installed
npm list

# 2. TypeScript compilation
npm run check

# 3. Start development server
npm run dev

# 4. Open browser to localhost:5000
```

**If you see the Groovlee interface, you're ready to code!**

### 10. Troubleshooting

**Port 5000 busy:**
```bash
npx kill-port 5000
# Or change port in server/index.ts
```

**TypeScript errors:**
```bash
# Check all type errors
npm run check
```

**Missing modules:**
```bash
rm -rf node_modules package-lock.json
npm install
```

**VS Code not recognizing TypeScript:**
- Reload VS Code (Ctrl+Shift+P → "Reload Window")
- Check TypeScript version (Ctrl+Shift+P → "TypeScript: Select Version")

---

## 🎯 Ready to Code!

You now have a complete development environment for the Groovlee project. Start editing components in `client/src/components/` and see your changes live!

**Happy coding!**  
*Setup guide by Ashutosh Anand*