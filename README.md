# Andreas - Portfolio Website

A modern, responsive portfolio landing page built with SvelteKit and shadcn-svelte, showcasing my expertise as a Senior Software Engineer with a focus on frontend development.

## 🚀 Live Demo

Visit the live site: [https://isandreas.github.io/](https://isandreas.github.io/)

## 📋 Features

- **Responsive Design**: Mobile-first approach that works seamlessly across all devices
- **Dark/Light Mode**: Toggle between themes with smooth transitions
- **Modern UI Components**: Built with shadcn-svelte for consistent, accessible components
- **Smooth Animations**: Subtle transitions and hover effects for enhanced UX
- **SEO Optimized**: Proper meta tags and semantic HTML
- **Fast Performance**: Static site generation with SvelteKit for optimal load times

## 🛠️ Technologies Used

### Frontend
- **SvelteKit**: Modern web framework for building fast, efficient applications
- **TypeScript**: Type-safe development
- **Tailwind CSS**: Utility-first CSS framework
- **shadcn-svelte**: High-quality, customizable UI components
- **Lucide Svelte**: Beautiful, consistent icons

### Deployment
- **GitHub Pages**: Static hosting
- **GitHub Actions**: Automated CI/CD pipeline

## 📦 Project Structure

```
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions deployment workflow
├── src/
│   ├── lib/
│   │   ├── components/
│   │   │   ├── ui/             # shadcn-svelte UI components
│   │   │   │   ├── button/
│   │   │   │   ├── card/
│   │   │   │   └── badge/
│   │   │   ├── Hero.svelte     # Hero section
│   │   │   ├── Skills.svelte   # Skills & About section
│   │   │   ├── Portfolio.svelte # Projects showcase
│   │   │   ├── Contact.svelte  # Contact information
│   │   │   └── ThemeToggle.svelte # Dark/light mode toggle
│   │   └── utils.ts            # Utility functions
│   ├── routes/
│   │   ├── +layout.svelte      # Root layout
│   │   ├── +page.svelte        # Main landing page
│   │   └── +page.ts            # Page configuration
│   ├── app.css                 # Global styles
│   └── app.html                # HTML template
├── static/
│   └── .nojekyll               # GitHub Pages configuration
├── package.json
├── svelte.config.js            # SvelteKit configuration
├── tailwind.config.js          # Tailwind CSS configuration
├── tsconfig.json               # TypeScript configuration
└── vite.config.ts              # Vite configuration
```

## 🚀 Local Development

### Prerequisites
- Node.js 18+ 
- npm or pnpm

### Installation

1. Clone the repository:
```bash
git clone https://github.com/isandreas/isandreas.github.io.git
cd isandreas.github.io
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser and navigate to `http://localhost:5173`

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build locally
- `npm run check` - Run type checking

## 🚀 Deployment

The site is automatically deployed to GitHub Pages when changes are pushed to the `main` branch.

### Manual Deployment

1. Build the project:
```bash
npm run build
```

2. The built files will be in the `build/` directory

### GitHub Pages Setup

1. Go to your repository settings
2. Navigate to "Pages" section
3. Set Source to "GitHub Actions"
4. The workflow will automatically deploy on push to main

## 🎨 Customization

### Update Personal Information

1. **Hero Section** (`src/lib/components/Hero.svelte`):
   - Update social media links (GitHub, LinkedIn, Email)

2. **Contact Section** (`src/lib/components/Contact.svelte`):
   - Update contact information and links

3. **Skills Section** (`src/lib/components/Skills.svelte`):
   - Modify technology stacks and badges

4. **Portfolio Section** (`src/lib/components/Portfolio.svelte`):
   - Add or modify project details

### Styling

- Global styles: `src/app.css`
- Theme colors: `tailwind.config.js` and `src/app.css`
- Component styles: Individual component files

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 📧 Contact

- GitHub: [@isandreas](https://github.com/isandreas)
- LinkedIn: [Your LinkedIn Profile](https://linkedin.com/in/yourprofile)
- Email: your.email@example.com

---

Built with ❤️ using SvelteKit and shadcn-svelte
