# Fynn - Handwerker Service Frankfurt

A modern, responsive website for a handyman service in Frankfurt, built with SvelteKit and Tailwind CSS.

## 🚀 Features

- Responsive design with mobile-first approach
- Smooth scrolling navigation
- Contact form with multiple communication options
- Portfolio showcase
- Customer testimonials
- Service area coverage

## 🐳 Docker Deployment

### Production Build

```sh
# Build and run the production container
docker-compose up --build

# Or build manually
docker build -t fynn-handwerker .
docker run -p 3000:3000 fynn-handwerker
```

### Development Build

```sh
# Run development server with hot reload
docker-compose --profile dev up --build dev

# Or build manually
docker build -f Dockerfile.dev -t fynn-handwerker-dev .
docker run -p 5173:5173 -v $(pwd):/app fynn-handwerker-dev
```

### Docker Commands

```sh
# Build production image
docker build -t fynn-handwerker .

# Run production container
docker run -d -p 3000:3000 --name fynn-app fynn-handwerker

# Stop and remove container
docker stop fynn-app && docker rm fynn-app

# View logs
docker logs fynn-app
```

## 🛠️ Local Development

### Prerequisites

- Node.js 18+ or Docker
- npm or yarn

### Installation

```sh
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## 📁 Project Structure

```
src/
├── lib/
│   └── components/          # Svelte components
│       ├── Header.svelte    # Navigation header
│       ├── Hero.svelte      # Hero section
│       ├── About.svelte     # About section
│       ├── Services.svelte  # Services grid
│       ├── Portfolio.svelte # Project showcase
│       ├── WhyChooseUs.svelte
│       ├── Testimonials.svelte
│       ├── ContactForm.svelte
│       └── Footer.svelte
├── routes/
│   ├── +layout.svelte       # App layout
│   └── +page.svelte         # Main page
└── app.html                 # HTML template
```

## 🎨 Tech Stack

- **Framework:** SvelteKit
- **Styling:** Tailwind CSS
- **Language:** TypeScript
- **Deployment:** Docker
- **Build Tool:** Vite

## 🌐 Deployment

The application is containerized and ready for deployment on any Docker-compatible platform:

- **Local:** `docker-compose up`
- **Cloud:** Deploy to AWS ECS, Google Cloud Run, Azure Container Instances
- **VPS:** Deploy to any VPS with Docker support

## 📞 Contact Information

This website represents a handyman service in Frankfurt offering:
- Repairs and maintenance
- Renovations
- Furniture assembly
- Garden work
- Bathroom and kitchen installations
- Electrical work

---

Built with ❤️ using SvelteKit and Tailwind CSS

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```sh
# create a new project in the current directory
npx sv create

# create a new project in my-app
npx sv create my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```sh
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```sh
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.
