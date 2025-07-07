# TurfBook Pro - Sports Facility Booking System

## Overview

TurfBook Pro is a modern web application for booking sports facilities, designed specifically for turf and sports venue management. The application provides a comprehensive booking system where customers can view available time slots, make reservations, and administrators can manage facilities and bookings.

## System Architecture

The application follows a modern full-stack architecture with clear separation between frontend and backend:

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **Styling**: Tailwind CSS with custom sports-themed design system
- **UI Components**: Radix UI primitives with shadcn/ui component library
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Session Storage**: PostgreSQL-based session storage with connect-pg-simple
- **API**: RESTful API design with JSON responses

## Key Components

### Database Schema
The application uses a well-structured PostgreSQL schema with the following main entities:

1. **Facilities**: Sports venues with pricing, types (premium/standard), and availability status
2. **Time Slots**: Bookable time periods for each facility with date/time and availability tracking
3. **Bookings**: Customer reservations with contact details, payment status, and booking status
4. **Users**: System users with role-based access (admin/user)

### Core Features
- **Facility Management**: CRUD operations for sports facilities
- **Time Slot Management**: Dynamic time slot creation and availability tracking
- **Booking System**: Customer booking with form validation and confirmation
- **Admin Dashboard**: Booking management and status updates
- **Responsive Design**: Mobile-first approach with Tailwind CSS

### API Endpoints
- `GET /api/facilities` - List all facilities
- `GET /api/facilities/:id` - Get facility details
- `POST /api/facilities` - Create new facility (admin)
- `GET /api/timeslots` - Get available time slots by date
- `POST /api/bookings` - Create new booking
- `GET /api/bookings` - List all bookings (admin)
- `PATCH /api/bookings/:id/status` - Update booking status (admin)

## Data Flow

1. **Customer Journey**:
   - Browse available facilities on the home page
   - Select a date to view time slots
   - Choose an available time slot
   - Fill out booking form with validation
   - Submit booking and receive confirmation

2. **Admin Workflow**:
   - Access admin dashboard to view all bookings
   - Update booking statuses (confirmed/cancelled)
   - Manage facility information
   - Monitor time slot availability

3. **Data Persistence**:
   - All data stored in PostgreSQL via Drizzle ORM
   - Real-time updates through TanStack Query cache invalidation
   - Optimistic updates for better user experience

## External Dependencies

### Database & Infrastructure
- **Neon Database**: Serverless PostgreSQL hosting
- **Drizzle ORM**: Type-safe database operations
- **Drizzle Kit**: Database migrations and schema management

### Frontend Libraries
- **React Ecosystem**: React, React DOM, React Hook Form
- **UI & Styling**: Radix UI, Tailwind CSS, class-variance-authority
- **State Management**: TanStack Query for server state
- **Validation**: Zod for schema validation
- **Utilities**: date-fns, clsx, nanoid

### Backend Dependencies
- **Express.js**: Web framework
- **Session Management**: express-session with connect-pg-simple
- **Development**: tsx for TypeScript execution, esbuild for production builds

## Deployment Strategy

### Development
- **Local Development**: `npm run dev` starts both frontend (Vite) and backend (Express)
- **Hot Reload**: Vite HMR for frontend, tsx watch mode for backend
- **Database**: `npm run db:push` to sync schema changes

### Production Build
- **Frontend**: Vite builds optimized static assets to `dist/public`
- **Backend**: esbuild compiles TypeScript to ES modules in `dist/`
- **Deployment**: Single build command creates both frontend and backend artifacts
- **Environment**: Requires `DATABASE_URL` environment variable

### Architecture Decisions

1. **Monorepo Structure**: Shared schema between frontend and backend eliminates type duplication
2. **TypeScript First**: Full type safety across the stack with shared interfaces
3. **Serverless Database**: Neon provides auto-scaling PostgreSQL without infrastructure management
4. **Component Library**: shadcn/ui provides consistent, accessible UI components
5. **Query Caching**: TanStack Query reduces API calls and improves performance
6. **Form Validation**: Zod schemas ensure data integrity on both client and server

## Advanced Features Implemented

### Real-time Features
- **WebSocket Integration**: Live updates for booking changes and slot availability
- **Live Dashboard**: Real-time booking status updates across all connected clients
- **Instant Notifications**: Immediate feedback when bookings are created or cancelled

### Admin Management System
- **Secure Authentication**: JWT-based admin login with session management
- **Advanced Analytics**: Revenue tracking, conversion rates, peak hour analysis
- **Booking Calendar**: Visual calendar showing booking density by date
- **Search & Filter**: Advanced filtering by status, date range, customer details
- **Data Export**: CSV export and automated report generation
- **Facility Management**: Create, edit, and manage multiple facilities

### WhatsApp Integration
- **Booking Confirmations**: Automatic WhatsApp notifications with booking details
- **Payment Info**: UPI details (9360429797@ptsbi) included in confirmations
- **Contact Integration**: Business contact (9360429797) for customer support

### Enhanced User Experience
- **Time Slot Grid**: 6 AM to midnight availability (18 time slots per day)
- **Pricing Display**: ₹600 per hour pricing throughout the system
- **Mobile Responsive**: Optimized for all device sizes
- **Professional Design**: Sports-themed green color scheme

### Business Features
- **Payment Integration Ready**: Structure prepared for UPI/payment gateway
- **Revenue Analytics**: Comprehensive financial tracking and reporting
- **Bulk Operations**: Bulk time slot creation for multiple days
- **Email Integration**: Automated email summary functionality

## Changelog

- July 07, 2025: Advanced TurfCourt booking system completed
  - **PostgreSQL Database Integration**: Migrated from in-memory to persistent database storage
  - **Database Seeding**: Automatic initialization with sample facilities and time slots
  - Real-time WebSocket updates with database persistence
  - Admin authentication and management with session storage
  - WhatsApp notification system
  - Analytics dashboard with export features
  - Facility management system with CRUD operations
  - Complete pricing update to ₹600/hour (6 AM to midnight, 18 slots/day)
  - Contact integration (9360429797, 9360429797@ptsbi)
  - Drizzle ORM integration with type-safe database operations

## User Preferences

Preferred communication style: Simple, everyday language.