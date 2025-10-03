# Kaktuse Portfolio

Modern web development portfolio showcasing innovative digital solutions with stunning animations and glassmorphism design.

## 🌵 About

Kaktuse is a professional web development portfolio that crafts impactful, modern, scalable, innovative, and beautiful web experiences. The site features cutting-edge animations, macOS-inspired navigation, and a sophisticated design system.

## ✨ Features

### 🎨 Design & UI
- **macOS Dock Navigation** - Desktop navigation inspired by macOS dock with glassmorphism effects
- **Responsive Mobile Navigation** - Touch-friendly button navigation for mobile devices
- **Glassmorphism Design** - Modern glass-like effects with backdrop blur
- **Solar Icons** - Beautiful duotone icons from the Solar icon collection
- **Custom Animations** - Engaging animations throughout the site

### 🎭 Animations
- **Typewriter Effect** - Dynamic word cycling on homepage hero
- **Character Animation** - Staggered bouncing letters for title reveal
- **Rain Effects** - Animated falling dots on contact page and portfolio badges
- **Floating Orbs** - Gradient background elements with smooth movement
- **Fade Transitions** - Smooth fade-in-up animations for content sections
- **Counter Animations** - Animated statistics counters

### 📱 Pages
- **Home** - Impactful hero with animations and call-to-action
- **Portfolio** - Featured projects showcase with flexible grid layout
- **About** - Personal information and technology stack
- **Contact** - Modern contact methods with interactive cards and FAQ

## 🛠 Tech Stack

- **Framework:** Nuxt 3.19.2
- **Language:** Vue.js 3 with TypeScript
- **Styling:** Tailwind CSS
- **Icons:** Solar Icons & UIL Icons via @iconify
- **Runtime:** Bun
- **UI Components:** shadcn-nuxt
- **Theme:** @nuxtjs/color-mode

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ or Bun
- Git

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd kaktuse
```

2. Install dependencies:
```bash
bun install
```

3. Prepare Nuxt:
```bash
bun run postinstall
```

### Development

Start the development server:
```bash
bun run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Production

Build for production:
```bash
bun run build
```

Preview production build:
```bash
bun run preview
```

Generate static site:
```bash
bun run generate
```

## 📁 Project Structure

```
kaktuse/
├── components/
│   └── Navbar.vue          # macOS dock-style navigation
├── pages/
│   ├── index.vue           # Homepage with animations
│   ├── portfolio.vue       # Projects showcase
│   ├── about.vue           # About page with tech stack
│   └── contact.vue         # Modern contact methods
├── public/
│   └── logo.png            # Kaktuse logo
├── assets/
├── layouts/
└── nuxt.config.ts          # Nuxt configuration
```

## 🎨 Design System

### Colors
- **Primary:** #F97315 (Orange)
- **Background:** #FAFAFA (Light)
- **Text:** #1F2937 (Dark)
- **Accent:** #7D6666 (Border)

### Typography
- **Headings:** Gambarino (Custom font)
- **Body:** System font stack

### Animations
- **Duration:** 0.3s - 0.8s
- **Easing:** ease-out, cubic-bezier
- **Delays:** Staggered for sequential reveals

## 🔧 Configuration

The site uses modern web technologies with careful attention to:
- **Performance** - Optimized animations and lazy loading
- **Accessibility** - Proper semantic HTML and ARIA labels
- **SEO** - Meta tags and structured data
- **Responsive Design** - Mobile-first approach

## 📝 Available Scripts

- `bun run dev` - Start development server
- `bun run build` - Build for production
- `bun run preview` - Preview production build
- `bun run generate` - Generate static site
- `bun run postinstall` - Prepare Nuxt

## 🐛 Troubleshooting

### Common Issues

**estree-walker dependency error:**
```bash
rm -rf node_modules bun.lockb
bun install
```

**Port already in use:**
The dev server will automatically find an available port (3001, 3002, etc.)

**Icon not loading:**
Ensure icon collections are installed:
```bash
bun add @iconify-json/solar @iconify-json/uil
```

## 🤝 Contributing

This is a personal portfolio project. For questions or suggestions, please reach out through the contact methods on the website.

## 📄 License

This project is private and proprietary. All rights reserved.

---

Built with ❤️ by **Yann Thevenin** (saravenpi)