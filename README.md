# K72 - Digital Agency Website

A modern, animated portfolio website for K72 (Soixante Douze), a creative digital agency that specializes in brand building and strategic marketing. The site showcases the agency's philosophy, projects, and team with smooth scroll-triggered animations and a premium user experience.

## Overview

K72 is a creative agency that believes in strategic brand building with longevity. This website serves as their digital portfolio, featuring:
- **Home page**: An immersive hero experience with video background and agency mission
- **Projects page**: Interactive portfolio of case studies with scroll animations
- **Agency page**: Team showcase with dynamic image transitions and brand philosophy

## Tech Stack

- **Frontend Framework**: React 18.2.0
- **Build Tool**: Vite 5.2.0
- **Styling**: Tailwind CSS 4.1.12
- **Routing**: React Router DOM 7.8.0
- **Animation Library**: GSAP 3.13.0 (GreenSock Animation Platform)
  - `@gsap/react`: React integration for GSAP
  - `ScrollTrigger`: Plugin for scroll-based animations
- **Development**: ESLint, Vite React Plugin with Babel Fast Refresh
- **Node Module Type**: ES Modules

## Project Structure

```
src/
├── pages/
│   ├── Home.jsx              # Landing page with hero video
│   ├── Projects.jsx          # Project portfolio gallery
│   └── Agence.jsx            # About agency & team showcase
├── components/
│   ├── Navigation/
│   │   ├── Navbar.jsx        # Top navigation bar with logo & menu toggle
│   │   └── FullScreenNav.jsx # Full-screen navigation menu with animations
│   ├── home/
│   │   ├── HomeHeroText.jsx  # Hero headline section
│   │   ├── HomeBottomText.jsx # Call-to-action buttons
│   │   └── Video.jsx         # Background video player
│   ├── projects/
│   │   └── ProjectCard.jsx   # Project showcase cards with hover effects
│   └── common/
│       └── Stairs.jsx        # Page transition animation component
├── context/
│   └── NavContext.jsx        # Global navigation & color state management
├── App.jsx                   # Main app component with routing
├── main.jsx                  # React DOM root entry point
└── index.css                 # Global styles

public/
└── video.mp4                 # Home page background video

index.html                    # HTML entry point
package.json                  # Project dependencies
vite.config.js              # Vite configuration
```

## Key Features

### 1. **Smooth Page Transitions**
The `Stairs` component creates an elegant stair-step transition animation when navigating between pages using GSAP timelines.

### 2. **Dynamic Navigation**
- **Navbar**: Displays logo and hamburger menu with color switching based on current page
- **FullScreenNav**: Full-screen overlay navigation that opens on menu click with staggered animations
- **NavContext**: React Context manages navigation state and nav color globally

### 3. **Scroll-Triggered Animations**
- **Projects Page**: Project cards animate in height based on scroll position using `ScrollTrigger`
- **Agency Page**: Team member images transition as the user scrolls through the content

### 4. **Hero Section**
- Full-screen video background
- Large, responsive typography (9.5vw on desktop, 12vw on mobile)
- Embedded video element within the hero text for visual interest

### 5. **Interactive Project Cards**
- Hover effects with rounded corners and overlay text
- Two images per project displayed side-by-side on desktop

## Installation & Setup

### Prerequisites
- Node.js (v14 or higher recommended)
- npm or yarn package manager

### Install Dependencies

```bash
npm install
```

### Development Server

Start the local development server with hot module replacement:

```bash
npm run dev
```

The site will be available at `http://localhost:5173` (default Vite port).

## Scripts

- **`npm run dev`** - Start development server with HMR
- **`npm run build`** - Build optimized production bundle
- **`npm run preview`** - Preview the production build locally
- **`npm run lint`** - Run ESLint to check code quality

## Component Deep Dive

### Navigation System
- **Navbar.jsx**: Fixed header with K72 logo and hamburger menu
  - Hover effect on menu button (green highlight)
  - Dynamic color based on page (white on home, black on projects/agency)
- **FullScreenNav.jsx**: Overlay navigation menu
  - Triggered by navbar hamburger
  - Animated stair pattern background
  - Staggered link animations on open/close

### Pages

#### Home.jsx
- Full-screen fixed video background
- Hero text with embedded video element
- Call-to-action buttons linking to Projects and Agency pages
- Agency mission statement

#### Projects.jsx
- Displays portfolio with linked project images from K72's case studies
- Scroll-triggered height animations for each project pair
- Responsive grid (1 column mobile, 2 columns desktop)

#### Agence.jsx
- **Page 1**: Animated team member images that transition based on scroll position
  - Images pin to viewport during scroll using `ScrollTrigger`
  - Agency tagline and philosophy displayed alongside
- **Page 2**: Reserved for additional content

### Context API

**NavContext.jsx** provides:
- `NavbarContext`: Manages navigation open/close state
- `NavbarColorContext`: Tracks navbar color based on current route
  - White color on home page
  - Black color on projects/agency pages

## Animation Techniques

The site uses GSAP for advanced animations:

1. **Timeline Animations**: Sequences multiple animations with precise timing
2. **ScrollTrigger**: Pins elements and triggers animations on scroll events
3. **Stagger Effects**: Creates cascading animations for visual appeal
4. **Interpolation**: Smooth progress-based animations for image transitions

## Styling

Tailwind CSS provides utility-based styling with:
- Responsive design (mobile-first approach with `lg:` breakpoints)
- Custom color scheme (white, black, lime green `#D3FD50`)
- Dynamic classNames for interactive states (hover, opacity, transitions)

## Performance Considerations

- Video autoplay with `muted` attribute for browser autoplay policies
- Lazy loading considerations for agency team images
- Optimized scroll event handling with GSAP ScrollTrigger
- CSS transitions for smooth hover effects

## Deployment

Build the production-optimized bundle:

```bash
npm run build
```

The output will be in the `dist/` folder, ready for deployment to hosting services (Vercel, Netlify, GitHub Pages, etc.).


