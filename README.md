# 🎫 SupportMCP - AI-Powered Customer Support System

<div align="center">

[![Laravel](https://img.shields.io/badge/Laravel-12.0-FF2D20.svg)](https://laravel.com)
[![Vue.js](https://img.shields.io/badge/Vue.js-3.4-4FC08D.svg)](https://vuejs.org)
[![PHP](https://img.shields.io/badge/PHP-8.2+-777BB4.svg)](https://php.net)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![AI](https://img.shields.io/badge/AI-Gemini-blue.svg)](https://ai.google.dev)

**A modern, intelligent customer support platform combining ticket management with AI-powered chat assistance**

</div>

## 📋 Overview

SupportMCP is a comprehensive customer support solution that seamlessly integrates traditional ticket management with cutting-edge AI technology. Built with Laravel and Vue.js, this system provides businesses with an efficient way to handle customer inquiries through both structured ticket workflows and intelligent AI conversations powered by Google's Gemini AI.

## ✨ Key Features

### 🎯 Ticket Management System
- **Complete CRUD Operations** - Create, read, update, and delete support tickets
- **Ticket Types** - Categorize issues as `bug`, `feature_request`, `question`, or `other`
- **Status Tracking** - Monitor ticket progression through `open`, `assigned`, and `resolved` states
- **Priority Management** - Set and track ticket priority levels
- **Auto-Assignment** - Employees can assign tickets to themselves
- **Resolution Tracking** - Automatic timestamps for `assigned_at` and `resolved_at`
- **System Information** - Capture relevant system details for debugging

### 🤖 AI-Powered Chat Assistant
- **Real-time WebSocket Communication** - Instant messaging between clients and Gemini AI
- **Intelligent Ticket Creation** - AI assists clients in submitting detailed support requests
- **Natural Language Processing** - Clients can describe issues in their own words
- **Automated Triage** - AI categorizes and prioritizes incoming requests
- **Resolution Delivery** - AI communicates final resolutions to clients
- **24/7 Availability** - Round-the-clock support without human intervention

### 👥 Role-Based Access Control
- **Client Role** - Limited access to chat interface and ticket viewing
- **Employee Role** - Full access to ticket management and admin panel
- **Permission-Based Security** - Granular control over system features
- **Secure Authentication** - Built on Laravel Sanctum for API security

## 🛠️ Tech Stack

| Component | Technology | Version |
|-----------|------------|---------|
| **Backend** | Laravel Framework | 12.0 |
| **Frontend** | Vue.js | 3.4 |
| **Build Tool** | Vite | 6.2.6 |
| **Styling** | Tailwind CSS | 3.2.1 |
| **Authentication** | Laravel Breeze & Sanctum | Latest |
| **AI Integration** | Google Gemini AI | Latest |
| **Real-time** | WebSocket | Native |
| **Database** | MySQL/PostgreSQL/SQLite | Any Laravel DB |
| **Permissions** | Spatie Laravel Permission | 6.16 |
| **Testing** | PHPUnit | 11.5.3 |

## 🚀 Quick Start

### Prerequisites
- PHP 8.2 or higher
- Composer
- Node.js and npm
- Database (MySQL, PostgreSQL, or SQLite)
- Google Gemini AI API Key

### Installation

#### 1. Clone the Repository
```bash
git clone https://github.com/imransom29/Customer-Support-Ticketing-Knowledge-Base-System.git
cd Customer-Support-Ticketing-Knowledge-Base-System
```

#### 2. Install Dependencies
```bash
# Install PHP dependencies
composer install

# Install Node.js dependencies
npm install
```

#### 3. Environment Configuration
```bash
# Copy environment file
cp .env.example .env

# Generate application key
php artisan key:generate

# Configure your database and AI API key in .env
```

#### 4. Database Setup
```bash
# Run migrations
php artisan migrate

# Seed database (optional)
php artisan db:seed
```

#### 5. Frontend Build
```bash
# Build assets for development
npm run dev

# Or build for production
npm run build
```

#### 6. Start the Application
```bash
# Start Laravel development server
php artisan serve

# Start queue worker (for background jobs)
php artisan queue:work
```

### Environment Configuration

Add your Google Gemini AI API key to your `.env` file:

```env
GEMINI_API_KEY=your_gemini_api_key_here

# Database configuration
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=supportmcp
DB_USERNAME=your_username
DB_PASSWORD=your_password
```

## 📖 Usage Guide

### For Clients
1. **Access the Chat Interface** - Navigate to the support portal
2. **Create Account** - Register through the chat interface
3. **Start Conversation** - Begin chatting with the AI assistant
4. **Submit Tickets** - Describe your issue and let AI create a ticket
5. **Track Progress** - Monitor ticket status through the chat

### For Employees
1. **Login to Admin Panel** - Access the dashboard with employee credentials
2. **View Ticket Queue** - See all open and assigned tickets
3. **Assign Tickets** - Take ownership of specific issues
4. **Resolve Issues** - Provide solutions and mark tickets as resolved
5. **Communicate** - Send updates to clients through the system

## 🏗️ Architecture

### Backend Structure
```
app/
├── Http/Controllers/          # Request handlers
├── Models/                    # Eloquent models
├── Jobs/                      # Background jobs
├── Listeners/                 # Event listeners
├── Policies/                  # Authorization policies
└── Services/                  # Business logic
```

### Frontend Structure
```
resources/
├── js/
│   ├── Components/           # Vue components
│   ├── Pages/               # Page components
│   └── Layouts/             # Layout templates
└── views/                   # Blade templates
```

### Database Schema
- **Users** - Client and employee accounts
- **Tickets** - Support ticket records
- **Messages** - Chat message history
- **Categories** - Ticket type definitions
- **Permissions** - Role-based access control

## 🔧 Configuration

### AI Settings
Configure Gemini AI behavior in `config/services.php`:

```php
'gemini' => [
    'api_key' => env('GEMINI_API_KEY'),
    'model' => 'gemini-pro',
    'max_tokens' => 1000,
],
```

### WebSocket Configuration
Set up WebSocket broadcasting in `config/broadcasting.php`:

```php
'default' => 'websocket',
'connections' => [
    'websocket' => [
        'driver' => 'websocket',
        'host' => env('WEBSOCKET_HOST', '127.0.0.1'),
        'port' => env('WEBSOCKET_PORT', 6001),
    ],
],
```

## 🧪 Testing

Run the test suite:

```bash
# Run all tests
php artisan test

# Run specific test file
php artisan test tests/Feature/TicketTest.php

# Generate test coverage report
php artisan test --coverage
```

## 🐳 Docker Support

Use Docker for containerized deployment:

```bash
# Build and start containers
docker-compose up -d

# Run migrations in container
docker-compose exec app php artisan migrate

# View logs
docker-compose logs -f
```

## 📊 System Screenshots

### Client Chat Interface
![Client Chat Interface](https://github.com/user-attachments/assets/aca2931f-20a8-433d-92d6-73fd97e5dc4c)

### AI Assistant in Action
![AI Assistant](https://github.com/user-attachments/assets/aaf64c0b-b119-4a49-a6a9-fc7c4d9ea8f5)

### Ticket Creation Flow
![Ticket Creation](https://github.com/user-attachments/assets/8853b988-f347-46d1-80b0-e22e7e732c38)

### Admin Dashboard
![Admin Dashboard](https://github.com/user-attachments/assets/fd7b79a5-a968-446d-93cb-861b74a72426)

### Ticket Management
![Ticket Management](https://github.com/user-attachments/assets/ad0e183a-7787-4152-a7fc-077a02356045)

### Resolution Workflow
![Resolution Workflow](https://github.com/user-attachments/assets/f7733427-d7c4-449a-b9d0-69789b189322)

## 🔒 Security Features

- **API Authentication** - Laravel Sanctum for secure API access
- **Role-Based Permissions** - Granular access control
- **Input Validation** - Comprehensive request validation
- **CSRF Protection** - Cross-site request forgery prevention
- **SQL Injection Prevention** - Eloquent ORM protection
- **XSS Protection** - Output escaping and sanitization

## 🚀 Performance Optimization

- **Database Indexing** - Optimized queries for large datasets
- **Caching Strategy** - Redis-based caching for frequent data
- **Asset Optimization** - Vite build optimization
- **Queue System** - Background job processing
- **Lazy Loading** - Efficient resource loading

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the Repository**
2. **Create Feature Branch** - `git checkout -b feature/amazing-feature`
3. **Commit Changes** - `git commit -m 'Add amazing feature'`
4. **Push to Branch** - `git push origin feature/amazing-feature`
5. **Open Pull Request**

### Development Guidelines
- Follow PSR-12 coding standards
- Write tests for new features
- Update documentation
- Use conventional commits

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Laravel Team** - Excellent PHP framework
- **Vue.js Team** - Progressive JavaScript framework
- **Google AI** - Gemini AI API
- **Tailwind CSS** - Utility-first CSS framework
- **Open Source Community** - Inspiration and support

## 📞 Support

- 📧 **Email**: imransom29@gmail.com
- 🐛 **Issues**: [GitHub Issues](https://github.com/imransom29/Customer-Support-Ticketing-Knowledge-Base-System/issues)
- 💬 **Discussions**: [GitHub Discussions](https://github.com/imransom29/Customer-Support-Ticketing-Knowledge-Base-System/discussions)
- 📖 **Documentation**: [Wiki](https://github.com/imransom29/Customer-Support-Ticketing-Knowledge-Base-System/wiki)

## 🔗 Related Projects

- [Laravel AI Chatbot](https://github.com/imransom29/laravel-ai-chatbot)
- [Vue.js Support Dashboard](https://github.com/imransom29/vue-support-dashboard)
- [AI Helpdesk System](https://github.com/imransom29/ai-helpdesk)

---
