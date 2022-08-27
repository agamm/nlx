# nlx
NewsletterX - Open-source, headless, superchareged analytics newsletter system.

## Why?

- 📊 Supercharged analytics: per URL, per email analytics, segmentation tools, deliverability metrics - all SQL queriable for your needs.
- 📝 MDX by default (including rasterizing components for email).
- 🦿Headless - customize the frontend blog of your newsletter as you please - don't be limited by templates.
- 📤 Email provider agnostic - SES/Mailgun/SendinBlue/Sendgrid.
- 👀 Sponsorship powered newsletter by default (priced ad slots and approoval, auto-generate ad information for sponsors, ad metrics).
- 💲Open-source!
- 🔍 SEO-optimized - Statically generate your posts via [Astro](https://astro.build/).
- 🧩 Extendible - want a paid newsletter / community? swap if with an NLX plugin.
  - Rich media and cards: twitter, youtube, callouts and markdown.
  - Plugins: paid subscribers w/ gated content, refferals and more...
- ⬆️ Easy hosting: Best in class DX using [JAMStack providers](https://docs.astro.build/en/guides/deploy/).
- Other features: doube-opt-in,  

## Architecture
*Statically generated, API routes and DB for analytics.*

### Front-end
We decided to use [Astro.js](astro.build) because of the following pros:
- Generates static content which is optimized for SEO.
- Use whatever view libaray of chose - 100% headless cutomizability.
- MDX as a first-class-citizen.
- Easy deployment.

### Back-end
- Sending emails via https://github.com/sofn-xyz/mailing
- Using [Astro API routes](https://docs.astro.build/en/guides/server-side-rendering/#api-routes) for serverside requests (mainly for analytics).
- DB: (TODO) either [prisma](https://www.prisma.io/), [supabase](https://supabase.com/) or [plantscale](https://planetscale.com/).
- Because of MDX is the source of truth for our emails and blog the serverside can be lean and only work on analytics and list segmentation.


