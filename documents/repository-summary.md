# Shopizer Shop ReactJS - Repository Summary

## Overview
Shopizer Shop ReactJS is an e-commerce frontend application built with React 16.6.0. It serves as the storefront interface for the Shopizer e-commerce platform, providing a complete shopping experience with product browsing, cart management, checkout, and user account features.

**Version:** 3.0.0  
**Node Version:** v16.13.0 (tested)  
**License:** Apache 2.0

## Technology Stack

### Core Framework
- **React** 16.6.0 with React DOM
- **React Router DOM** 5.1.2 for navigation
- **Redux** 4.0.4 with React-Redux 7.1.3 for state management
- **Redux Thunk** for async actions
- **Bootstrap** 4.5.0 with React-Bootstrap 1.0.1

### Key Libraries
- **Axios** 0.21.1 - HTTP client for API calls
- **Stripe Integration** - Payment processing (@stripe/react-stripe-js, @stripe/stripe-js)
- **Google Maps React** - Location and mapping features
- **Swiper** - Product carousels and sliders
- **React Hook Form** - Form validation and management
- **Moment.js** - Date/time handling
- **Universal Cookie** - Cookie management

### UI/UX Libraries
- animate.css, react-spinners, react-toast-notifications
- react-star-ratings, react-modal-video, react-lightgallery
- react-countdown-now, react-countup, react-paginate

## Project Structure

```
shopizer-shop-reactjs/
├── public/                    # Static assets and HTML template
│   ├── assets/               # Images and static resources
│   ├── env-config.js         # Environment configuration
│   └── index.html            # Main HTML template
├── src/
│   ├── assets/               # Fonts, CSS, SCSS
│   │   ├── css/
│   │   ├── scss/             # Sass stylesheets (34 files)
│   │   └── fonts/            # Custom fonts
│   ├── components/           # Reusable React components
│   │   ├── header/           # Header components
│   │   ├── footer/           # Footer components
│   │   ├── product/          # Product-related components (15 subdirs)
│   │   ├── hero-slider/      # Homepage slider
│   │   ├── feature-icon/     # Feature icons
│   │   ├── promos/           # Promotional components
│   │   ├── newsletter/       # Newsletter subscription
│   │   ├── section-title/    # Section titles
│   │   ├── contact/          # Contact form
│   │   ├── consent/          # Cookie consent
│   │   └── loader/           # Loading indicators
│   ├── wrappers/             # Component wrappers
│   │   ├── header/
│   │   ├── footer/
│   │   ├── product/          # Product wrappers (11 subdirs)
│   │   ├── hero-slider/
│   │   ├── feature-icon/
│   │   ├── promos/
│   │   ├── breadcrumb/
│   │   └── newsletter/
│   ├── pages/                # Page components
│   │   ├── home/             # Homepage
│   │   ├── category/         # Category listing
│   │   ├── product-details/  # Product detail page
│   │   ├── search-product/   # Search results
│   │   ├── content/          # CMS content pages
│   │   └── other/            # Other pages
│   │       ├── Cart.js
│   │       ├── Checkout.js
│   │       ├── LoginRegister.js
│   │       ├── MyAccount.js
│   │       ├── OrderConfirm.js
│   │       ├── OrderDetails.js
│   │       ├── RecentOrder.js
│   │       ├── Contact.js
│   │       ├── ForgotPassword.js
│   │       ├── ResetPassword.js
│   │       └── NotFound.js
│   ├── redux/                # State management
│   │   ├── actions/          # Redux actions (8 files)
│   │   └── reducers/         # Redux reducers (9 files)
│   ├── helpers/              # Helper utilities
│   │   ├── product.js        # Product utilities
│   │   └── scroll-top.js     # Scroll utilities
│   ├── util/                 # Utility functions
│   │   ├── constant.js       # Constants
│   │   ├── webService.js     # API service layer
│   │   └── helper.js         # General helpers
│   ├── translations/         # Internationalization
│   │   ├── english.json
│   │   └── french.json
│   ├── data/                 # Static data
│   │   ├── hero-sliders/
│   │   └── feature-icons/
│   ├── layouts/              # Layout components
│   │   └── Layout.js
│   ├── App.js                # Main application component
│   └── index.js              # Application entry point
├── conf/                     # Nginx configuration
│   └── conf.d/
│       ├── default.conf
│       └── gzip.conf
├── .circleci/                # CI/CD configuration
│   └── config.yml
├── Dockerfile                # Docker container configuration
├── env.sh                    # Environment setup script
├── package.json              # Dependencies and scripts
└── README.md                 # Project documentation
```

## Key Features

### E-commerce Functionality
- **Product Catalog**: Browse products by category with filtering and sorting
- **Product Details**: Detailed product pages with images, descriptions, variants
- **Shopping Cart**: Add/remove items, update quantities
- **Checkout Process**: Multi-step checkout with address and payment
- **Payment Integration**: Stripe payment processing
- **Order Management**: Order confirmation, order history, order details

### User Features
- **Authentication**: Login, registration, password reset
- **User Account**: Profile management, address book, order history
- **Wishlist**: Save favorite products
- **Product Reviews**: Star ratings and reviews
- **Product Search**: Search functionality with results page

### UI/UX Features
- **Responsive Design**: Mobile-friendly Bootstrap layout
- **Hero Sliders**: Homepage promotional sliders
- **Product Carousels**: Featured and related products
- **Image Galleries**: Product image lightbox
- **Animations**: CSS animations for enhanced UX
- **Loading States**: Spinners and loading indicators
- **Toast Notifications**: User feedback messages
- **Cookie Consent**: GDPR-compliant cookie banner
- **Newsletter**: Email subscription
- **Contact Form**: Customer support contact

### Internationalization
- Multi-language support (English, French)
- Redux-multilanguage integration

### Maps Integration
- Google Maps for store locations
- React Geocode for address lookup

## Configuration

### Environment Configuration
Configuration is managed through `public/env-config.js`:
- `APP_MERCHANT`: Merchant identifier (default: "DEFAULT")
- `APP_BASE_URL`: Backend API URL (default: http://localhost:8080)
- `APP_THEME_COLOR`: Theme color customization

### Backend Integration
The application connects to a Shopizer backend API for:
- Product catalog data
- User authentication
- Order processing
- Content management

## Available Scripts

```bash
# Install dependencies
npm i
# or if it fails
npm install --legacy-peer-deps

# Development server (port 3000)
npm run dev

# Production build
npm run build

# Run tests
npm test

# Integration mode
npm run intergartion
```

## Docker Support

### Build Docker Image
```bash
docker build . -t shopizerecomm/shopizer-shop:latest
```

### Run Container
```bash
docker run \
  -e "APP_MERCHANT=DEFAULT" \
  -e "APP_BASE_URL=http://localhost:8080" \
  -it --rm -p 80:80 shopizerecomm/shopizer-shop-reactjs
```

Access at: http://localhost

## State Management

Redux store manages:
- Product catalog and filters
- Shopping cart state
- User authentication
- Wishlist items
- UI state (modals, notifications)
- Language preferences

Redux middleware:
- redux-thunk for async operations
- redux-localstorage-simple for persistence
- redux-devtools-extension for debugging

## Styling

- **SCSS**: 34 SCSS files for modular styling
- **Bootstrap 4.5.0**: Grid system and components
- **Custom Fonts**: 12 font files included
- **Animate.css**: Pre-built animations
- **Responsive**: Mobile-first design approach

## Browser Support

### Production
- >0.2% market share
- Not dead browsers
- Not Opera Mini
- IE 11 support

### Development
- Latest Chrome, Firefox, Safari
- IE 11

## CI/CD

CircleCI configuration included for automated:
- Build processes
- Testing
- Deployment pipelines

## Dependencies Summary

**Total Dependencies**: 40+ production dependencies  
**Dev Dependencies**: 2 (redux-devtools-extension, sass)

Key dependency categories:
- React ecosystem (core, router, hooks)
- Redux state management
- UI components (Bootstrap, Swiper, modals)
- Payment processing (Stripe)
- Maps and location (Google Maps)
- Forms and validation
- Utilities (moment, axios, cookies)

## Development Notes

- Built with Create React App
- Uses legacy peer dependencies (may require `--legacy-peer-deps` flag)
- Tested with Node v16.13.0
- Includes service worker for PWA capabilities
- Polyfills included for IE11 support

## Integration Points

1. **Shopizer Backend API**: RESTful API for all e-commerce operations
2. **Stripe**: Payment processing
3. **Google Maps**: Location services
4. **CDN**: Static assets can be served via CDN

## Security Considerations

- SHA-512 hashing (js-sha512)
- Secure cookie handling
- Environment-based configuration
- HTTPS recommended for production

## Performance Features

- Code splitting via React Router
- Lazy loading of images
- Redux state persistence
- Gzip compression (nginx config)
- Service worker caching
- Optimized production builds

---

**Last Updated**: March 11, 2026  
**Repository**: shopizer-shop-reactjs  
**Maintainer**: Shopizer E-commerce
