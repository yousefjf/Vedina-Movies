# Vedina Movies Frontend Documentation

## 🎬 Overview

Vedina Movies is a modern, fast, and user-friendly movie streaming platform built with vanilla JavaScript. Experience seamless movie browsing and streaming without any heavyweight frameworks. Visit our [live demo](https://movies.vedina.ir) to see it in action!

## ✨ Features

### 🎯 Core Features

- **No Framework Dependencies**: Built with pure JavaScript for maximum performance
- **AJAX-Powered**: Smooth, no-refresh navigation and interactions
- **Responsive Design**: Perfect viewing experience on all devices
- **Progressive Enhancement**: Works even with JavaScript disabled
- **Offline Support**: Basic functionality available offline
- **Fast Loading**: Optimized assets and lazy loading implementation

### 🎨 User Interface Features

- **Dynamic Movie Grid**: Responsive movie showcase with smooth loading
- **Advanced Search**: Real-time search with filters
  - Genre filtering
  - Year selection
  - Rating-based filtering
  - Language/subtitle options
- **User Dashboard**
  - Watchlist management
  - Viewing history
  - Favorite movies
  - Profile settings
- **Video Player**
  - Custom controls
  - Multiple quality options
  - Subtitle support
  - Playback speed control
- **Blog Section**
  - Movie news and reviews
  - Category-based filtering
  - Search functionality

## 🛠 Technical Stack

- **Vanilla JavaScript**: Core programming
- **HTML5**: Semantic markup
- **CSS3**: Modern styling features
  - CSS Grid
  - Flexbox
  - Custom Properties
  - Animations
- **AJAX**: XMLHttpRequest and Fetch API
- **LocalStorage**: Client-side data persistence
- **Service Workers**: Offline functionality

## 📁 Project Structure

```
frontend/
├── assets/
│   ├── css/
│   │   ├── main.css
│   │   ├── player.css
│   │   └── responsive.css
│   ├── js/
│   │   ├── api.js
│   │   ├── auth.js
│   │   ├── player.js
│   │   └── ui.js
│   └── images/
├── pages/
│   ├── home.html
│   ├── movies.html
│   ├── player.html
│   └── profile.html
└── index.html
```

## 🔒 Security Features

- CSRF Protection
- XSS Prevention
- Content Security Policy
- Secure Session Management
- Input Sanitization

## 📱 Responsive Design

The application is fully responsive with breakpoints at:

- Mobile: 320px - 480px
- Tablet: 481px - 768px
- Desktop: 769px+

Example media query usage:

```css
/* Tablet and up */
@media screen and (min-width: 481px) {
  .movie-grid {
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  }
}
```

## ⚡ Performance Optimizations

- Image lazy loading
- Resource preloading
- Code splitting
- Asset minification
- Browser caching
- Gzip compression

## 🔄 State Management

Custom state management solution using the Observer pattern:

```javascript
class Store {
  constructor() {
    this.state = {};
    this.observers = [];
  }

  subscribe(observer) {
    this.observers.push(observer);
  }

  update(newState) {
    this.state = { ...this.state, ...newState };
    this.observers.forEach((observer) => observer(this.state));
  }
}
```

## 👥 Team

- **Lead Developer**: Yousef Jafari
- **Company**: Vedina Co.

## 📞 Support

For support, email support@vedina.ir or join our Slack channel.

## 🔗 Links

- [Live Demo](https://movies.vedina.ir)
- [API Documentation](./api-readme.md)
- [Company Website](https://vedina.ir)

---

Built with ❤️ by [Yousef Jafari](https://github.com/yousef-jafari) at [Vedina Co.](https://vedina.ir)
