# Airbnb Clone API Endpoints Documentation

## User Management

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `POST /api/auth/refresh-token` - Refresh authentication token
- `POST /api/auth/forgot-password` - Initiate password reset
- `POST /api/auth/reset-password` - Complete password reset
- `POST /api/auth/verify-email` - Verify user email
- `POST /api/auth/oauth/{provider}` - OAuth authentication (Google, Facebook, etc.)

### User Profile
- `GET /api/users/me` - Get current user profile
- `PUT /api/users/me` - Update user profile
- `GET /api/users/{userId}` - Get public user profile
- `POST /api/users/me/avatar` - Upload profile picture
- `POST /api/users/me/verification` - Submit verification documents
- `GET /api/users/me/verification-status` - Check verification status

## Property Management

### Property Listings
- `POST /api/properties` - Create a new property listing
- `GET /api/properties` - List properties (with filters)
- `GET /api/properties/{propertyId}` - Get property details
- `PUT /api/properties/{propertyId}` - Update property details
- `DELETE /api/properties/{propertyId}` - Remove property listing
- `GET /api/users/{userId}/properties` - Get properties by user

### Property Media
- `POST /api/properties/{propertyId}/images` - Upload property images
- `DELETE /api/properties/{propertyId}/images/{imageId}` - Delete property image
- `PUT /api/properties/{propertyId}/images/reorder` - Reorder property images

### Availability Management
- `GET /api/properties/{propertyId}/availability` - Get property availability
- `PUT /api/properties/{propertyId}/availability` - Update availability
- `POST /api/properties/{propertyId}/blocked-dates` - Block specific dates
- `DELETE /api/properties/{propertyId}/blocked-dates/{dateId}` - Unblock dates

### Pricing Management
- `GET /api/properties/{propertyId}/pricing` - Get property pricing details
- `PUT /api/properties/{propertyId}/pricing` - Update base pricing
- `POST /api/properties/{propertyId}/special-pricing` - Add special pricing for dates
- `DELETE /api/properties/{propertyId}/special-pricing/{pricingId}` - Remove special pricing

## Search & Discovery

### Search
- `GET /api/search` - Search properties with filters
- `GET /api/search/autocomplete` - Location autocomplete
- `GET /api/search/map` - Map-based property search

### Recommendations
- `GET /api/recommendations` - Get personalized recommendations
- `GET /api/recommendations/similar/{propertyId}` - Get similar properties
- `GET /api/trending` - Get trending locations or properties

## Booking System

### Reservations
- `POST /api/bookings` - Create new booking
- `GET /api/bookings` - List user bookings (as guest)
- `GET /api/host/bookings` - List user bookings (as host)
- `GET /api/bookings/{bookingId}` - Get booking details
- `PUT /api/bookings/{bookingId}` - Update booking (dates, guests)
- `DELETE /api/bookings/{bookingId}` - Cancel booking

### Host Management
- `GET /api/host/dashboard` - Host dashboard data
- `PUT /api/host/bookings/{bookingId}/status` - Approve/reject booking
- `POST /api/host/bookings/{bookingId}/message` - Message guest

## Payment System

### Payment Processing
- `POST /api/payments/intent` - Create payment intent
- `POST /api/payments/confirm` - Confirm payment
- `GET /api/payments/methods` - Get user payment methods
- `POST /api/payments/methods` - Add payment method
- `DELETE /api/payments/methods/{paymentMethodId}` - Remove payment method

### Host Payouts
- `GET /api/host/payouts` - Get payout history
- `POST /api/host/payout-methods` - Add payout method
- `GET /api/host/payout-methods` - Get payout methods
- `PUT /api/host/payout-methods/{methodId}/default` - Set default payout method

### Refunds
- `POST /api/bookings/{bookingId}/refund` - Process refund

## Communication System

### Messaging
- `GET /api/conversations` - Get user conversations
- `GET /api/conversations/{conversationId}` - Get conversation details
- `POST /api/conversations` - Start new conversation
- `POST /api/conversations/{conversationId}/messages` - Send message
- `PUT /api/conversations/{conversationId}/read` - Mark conversation as read

## Review & Rating System

### Reviews
- `POST /api/bookings/{bookingId}/reviews` - Create review
- `GET /api/properties/{propertyId}/reviews` - Get property reviews
- `GET /api/users/{userId}/reviews` - Get user reviews
- `POST /api/reviews/{reviewId}/response` - Respond to review

## Analytics & Reporting

### Host Analytics
- `GET /api/host/analytics/bookings` - Get booking statistics
- `GET /api/host/analytics/revenue` - Get revenue reports
- `GET /api/host/analytics/occupancy` - Get occupancy rates

### Financial Reporting
- `GET /api/host/financial/transactions` - Get transaction history
- `GET /api/host/financial/earnings` - Get earnings reports
- `GET /api/host/financial/tax-documents` - Get tax documents

## Security & Preferences

### Account Security
- `POST /api/users/me/two-factor` - Enable/disable two-factor authentication
- `GET /api/users/me/sessions` - List active sessions
- `DELETE /api/users/me/sessions/{sessionId}` - Revoke session

### Preferences
- `GET /api/users/me/preferences` - Get user preferences
- `PUT /api/users/me/preferences` - Update user preferences
- `PUT /api/users/me/notifications` - Update notification settings
