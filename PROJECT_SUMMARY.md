# SWP Project No Smoking - Backend API

## Project Summary

SWP Project No Smoking is a comprehensive smoking cessation support platform built as a backend REST API service. The application serves as a digital ecosystem designed to help smokers quit their habit through structured quit plans, professional coach guidance, community support, and progress tracking.

### Core Concept
The platform connects smoking cessation seekers (Members) with professional coaches who guide them through personalized quit plans. The system provides comprehensive tracking, gamification through badges, community features through blogs, and payment integration for premium memberships.

## Technologies & Frameworks

### Core Framework & Platform
- **Spring Boot 3.5.0** - Main application framework
- **Java 17** - Programming language
- **Maven** - Build management and dependency resolution

### Database & Persistence
- **Microsoft SQL Server** - Primary database
- **Spring Data JPA** - Data access layer
- **Hibernate** - ORM framework with automatic DDL updates

### Security & Authentication
- **Spring Security** - Security framework
- **OAuth 2.0 Resource Server** - OAuth integration
- **JWT (JSON Web Tokens)** - Authentication tokens using Nimbus JOSE JWT
- **Google OAuth Integration** - Social login functionality
- **Password Encryption** - Using Spring Security Crypto

### API & Documentation
- **Spring Web MVC** - REST API framework
- **SpringDoc OpenAPI 3** - API documentation and Swagger UI
- **Bean Validation** - Request/response validation

### Communication & Real-time Features
- **WebSocket** - Real-time messaging system
- **Spring Mail** - Email functionality for notifications and password resets
- **SMTP Gmail Integration** - Email service provider

### Payment Integration
- **VNPay** - Vietnamese payment gateway for membership subscriptions

### Development & Productivity Tools
- **Lombok** - Code generation for boilerplate reduction
- **MapStruct** - Object mapping between DTOs and entities
- **Spring Boot DevTools** - Development productivity

### Task Management
- **Spring Scheduling** - Automated tasks and cron jobs

## System Architecture & Responsibilities

### 1. User Management System
**Components:** `User`, `AuthenticationController`, `UserService`, `AuthenticationService`

**Responsibilities:**
- User registration and authentication
- Role-based access control (Member, Coach, Admin)
- JWT token management and refresh
- User profile management
- Account status management (Active, Inactive, Banned)

### 2. Member Management System  
**Components:** `Member`, `MemberService`, `MemberInitialInfo`, `MemberBadge`

**Responsibilities:**
- Member profile creation and management
- Initial smoking assessment and data collection
- Member demographics and personal information
- Achievement tracking through badges
- Member-specific functionality and preferences

### 3. Coach Management System
**Components:** `Coach`, `CoachService`, `CoachDashboard`, `CoachReview`

**Responsibilities:**
- Coach profile and credentials management
- Specialization and experience tracking
- Coach capacity management (max members)
- Performance metrics and rating system
- Coach dashboard with member overview

### 4. Quit Plan Management System
**Components:** `QuitPlan`, `QuitPlanStage`, `QuitPlanService`, `SmokingLog`

**Responsibilities:**
- Personalized quit plan creation
- Multi-stage quit plan progression
- Progress tracking and monitoring
- Smoking behavior logging and analytics
- Goal setting and achievement tracking
- Health status monitoring

### 5. Coach-Member Relationship System
**Components:** `MemberCoachSelection`, `CoachMemberService`

**Responsibilities:**
- Coach selection and assignment process
- Member-coach pairing algorithms
- Relationship management
- Communication facilitation
- Progress review and feedback

### 6. Progress Tracking & Analytics System
**Components:** `SmokingLog`, `SmokingLogService`, `DashboardService`

**Responsibilities:**
- Daily/weekly smoking behavior logging
- Craving level tracking (Low, Medium, High)
- Health status updates
- Statistical analysis and reporting
- Progress visualization data

### 7. Gamification System
**Components:** `Badge`, `MemberBadge`, `BadgeService`

**Responsibilities:**
- Achievement badge definitions
- Badge awarding logic
- Member progress recognition
- Motivation through achievements
- Badge display and management

### 8. Content Management System
**Components:** `BlogPost`, `BlogCategory`, `BlogService`

**Responsibilities:**
- Educational content creation
- Blog post management
- Content categorization
- Community knowledge sharing
- Content moderation

### 9. Membership & Payment System
**Components:** `MembershipPackage`, `UserMembership`, `PaymentService`, `VNPayService`

**Responsibilities:**
- Subscription plan management
- Payment processing integration
- Membership tier management
- Billing and subscription tracking
- Payment gateway integration (VNPay)

### 10. Communication System
**Components:** `Message`, `MessageWebSocketController`, `NotificationService`

**Responsibilities:**
- Real-time messaging between members and coaches
- System notification management
- Email communication for important updates
- WebSocket-based real-time features

### 11. Revenue Management System
**Components:** `RevenueController`, `RevenueService`

**Responsibilities:**
- Financial analytics and reporting
- Revenue tracking from memberships
- Payment analytics
- Financial dashboard data

### 12. Security & Configuration
**Components:** `SecurityConfig`, `CorsConfig`, `WebSocketConfig`

**Responsibilities:**
- API security configuration
- CORS policy management
- WebSocket security
- OAuth integration setup
- JWT configuration management

## API Structure & Conventions

The project follows RESTful API conventions with the following patterns:

### Endpoint Structure
- Base URL pattern: `/api/{resource}`
- Hierarchical relationships using forward slashes
- Lowercase with hyphens for multi-word resources
- Plural nouns for collections

### Authentication Endpoints
- `POST /api/auth/login` - User authentication
- `POST /api/auth/register` - User registration  
- `POST /api/auth/refresh-token` - Token refresh

### Resource Management
- Standard CRUD operations following REST principles
- Query parameters for filtering and pagination
- Consistent response format using `ResponseObject<T>`

## Key Features

1. **Personalized Quit Plans** - Customized smoking cessation programs
2. **Professional Coaching** - Expert guidance and support
3. **Progress Tracking** - Comprehensive logging and analytics
4. **Gamification** - Achievement system with badges
5. **Community Features** - Blog and knowledge sharing
6. **Real-time Communication** - WebSocket-based messaging
7. **Payment Integration** - Subscription management with VNPay
8. **Mobile-Ready API** - RESTful design for mobile applications
9. **Security** - Comprehensive authentication and authorization
10. **Scheduling** - Automated tasks and reminders

## Database Schema

The system uses Microsoft SQL Server with JPA entities representing:
- User hierarchy (User -> Member/Coach)
- Quit plan progression system
- Logging and tracking tables
- Membership and payment records
- Communication and notification tables

## Development Features

- **Hot Reload** - Development productivity tools
- **API Documentation** - Swagger UI integration
- **Email Integration** - SMTP support for notifications
- **Scheduling** - Automated background tasks
- **Object Mapping** - Automatic DTO-Entity conversion
- **Validation** - Request/response validation
- **Error Handling** - Centralized exception management

This platform represents a comprehensive solution for smoking cessation support, combining behavioral tracking, professional guidance, community support, and gamification to help users successfully quit smoking.