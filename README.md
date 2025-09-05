# Express Starter Template

A modern, production-ready Express.js starter template with TypeScript, authentication, and database integration.

## 🚀 Tech Stack

### Core Framework
- **Express.js 5** - Fast, unopinionated web framework for Node.js
- **TypeScript** - Type-safe JavaScript with modern ES features
- **Node.js** - JavaScript runtime environment

### Database & ORM
- **PostgreSQL** - Robust relational database
- **Drizzle ORM** - Type-safe SQL toolkit and query builder
- **Drizzle Kit** - Database migrations and schema management

### Authentication
- **Better Auth** - Modern authentication library with built-in security features
- Email verification support
- Social provider integration ready (Google, etc.)
- Session management with database persistence

### Development Tools
- **pnpm** - Fast, disk space efficient package manager
- **Nodemon** - Auto-restart development server
- **ESLint** - Code linting with TypeScript support
- **ts-node** - TypeScript execution environment
- **CORS** - Cross-origin resource sharing middleware

## 📁 Project Structure

```
src/
├── config/           # Environment and app configuration
├── controllers/       # Request handlers (empty - ready for your logic)
├── data/             # Database related files
│   ├── db.ts         # Database connection
│   └── schema/       # Drizzle schema definitions
├── lib/              # Utility libraries
│   └── auth.ts       # Better Auth configuration
├── routes/           # API route definitions
│   ├── better-auth/  # Authentication endpoints
│   └── me/           # User profile endpoints
├── services/         # Business logic layer (empty - ready for your services)
├── types/            # TypeScript type definitions
├── index.ts          # Application entry point
└── server.ts         # Express server setup
```

## 🛠️ Configuration Features

### Path Aliases
Configured TypeScript path aliases for clean imports:
- `@/*` - Root src directory
- `@data/*` - Database and data layer
- `@lib/*` - Utility libraries
- `@schema/*` - Database schema files
- `@routes/*` - API routes
- `@config/*` - Configuration files
- `@services/*` - Business logic services
- `@types/*` - Type definitions
- `@middleware/*` - Express middleware

### Database Schema
Pre-configured database tables:
- **Users** - User accounts with roles and status
- **Sessions** - Authentication sessions
- **Accounts** - OAuth provider accounts
- **Verifications** - Email verification tokens

### Custom ESLint Rules
- Custom rule to enforce `@schema/*` imports for schema files
- TypeScript ESLint integration
- Automatic code formatting and linting

## 🚦 Getting Started

### Prerequisites
- Node.js (v18 or higher)
- pnpm (recommended) or npm
- PostgreSQL database

### Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd express-starter-template
   ```

2. **Install dependencies**
   ```bash
   pnpm install
   ```

3. **Environment setup**
   ```bash
   cp .env.example .env
   ```
   
   Fill in your environment variables:
   ```env
   PORT=3000
   CLIENT_URL=http://localhost:5173
   DATABASE_URL=postgresql://username:password@localhost:5432/database
   BETTER_AUTH_SECRET=your-secret-key
   BETTER_AUTH_URL=http://localhost:3000
   ```

4. **Database setup**
   ```bash
   # Generate migration files
   pnpm db:generate
   
   # Run migrations
   pnpm db:migrate
   
   # Open Drizzle Studio (optional)
   pnpm db:studio
   ```

5. **Start development server**
   ```bash
   pnpm dev
   ```

## 📜 Available Scripts

- `pnpm dev` - Start development server with hot reload
- `pnpm build` - Build for production
- `pnpm start` - Start production server
- `pnpm db:generate` - Generate database migrations
- `pnpm db:migrate` - Run database migrations
- `pnpm db:studio` - Open Drizzle Studio
- `pnpm lint` - Run ESLint
- `pnpm lint:fix` - Fix ESLint issues automatically

## 🔐 Authentication Endpoints

The template includes pre-configured authentication routes:

- `POST /api/auth/sign-up` - User registration
- `POST /api/auth/sign-in` - User login
- `POST /api/auth/sign-out` - User logout
- `GET /api/me` - Get current user session

## 🏗️ Built-in Features

- ✅ Type-safe database operations with Drizzle ORM
- ✅ Secure authentication with Better Auth
- ✅ CORS configuration for frontend integration
- ✅ Environment-based configuration
- ✅ Database migrations and schema management
- ✅ Development hot reload with Nodemon
- ✅ Code linting and formatting
- ✅ Path aliases for clean imports
- ✅ Production-ready build process

## 🔧 Customization

### Adding New Routes
1. Create route files in `src/routes/`
2. Import and use in `src/server.ts`

### Database Schema Changes
1. Modify schema files in `src/data/schema/`
2. Run `pnpm db:generate` to create migrations
3. Run `pnpm db:migrate` to apply changes

### Social Authentication
Uncomment and configure social providers in `src/lib/auth.ts`:
```typescript
socialProviders: {
  google: {
    clientId: process.env.GOOGLE_CLIENT_ID,
    clientSecret: process.env.GOOGLE_CLIENT_SECRET,
  },
},
```

## 📝 License

ISC License - feel free to use this template for your projects!

---

**Ready to build something amazing? Start coding! 🚀**