# Mazad - Online Auction House Platform

A comprehensive full-stack auction house website built with modern technologies, featuring real-time bidding, secure payment processing, and advanced user management.

## 🏗️ Project Overview

Mazad is a sophisticated online auction platform that enables users to buy and sell items through competitive bidding. The platform features real-time updates, secure payment processing, user authentication, and comprehensive admin management.

## 🚀 Features

### Core Auction Features
- **Real-time Bidding**: Live auction updates using SignalR
- **Auction Management**: Create, edit, and manage auctions
- **Bid Tracking**: Real-time bid history and notifications
- **Auction Scheduling**: Automated start/end times with background jobs
- **Multiple Auction States**: Active, upcoming, ended, and completed auctions

### User Management
- **Multi-role System**: Buyers, Sellers, and Admins
- **User Profiles**: Comprehensive user profiles with verification
- **Identity Verification**: National ID upload and verification
- **User Blocking**: Admin controls for user management

### Payment & Transactions
- **Multiple Payment Methods**: PayPal and Stripe integration
- **Secure Transactions**: Encrypted payment processing
- **Balance Management**: User wallet and balance tracking
- **Withdrawal System**: Secure fund withdrawal for sellers

### Communication & Notifications
- **Real-time Chat**: In-app messaging system
- **Push Notifications**: Instant updates for bids and auction events
- **Email Notifications**: Automated email alerts
- **Favorites System**: Save favorite auctions and categories

### Admin Features
- **Dashboard Analytics**: Comprehensive admin dashboard
- **User Management**: User approval, blocking, and monitoring
- **Auction Oversight**: Monitor and manage all auctions
- **Category Management**: Organize items by categories
- **Complaint Handling**: User complaint management system

### Additional Features
- **Image Management**: Cloudinary integration for image storage
- **Search & Filtering**: Advanced search with multiple filters
- **Pagination**: Efficient data loading
- **Review System**: User feedback and ratings
- **Shipment Tracking**: Order fulfillment tracking
- **Event Management**: Special auction events

## 🛠️ Technology Stack

### Backend
- **Framework**: ASP.NET Core 8.0
- **Database**: SQL Server with Entity Framework Core
- **Authentication**: JWT Bearer Tokens with ASP.NET Core Identity
- **Real-time Communication**: SignalR
- **Background Jobs**: Hangfire
- **Payment Processing**: 
  - Stripe.net
  - PayPal API
- **File Storage**: Cloudinary
- **Logging**: Serilog
- **API Documentation**: Swagger/OpenAPI

### Frontend
- **Framework**: Angular 18
- **UI Components**: Angular Material
- **Styling**: Bootstrap 5.3
- **Charts**: CanvasJS, ngx-charts
- **Real-time**: SignalR Client, Socket.io
- **Payment**: Stripe.js
- **Icons**: FontAwesome, Material Design Icons
- **Animations**: AOS (Animate On Scroll)
- **Carousel**: ngx-owl-carousel-o
- **Notifications**: ngx-toastr

### Development Tools
- **Package Manager**: npm (Frontend), NuGet (Backend)
- **Build Tool**: Angular CLI
- **Testing**: Jasmine & Karma
- **Version Control**: Git

## 📁 Project Structure

```
Mazad/
├── Mazad-Backend/                 # Backend API
│   ├── Final/                     # Domain Models
│   │   ├── Models/               # Entity models
│   │   └── Enums/                # Enumerations
│   ├── FinalApi/                 # Web API
│   │   ├── Controllers/          # API Controllers
│   │   ├── Hubs/                 # SignalR Hubs
│   │   ├── Services/             # Business Logic
│   │   └── wwwroot/              # Static files
│   ├── Infrastructure/           # Data Access Layer
│   │   ├── FinalDbContext.cs     # Database Context
│   │   └── Migrations/           # Database Migrations
│   ├── Managers/                 # Business Logic Managers
│   └── ModelView/                # View Models & DTOs
└── Mazad-Frontend/               # Frontend Application
    └── zaid/                     # Angular App
        ├── src/
        │   ├── Action/           # Auction Actions
        │   ├── Admin/            # Admin Dashboard
        │   ├── User/             # User Interface
        │   ├── Shared/           # Shared Components
        │   └── app/              # Core App Files
        └── public/               # Static Assets
```

## 🚀 Getting Started

### Prerequisites
- .NET 8.0 SDK
- SQL Server (Local or Azure)
- Node.js 18+ and npm
- Angular CLI

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Mazad/Mazad-Backend
   ```

2. **Configure Database**
   - Update connection string in `appsettings.json`
   - Run Entity Framework migrations:
   ```bash
   cd FinalApi
   dotnet ef database update
   ```

3. **Configure External Services**
   - Add Cloudinary credentials
   - Configure Stripe API keys
   - Set up PayPal API credentials
   - Configure JWT secret key

4. **Run the Backend**
   ```bash
   cd FinalApi
   dotnet run
   ```

### Frontend Setup

1. **Install Dependencies**
   ```bash
   cd Mazad-Frontend/zaid
   npm install
   ```

2. **Configure Environment**
   - Update API endpoints in `environment.ts`

3. **Run the Frontend**
   ```bash
   ng serve
   ```

## 🔧 Configuration

### Environment Variables
```json
{
  "ConnectionStrings": {
    "LocalConn": "Server=...;Database=MazadDB;..."
  },
  "JwtSettings": {
    "Key": "your-secret-key-here"
  },
  "Cloudinary": {
    "CloudName": "your-cloud-name",
    "ApiKey": "your-api-key",
    "ApiSecret": "your-api-secret"
  },
  "Stripe": {
    "SecretKey": "sk_test_...",
    "PublishableKey": "pk_test_..."
  },
  "PayPal": {
    "ClientId": "your-paypal-client-id",
    "ClientSecret": "your-paypal-client-secret"
  }
}
```

## 📊 API Endpoints

### Authentication
- `POST /api/Account/Login` - User login
- `POST /api/Account/Register` - User registration
- `POST /api/Account/Logout` - User logout

### Auctions
- `GET /api/Auction/GetAuctions` - Get active auctions
- `POST /api/Auction` - Create new auction
- `GET /api/Auction/{id}` - Get auction details
- `PUT /api/Auction/{id}` - Update auction

### Bidding
- `POST /api/Bid` - Place a bid
- `GET /api/Bid/auction/{id}` - Get auction bids

### Payments
- `POST /api/Payment/ProcessPayment` - Process payment
- `GET /api/Payment/UserPayments` - Get user payments

## 🔐 Security Features

- JWT-based authentication
- Role-based authorization
- Input validation and sanitization
- Secure payment processing
- File upload validation
- CORS configuration

## 🧪 Testing

### Backend Testing
```bash
cd Mazad-Backend/FinalApi
dotnet test
```

### Frontend Testing
```bash
cd Mazad-Frontend/zaid
ng test
```

## 📈 Performance Features

- **Caching**: Memory cache for frequently accessed data
- **Pagination**: Efficient data loading
- **Lazy Loading**: Entity Framework lazy loading
- **Background Jobs**: Hangfire for scheduled tasks
- **Real-time Updates**: SignalR for live updates

## 🚀 Deployment

### Backend Deployment
1. Build the application:
   ```bash
   dotnet publish -c Release
   ```
2. Deploy to Azure App Service or IIS

### Frontend Deployment
1. Build for production:
   ```bash
   ng build --configuration production
   ```
2. Deploy to Azure Static Web Apps or any web server

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Team

- **Backend Development**: ASP.NET Core team
- **Frontend Development**: Angular team
- **Database Design**: SQL Server team
- **UI/UX Design**: Design team

## 📞 Support

For support and questions:
- Create an issue in the repository
- Contact the development team
- Check the documentation

## 🔄 Version History

- **v1.0.0** - Initial release with core auction functionality
- **v1.1.0** - Added real-time bidding and chat features
- **v1.2.0** - Enhanced payment processing and admin dashboard
- **v1.3.0** - Added shipment tracking and review system

---

**Mazad** - Where bidding meets innovation! 🏆 