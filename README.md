# Pannu HD Studio Portfolio Website

A modern, responsive, and production-ready photography portfolio website built with Next.js 14, TypeScript, and Tailwind CSS. This website showcases professional photography services with a beautiful gallery, contact form, and comprehensive service pages.

![Photography Portfolio Website](https://images.unsplash.com/photo-1606800052052-a08af7148866?w=1200&h=630&fit=crop)

## ✨ Features

- **Modern Design**: Clean, professional aesthetic with custom Tailwind theme
- **Responsive Layout**: Mobile-first design that works on all devices
- **Portfolio Gallery**: Filterable gallery with lightbox functionality
- **Service Pages**: Individual pages for each photography service
- **Contact Form**: Working contact form with email integration
- **SEO Optimized**: Meta tags, structured data, and sitemap
- **Accessibility**: WCAG AA compliant with keyboard navigation
- **Performance**: Optimized images, lazy loading, and fast loading times
- **TypeScript**: Full type safety throughout the application
- **Email Integration**: SMTP and Formspree fallback support

## 🚀 Tech Stack

- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Animations**: Framer Motion
- **Images**: next/image with optimization
- **Validation**: Zod
- **Email**: Nodemailer + Formspree fallback
- **Lightbox**: yet-another-react-lightbox
- **Icons**: Lucide React
- **SEO**: next-sitemap
- **Linting**: ESLint + Prettier

## 📋 Prerequisites

- Node.js 18.0 or higher
- npm, yarn, or pnpm package manager
- Git

## 🛠️ Getting Started

### 1. Clone the Repository

```bash
git clone <repository-url>
cd photography-portfolio
```

### 2. Install Dependencies

```bash
npm install
# or
yarn install
# or
pnpm install
```

### 3. Environment Setup

Copy the example environment file and configure your settings:

```bash
cp env.example .env.local
```

Edit `.env.local` with your configuration:

```env
# Site Configuration
SITE_URL=https://www.yourdomain.com
NEXT_PUBLIC_SITE_URL=https://www.yourdomain.com

# Email Configuration (SMTP)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-app-password
SMTP_SECURE=false
TO_EMAIL=hello@yourdomain.com
FROM_EMAIL=hello@yourdomain.com

# Formspree Fallback (if SMTP not configured)
FORMSPREE_ENDPOINT=https://formspree.io/f/YOUR_FORM_ID

# Optional: reCAPTCHA
ENABLE_CAPTCHA=false
NEXT_PUBLIC_RECAPTCHA_SITE_KEY=your-recaptcha-site-key
RECAPTCHA_SECRET_KEY=your-recaptcha-secret-key
```

### 4. Run the Development Server

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### 5. Build for Production

```bash
npm run build
npm start
# or
yarn build
yarn start
# or
pnpm build
pnpm start
```

## ⚙️ Configuration

### Site Configuration

All site settings are centralized in `src/config/site.config.ts`. Update the following:

- **Brand Information**: Site name, tagline, contact details
- **Colors**: Primary, secondary, and accent colors
- **Services**: Available photography services and pricing
- **Portfolio**: Sample images and categories
- **Testimonials**: Client testimonials
- **FAQ**: Frequently asked questions

### Tailwind Theme

Customize the design system in `tailwind.config.ts`:

- Colors and gradients
- Typography (Inter + Playfair Display)
- Spacing and sizing
- Animations and transitions
- Custom components

### SEO Settings

Update SEO settings in `src/lib/utils.ts`:

- Meta descriptions
- Open Graph images
- Canonical URLs
- JSON-LD structured data

## 📧 Email Setup

### Option 1: SMTP (Recommended)

Configure SMTP settings in your `.env.local`:

```env
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-app-password
SMTP_SECURE=false
TO_EMAIL=hello@yourdomain.com
FROM_EMAIL=hello@yourdomain.com
```

For Gmail, you'll need to:
1. Enable 2-factor authentication
2. Generate an app password
3. Use the app password in `SMTP_PASS`

### Option 2: Formspree Fallback

If SMTP is not configured, the form will automatically use Formspree:

1. Sign up at [formspree.io](https://formspree.io)
2. Create a new form
3. Add the endpoint URL to `FORMSPREE_ENDPOINT`

## 🖼️ Adding Images

### Portfolio Images

1. Add images to `src/config/site.config.ts` in the `SAMPLE_IMAGES` object
2. Use high-quality images (minimum 800x600px)
3. Include proper alt text and captions
4. Images are automatically optimized with `next/image`

### Image Sources

The project is configured to use images from:
- Unsplash (already configured)
- Pexels (already configured)
- Your own domain (add to `next.config.js`)

### Adding New Image Sources

Update `next.config.js`:

```javascript
images: {
  remotePatterns: [
    {
      protocol: 'https',
      hostname: 'your-domain.com',
      port: '',
      pathname: '/**',
    },
  ],
}
```

## 🚀 Deployment

### Vercel (Recommended)

1. Push your code to GitHub
2. Connect your repository to Vercel
3. Add environment variables in Vercel dashboard
4. Deploy automatically on every push

### Other Platforms

The app can be deployed to any platform that supports Next.js:

- Netlify
- AWS Amplify
- DigitalOcean App Platform
- Railway
- Render

### Build Configuration

Ensure your deployment platform:
- Uses Node.js 18+
- Runs `npm run build` for production
- Serves static files from the `out` directory (if using static export)

## ♿ Accessibility

The website is built with accessibility in mind:

- **Semantic HTML**: Proper heading structure and landmarks
- **Keyboard Navigation**: Full keyboard support
- **Screen Readers**: ARIA labels and descriptions
- **Color Contrast**: WCAG AA compliant
- **Focus Management**: Visible focus indicators
- **Alt Text**: Descriptive alt text for all images

### Testing Accessibility

Use these tools to test accessibility:

- [WAVE](https://wave.webaim.org/)
- [axe DevTools](https://www.deque.com/axe/devtools/)
- [Lighthouse](https://developers.google.com/web/tools/lighthouse)

## 🎨 Customization

### Colors

Update the color scheme in `tailwind.config.ts`:

```typescript
colors: {
  primary: {
    // Your primary colors
  },
  secondary: {
    // Your secondary colors
  },
  accent: {
    // Your accent colors
  },
}
```

### Fonts

Change fonts in `tailwind.config.ts` and `src/app/layout.tsx`:

```typescript
fontFamily: {
  sans: ['Your-Sans-Font', 'system-ui', 'sans-serif'],
  serif: ['Your-Serif-Font', 'Georgia', 'serif'],
}
```

### Content

All content is managed in `src/config/site.config.ts`:

- Services and pricing
- Portfolio categories
- Testimonials
- FAQ content
- Contact information

## 📊 Performance

The website is optimized for performance:

- **Image Optimization**: Automatic WebP conversion and responsive sizing
- **Code Splitting**: Automatic code splitting by Next.js
- **Lazy Loading**: Images and components load as needed
- **Caching**: Optimized caching strategies
- **Bundle Size**: Minimal JavaScript bundle

### Performance Testing

Test performance with:

- [Lighthouse](https://developers.google.com/web/tools/lighthouse)
- [PageSpeed Insights](https://pagespeed.web.dev/)
- [WebPageTest](https://www.webpagetest.org/)

## 🧪 Testing

### Manual Testing Checklist

- [ ] Navigation works on all devices
- [ ] Portfolio filter functions correctly
- [ ] Lightbox opens and closes properly
- [ ] Contact form submits successfully
- [ ] All links work and are not broken
- [ ] Images load properly
- [ ] Mobile menu functions correctly
- [ ] 404 page displays correctly

### Automated Testing

Run the linter and type checker:

```bash
npm run lint
npm run type-check
```

## 🔧 Troubleshooting

### Common Issues

**Build Errors**
- Check TypeScript errors: `npm run type-check`
- Verify all imports are correct
- Ensure environment variables are set

**Email Not Sending**
- Verify SMTP credentials
- Check if Formspree fallback is working
- Review server logs for errors

**Images Not Loading**
- Check `next.config.js` remote patterns
- Verify image URLs are accessible
- Ensure proper image optimization

**Styling Issues**
- Clear browser cache
- Check Tailwind CSS compilation
- Verify custom CSS is not conflicting

### Getting Help

1. Check the [Next.js documentation](https://nextjs.org/docs)
2. Review [Tailwind CSS docs](https://tailwindcss.com/docs)
3. Search existing issues in the repository
4. Create a new issue with detailed information

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-feature`
3. Commit changes: `git commit -am 'Add new feature'`
4. Push to branch: `git push origin feature/new-feature`
5. Submit a pull request

## 📞 Support

For support and questions:

- **Email**: hello@sarahjohnsonphoto.com
- **Phone**: +1 (555) 123-4567
- **Website**: [sarahjohnsonphoto.com](https://www.sarahjohnsonphoto.com)

## 🙏 Acknowledgments

- [Next.js](https://nextjs.org/) for the amazing framework
- [Tailwind CSS](https://tailwindcss.com/) for the utility-first CSS
- [Unsplash](https://unsplash.com/) for beautiful sample images
- [Lucide](https://lucide.dev/) for the icon library
- [Framer Motion](https://www.framer.com/motion/) for smooth animations

---

**Built with ❤️ for photographers who want to showcase their work beautifully.**
