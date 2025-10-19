# 🚀 TeraBox Web - Professional File Downloader

![TeraBox Web](https://img.shields.io/badge/TeraBox-Web-blue?style=for-the-badge&logo=download&logoColor=white)
![Version](https://img.shields.io/badge/version-2.0.1-green?style=for-the-badge)
![React](https://img.shields.io/badge/React-18.0-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.0-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Netlify](https://img.shields.io/badge/Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)

> **Fast, secure, and reliable file downloads from TeraBox with no limits.**

A modern, responsive web application that allows users to download files from TeraBox with direct download links and proxy support. Built with React 18, TypeScript, and Tailwind CSS, deployed on Netlify with serverless functions. Features a beautiful glassmorphism UI, dark/light mode, and comprehensive API documentation.

**Version 2.0.1** - Enhanced performance, improved UI/UX, and better error handling.

## ✨ Features

### 🎯 Core Features
- **🔗 Direct Downloads**: Get direct download links from TeraBox URLs
- **🛡️ Proxy Support**: External proxy integration for faster downloads
- **🌙 Dark/Light Mode**: Beautiful theme switching with system preference detection
- **📱 Mobile Responsive**: Optimized for all devices and screen sizes
- **⚡ Fast & Reliable**: Serverless architecture for optimal performance
- **🍪 Cookie Management**: Easy NDUS cookie setup with detailed guide

### 🎨 Design & UX
- **Modern UI/UX**: Clean, professional interface with smooth animations
- **Glassmorphism Effects**: Beautiful backdrop blur and transparency effects
- **Responsive Design**: Mobile-first approach with perfect scaling
- **Accessibility**: ARIA labels, keyboard navigation, and screen reader support
- **Loading States**: Elegant loading animations and error handling

### 🔧 Technical Features
- **REST API**: Full-featured API with comprehensive documentation
- **CORS Handling**: Serverless functions to bypass browser limitations
- **Error Handling**: Robust error management with user-friendly messages
- **Type Safety**: Full TypeScript implementation
- **SEO Optimized**: Meta tags, Open Graph, and mobile optimization

## 🚀 Live Demo

**🌐 Website**: [https://terawebar.netlify.app](https://terawebar.netlify.app)
**📖 API Docs**: [https://terawebar.netlify.app/download](https://terawebar.netlify.app/download)

## 📋 Table of Contents

- [Features](#-features)
- [Installation](#-installation)
- [Usage](#-usage)
- [API Documentation](#-api-documentation)
- [Cookie Setup Guide](#-cookie-setup-guide)
- [Technology Stack](#-technology-stack)
- [Project Structure](#-project-structure)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

## ⚡ Quick Start

```bash
# Clone and install
git clone https://github.com/Itz-Ashlynn/Terabox-Web.git
cd Terabox-Web
npm install

# Start development server
npm run dev

# Open http://localhost:5173
```

## 🛠️ Installation

### Prerequisites
- **Node.js** (v18 or higher)
- **npm** or **yarn**
- **Git**

### Local Development Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/Itz-Ashlynn/Terabox-Web.git
   cd Terabox-Web
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Start development server**
   ```bash
   npm run dev
   # or
   yarn dev
   ```

4. **Open your browser**
   ```
   http://localhost:5173
   ```

### Build for Production

```bash
npm run build
# or
yarn build
```

## 📖 Usage

### Web Interface

1. **Visit the website**: [https://terawebar.netlify.app](https://terawebar.netlify.app)
2. **Setup your cookie**: Follow the detailed guide in the Cookie Setup section
3. **Enter TeraBox URL**: Paste your TeraBox share link
4. **Download**: Choose between direct download or proxy download

### API Usage

The API provides programmatic access to TeraBox file information and download links.

#### Base URL
```
https://terawebar.netlify.app
```

#### Endpoints

##### POST `/api/download`
Get file information and download links.

**Request:**
```bash
curl -X POST "https://terawebar.netlify.app/api/download" \
  -H "Content-Type: application/json" \
  -d '{
    "link": "https://1024terabox.com/s/1abc123def456",
    "cookies": "ndus=YourCookieValueHere"
  }'
```

**Response:**
```json
{
  "file_name": "example_file.zip",
  "download_link": "https://direct-download-link.com/file",
  "thumbnail": "https://thumbnail-url.com/thumb.jpg",
  "file_size": "125.50 MB",
  "size_bytes": 131621888,
  "proxy_url": "https://terabox.ashlynn.workers.dev/proxy?url=encoded_url&file_name=example_file.zip&cookie=encoded_cookie"
}
```

## 🔐 API Documentation

### Authentication
All API requests require a valid TeraBox `ndus` cookie for authentication.

### Request Format
- **Method**: POST
- **Content-Type**: application/json
- **Body**: JSON object with `link` and `cookies` parameters

### Response Format
- **Success**: HTTP 200 with file information
- **Error**: HTTP 400/500 with error message

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `link` | string | ✅ | TeraBox share URL |
| `cookies` | string | ✅ | TeraBox ndus cookie value |

### Response Fields

| Field | Type | Description |
|-------|------|-------------|
| `file_name` | string | Original filename from TeraBox |
| `download_link` | string | Direct download URL from TeraBox |
| `thumbnail` | string | Preview image URL (if available) |
| `file_size` | string | Human-readable file size |
| `size_bytes` | number | File size in bytes |
| `proxy_url` | string | External proxy download URL |

### HTTP Status Codes

| Code | Description |
|------|-------------|
| 200 | Success - File information retrieved |
| 400 | Bad Request - Invalid parameters |
| 404 | Not Found - Endpoint not found |
| 500 | Server Error - Internal error occurred |

## 🍪 Cookie Setup Guide

### How to Export NDUS Cookie

Follow these simple steps to extract your NDUS cookie using the Cookies Editor extension:

#### Step 1: Install Cookies Editor Extension
Download and install the Cookies Editor extension from your browser's extension store:
- **Chrome**: [Chrome Web Store](https://chrome.google.com/webstore)
- **Firefox**: [Firefox Add-ons](https://addons.mozilla.org)

#### Step 2: Open TeraBox Website
Navigate to [https://terabox.com](https://terabox.com) in your browser and log in to your account.

#### Step 3: Play Any Video
Find any video file on TeraBox and start playing it. This ensures your session is active and the NDUS cookie is properly set.

#### Step 4: Open Cookies Editor
Click on the Cookies Editor extension icon in your browser toolbar.

#### Step 5: Find NDUS Cookie
In the cookies list, search for the cookie named `ndus`.

#### Step 6: Copy Cookie Value
Copy the entire value of the NDUS cookie. It should look like:
```
Y2YqaCTteHuiU3Ud_MYU7vHoVW4DNBi0MPmg_1tQ
```

#### Step 7: Use in API
Use the complete cookie in the format:
```
ndus=YOUR_COPIED_VALUE
```

### Important Tips

- **Alternative Method**: You can also use browser Developer Tools (F12) → Application → Cookies → terabox.com → find 'ndus'
- **Cookie Validity**: NDUS cookies may expire after some time. If you get authentication errors, generate a new cookie
- **Account Type**: Both free and premium accounts work, but premium accounts offer significantly faster download speeds

## 🛠️ Technology Stack

### Frontend
- **⚛️ React 18**: Modern React with hooks and functional components
- **📘 TypeScript**: Type-safe development with full IntelliSense
- **🎨 Tailwind CSS**: Utility-first CSS framework for rapid UI development
- **🧭 React Router**: Client-side routing for SPA navigation
- **🎭 Lucide React**: Beautiful, customizable icons

### Backend
- **☁️ Netlify Functions**: Serverless functions for API endpoints
- **🔄 CORS Handling**: Cross-origin request management
- **🛡️ Proxy Integration**: External proxy service integration

### Development Tools
- **⚡ Vite**: Fast build tool and development server
- **📦 npm/yarn**: Package management
- **🔧 ESLint**: Code linting and formatting
- **🎯 PostCSS**: CSS processing and optimization

### Deployment
- **🌐 Netlify**: Hosting, CI/CD, and serverless functions
- **🔄 GitHub Actions**: Automated deployment and testing
- **📈 Analytics**: Performance monitoring and user analytics

## 📁 Project Structure

```
terabox-web/
├── 📁 public/                  # Static assets
├── 📁 src/                     # Source code
│   ├── 📁 components/          # React components
│   │   ├── 🎨 Header.tsx      # Navigation header
│   │   ├── 📥 DownloadCard.tsx # File info display
│   │   └── 🍪 CookieModal.tsx  # Cookie setup modal
│   ├── 📁 context/             # React Context
│   │   ├── 🌙 ThemeContext.tsx # Dark/light theme
│   │   └── 🍪 CookieContext.tsx # Cookie management
│   ├── 📁 pages/               # Page components
│   │   ├── 🏠 Home.tsx         # Main landing page
│   │   ├── 📖 Download.tsx     # API documentation
│   │   └── ℹ️ About.tsx        # About page
│   ├── 📁 services/            # API services
│   │   └── 🔌 api.ts           # API client functions
│   ├── 🎨 index.css            # Global styles
│   ├── ⚛️ App.tsx              # Root component
│   └── 🚀 main.tsx             # Application entry
├── 📁 netlify/                 # Netlify functions
│   └── 📁 functions/           # Serverless functions
│       ├── 📥 download.js      # Download endpoint
│       ├── 🔧 api.js           # Main API endpoint
│       └── 🔄 proxy.js         # Proxy endpoint
├── ⚙️ netlify.toml             # Netlify configuration
├── 🎨 tailwind.config.js       # Tailwind configuration
├── 📦 package.json             # Dependencies and scripts
├── 🔧 vite.config.ts           # Vite configuration
└── 📖 README.md                # This file
```

## 🌐 Deployment

### Netlify Deployment (Recommended)

1. **Fork this repository**
2. **Connect to Netlify**:
   - Login to [Netlify](https://netlify.com)
   - Click "New site from Git"
   - Select your forked repository
3. **Configure build settings**:
   - Build command: `npm run build`
   - Publish directory: `dist`
4. **Deploy**: Netlify will automatically deploy your site

### Manual Deployment

1. **Build the project**:
   ```bash
   npm run build
   ```

2. **Deploy the `dist` folder** to your hosting provider

### Environment Variables

No environment variables are required for basic functionality. The application uses:
- Netlify Functions for API endpoints
- External proxy service for downloads
- Client-side cookie management

## 🤝 Contributing

We welcome contributions! Please follow these steps:

### Getting Started

1. **Fork the repository**
2. **Create a feature branch**:
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make your changes**
4. **Commit your changes**:
   ```bash
   git commit -m 'Add amazing feature'
   ```
5. **Push to the branch**:
   ```bash
   git push origin feature/amazing-feature
   ```
6. **Open a Pull Request**

### Development Guidelines

- **Code Style**: Follow existing TypeScript and React patterns
- **Testing**: Ensure your changes don't break existing functionality
- **Documentation**: Update documentation for new features
- **Responsive**: Test on mobile devices and different screen sizes
- **Accessibility**: Maintain ARIA labels and keyboard navigation

### Areas for Contribution

- 🐛 **Bug Fixes**: Report and fix bugs
- ✨ **New Features**: Add new functionality
- 🎨 **UI/UX Improvements**: Enhance design and user experience
- 📖 **Documentation**: Improve docs and guides
- 🔧 **Performance**: Optimize speed and efficiency
- 🌐 **Internationalization**: Add multi-language support

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 TeraBox Web - Ashlynn

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 🙏 Acknowledgments

- **TeraBox**: For providing the file sharing service
- **React Team**: For the amazing React framework
- **Tailwind CSS**: For the utility-first CSS framework
- **Netlify**: For hosting and serverless functions
- **Lucide**: For the beautiful icon set
- **External Proxy**: Thanks to the external proxy service provider

## 📞 Support

If you encounter any issues or have questions:

1. **Check the documentation**: Most common issues are covered here
2. **Search existing issues**: Someone might have already reported it
3. **Create a new issue**: Provide detailed information about the problem
4. **Join our community**: Connect with other users and contributors

## 🔗 Links

- **🌐 Live Website**: [https://terawebar.netlify.app](https://terawebar.netlify.app)
- **📖 API Documentation**: [https://terawebar.netlify.app/download](https://terawebar.netlify.app/download)
- **🐙 GitHub Repository**: [https://github.com/Itz-Ashlynn/Terabox-Web](https://github.com/Itz-Ashlynn/Terabox-Web)
- **🚀 Netlify Dashboard**: [https://app.netlify.com](https://app.netlify.com)

---

<div align="center">

**⭐ Star this repository if you found it helpful! ⭐**

Made with ❤️ by [Ashlynn](https://t.me/Ashlynn_Repository)

</div>