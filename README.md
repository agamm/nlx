# nlx
NewsletterX - Open-source, headless, supercharged-analytics newsletter system.

## Why?

- 📊 Supercharged analytics: per URL, per email analytics, segmentation tools, deliverability metrics, blog analytics - all SQL queriable for your needs.
- 📝 MDX by default (including rasterizing components for email).
- 🦿Headless - customize the frontend blog of your newsletter as you please - don't be limited by templates.
  - Customize templates like welcome, verify, and unsubscribe emails.
- 📤 Email provider agnostic - SES/Mailgun/SendinBlue/Sendgrid.
- 👀 Sponsorship-powered newsletter by default (priced ad slots and approval, auto-generate ad information for sponsors, ad metrics).
- 💲Open-source!
- 🔍 SEO-optimized - Statically generate your posts via [Astro](https://astro.build/).
  - Scalable blog-wise (static files and stateless).
- 🧩 Extendible - want a paid newsletter/community? swap it with an NLX plugin.
  - Rich media and cards: Twitter, youtube, callouts, and markdown.
  - Plugins: paid subscribers w/ gated content (granular gated content, links), referrals, and more...
- ⬆️ Easy hosting: Best in class DX using [JAMStack providers](https://docs.astro.build/en/guides/deploy/).
- 🍰 Easy backup/restore - file-based content and one-click db export (one zip file).
- 🛸 Import newsletter from Substack/Ghost/Mailchimp/Revue.
- Other features: double-opt-in, auto-optimize images, auto `?ref` on links.

## Roadmap
MVP Phase:
- Manage to have a way to convert MDX into a blog post in Astro and send it as an email - via the cli at first.
- Add subscription service with API back to frontend.
- Add analytics service per link and subscriber.
- Start versioning & releasing it.

## Architecture
*Statically generated, API routes and DB for analytics.*

### Front-end
We decided to use [Astro.js](astro.build) because of the following pros:
- Generates static content which is optimized for SEO.
- Use whatever view library of choice - 100% headless customizability.
- MDX as a first-class citizen.
- Easy deployment.

### Back-end
- Sending emails via https://github.com/sofn-xyz/mailing (and maybe [mjml](https://github.com/mjmlio/mjml))
- Using [Astro API routes](https://docs.astro.build/en/guides/server-side-rendering/#api-routes) for serverside requests (mainly for analytics and subscribers).
- DB: (TODO) either [prisma](https://www.prisma.io/), [supabase](https://supabase.com/) or [plantscale](https://planetscale.com/).
- Because MDX is the source of truth for our emails and blog the serverside can be lean and only work on analytics and list segmentation.


### Other nice-to-haves
- 2FA for admin.
- Captcha on subscribe.
- Cron backups.
- Verify email on signup-api (check mx records).
- Encrypt member emails and info (admin secondary password to send email).
- Auto-tweet new post.
- Comments (via discord?).

