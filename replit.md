# Overview

Gr1mAI is a bilingual AI assistant application that provides intelligent chat conversations and image generation capabilities. The system is built as a full-stack web application with a React frontend and Express.js backend, supporting both English and German languages. Users can create accounts, manage chat sessions, and interact with AI services including text completion via Google Gemini and image generation capabilities.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
- **Framework**: React with TypeScript using Vite as the build tool
- **Styling**: Tailwind CSS with shadcn/ui component library and Radix UI primitives
- **State Management**: TanStack Query for server state, React hooks for local state
- **Routing**: Wouter for lightweight client-side routing
- **Internationalization**: react-i18next for German/English language support
- **Animations**: Framer Motion for smooth UI transitions and typewriter effects

## Backend Architecture
- **Framework**: Express.js with TypeScript
- **Authentication**: Passport.js with local strategy and session-based auth
- **Session Management**: Express sessions with PostgreSQL store via connect-pg-simple
- **Security**: Cloudflare Turnstile for bot protection, bcrypt-style password hashing
- **API Design**: RESTful endpoints with JSON responses
- **Development**: Hot reload with Vite integration and custom logging middleware

## Data Storage Solutions
- **Database**: PostgreSQL with Drizzle ORM for type-safe database operations
- **Schema**: Three main entities - users, sessions, and messages with proper relationships
- **Session Storage**: Database-backed session store for authentication persistence
- **Fallback Storage**: Memory-based storage implementation for development/testing
- **Migrations**: Drizzle Kit for database schema management

## Authentication and Authorization
- **Strategy**: Session-based authentication using Passport.js Local Strategy
- **Password Security**: Scrypt-based password hashing with random salts
- **Session Security**: Secure cookies with HTTPS-only in production
- **Bot Protection**: Cloudflare Turnstile integration for registration/login
- **Route Protection**: Custom ProtectedRoute component for authenticated access

## External Dependencies

### AI Services
- **Google Gemini API**: Primary AI service for text completion and image generation via @google/genai SDK
- **Model**: gemini-2.5-flash for text completion with JSON structured responses
- **Image Generation**: Integrated Gemini image generation with aspect ratio and size controls

### Database Services
- **Neon Database**: PostgreSQL hosting via @neondatabase/serverless for production
- **Connection**: SSL-enabled connections with proper timeout and connection pooling

### Security Services
- **Cloudflare Turnstile**: Bot protection service for form submissions
- **Verification**: Server-side token validation against Cloudflare API

### Development Tools
- **Replit Integration**: Custom Vite plugins for Replit environment support
- **Error Handling**: Runtime error modal overlay for development
- **Theme System**: JSON-based theme configuration with shadcn integration

### UI Libraries
- **Radix UI**: Comprehensive set of accessible UI primitives
- **Lucide Icons**: Icon library for consistent visual elements
- **Date Handling**: date-fns for internationalized date formatting
- **Form Validation**: React Hook Form with Zod resolvers for type-safe forms