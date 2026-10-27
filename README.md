# Innoish Website (React)

React + Vite rebuild of innoish.com with the Innoish logo and purple/white theme.

## Pages
| Route | Page |
|---|---|
| `/` | Home: hero, dashboard card, all solutions, Why Innoish, quick contact |
| `/solutions` | All solutions |
| `/solutions/:slug` | Detail page for each of the 7 solutions |
| `/about` | About, Why Innoish, core capabilities |
| `/contact` | Enquiry form and contact details |
| `/demo` | Request a Demo form |
| `/privacy`, `/terms` | Legal pages (templates, so review them before publishing) |
| `*` | 404 page |

## Run locally
```bash
npm install
npm run dev        # http://localhost:5173
```

## Build for production
```bash
npm run build      # output in dist/
npm run preview
```
Upload the contents of `dist/` to any static host. The app uses client-side routing, and the redirect rules for common hosts are already included:
- Netlify: `public/_redirects`
- Vercel: `vercel.json`
- Apache / cPanel / Hostinger: `public/.htaccess`

## Editing content
- **Contact email, company name:** `src/config.js`
- **Solutions (titles, bullets, benefits, steps):** `src/data/solutions.js`. Adding an entry automatically creates a card and a detail page.
- **Colors and fonts:** CSS variables at the top of `src/styles.css`
- **Logo:** `src/assets/innoish-logo.png` (and the white version for the footer). The favicon is `public/favicon.png`.

## Forms
The enquiry and demo forms open the visitor's email app with the message pre-filled, addressed to `contactEmail` in `src/config.js`. To post submissions directly to a backend or a form service (e.g. Formspree, EmailJS), replace `handleSubmit` in `src/components/EnquiryForm.jsx`.
