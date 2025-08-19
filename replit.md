# CryptoSecure Exchange

## Overview

CryptoSecure Exchange is a full-stack web application that provides a secure cryptocurrency trading platform with robust authentication features and comprehensive trading dashboard. The application implements a two-factor authentication (2FA) system using OTP codes and offers a professional trading interface with real-time cryptocurrency charts, portfolio management, and multi-currency trading capabilities. Built with React and Express, it emphasizes security best practices with session management and encrypted communications.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
The client-side application is built using React with TypeScript and follows a component-based architecture:

- **UI Framework**: React 18 with TypeScript for type safety and modern development patterns
- **Styling**: Tailwind CSS with a custom design system based on shadcn/ui components for consistent styling
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: React Query (TanStack Query) for server state management and caching
- **Form Handling**: React Hook Form with Zod validation for type-safe form management
- **Component Library**: Comprehensive UI component system using Radix UI primitives
- **Data Visualization**: Recharts library for cryptocurrency charts and trading visualizations
- **Dashboard Features**: Professional trading interface with real-time charts, portfolio management, and multi-currency support

### Backend Architecture
The server-side follows a RESTful API design pattern:

- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript for full-stack type safety
- **Database ORM**: Drizzle ORM with PostgreSQL dialect for database operations
- **Session Management**: Custom session handling with token-based authentication
- **Authentication Flow**: Multi-step authentication with username/password + OTP verification

### Database Design
The application uses a PostgreSQL database with three main entities:

- **Users Table**: Stores user credentials and profile information with unique constraints on username and email
- **Sessions Table**: Manages user sessions with token-based authentication and expiration tracking
- **OTP Codes Table**: Handles two-factor authentication codes with time-based expiration and usage tracking

The database schema implements proper foreign key relationships and includes automatic UUID generation for primary keys.

### Authentication & Security
The application implements a comprehensive security model:

- **Two-Factor Authentication**: Required OTP verification via email after initial login
- **Session Management**: Token-based sessions with configurable expiration (24 hours default, 7 days for "remember me")
- **Password Security**: Currently uses plain text storage (noted for production enhancement)
- **Data Validation**: Comprehensive input validation using Zod schemas on both client and server

### Development Architecture
The project follows a monorepo structure with shared code:

- **Shared Schema**: Common TypeScript types and Zod validation schemas shared between client and server
- **Development Tools**: Vite for fast development builds with HMR support
- **Type Safety**: Full TypeScript coverage across the entire stack
- **Build System**: Separate build processes for client (Vite) and server (esbuild)

## External Dependencies

### Database & ORM
- **Neon Database**: Serverless PostgreSQL database hosting (@neondatabase/serverless)
- **Drizzle ORM**: Modern TypeScript ORM for database operations with PostgreSQL dialect
- **Drizzle Kit**: Database migration and schema management tooling

### Frontend Libraries
- **React Ecosystem**: React 18 with TypeScript support
- **UI Components**: Radix UI primitives for accessible component foundations
- **Form Management**: React Hook Form with Hookform Resolvers for validation integration
- **Data Fetching**: TanStack React Query for server state management
- **Styling**: Tailwind CSS with Class Variance Authority for component variants
- **Icons**: Lucide React for consistent iconography
- **Date Handling**: date-fns for date manipulation and formatting

### Backend Dependencies
- **Express.js**: Web framework for Node.js with middleware support
- **Session Storage**: connect-pg-simple for PostgreSQL session storage
- **Development Tools**: tsx for TypeScript execution and nodemon-like functionality
- **Build Tools**: esbuild for fast server bundling

### Development & Build Tools
- **Vite**: Frontend build tool with React plugin and development server
- **TypeScript**: Language and compiler for type safety
- **ESLint & Prettier**: Code quality and formatting tools (inferred from typical setup)
- **PostCSS**: CSS processing with Tailwind CSS integration

### Authentication & Validation
- **Zod**: Runtime type validation and schema definition
- **Crypto Module**: Node.js built-in crypto for UUID generation and security operations
- **Drizzle-Zod**: Integration between Drizzle ORM and Zod for database schema validation

The application is designed to be deployed on platforms that support Node.js applications with PostgreSQL databases, with environment variable configuration for database connections and other runtime settings.