# List2Cart landing page

A responsive, static launch page for `list2cart.in`. It has no backend dependency; the structure is ready to connect to Supabase when product features are defined.

## Preview locally

Open `index.html` in a browser, or run a local static server from this folder (for example, `python3 -m http.server 8000`) and visit `http://localhost:8000`.

## Deploy on Vercel

1. Sign in to Vercel and choose **Add New → Project**.
2. Import the Git repository containing this folder, or deploy this folder with Vercel's CLI.
3. If prompted for framework settings, choose **Other**. Leave the build command empty and use `.` as the output directory (or the project root if importing this folder as its own repository).
4. Deploy and open the generated `vercel.app` preview URL.
5. In the Vercel project, open **Settings → Domains**, add `list2cart.in` and `www.list2cart.in`. Set the preferred canonical domain in Vercel if prompted.
6. Vercel will show the DNS records required for this project. Keep that screen open while editing DNS in GoDaddy.

## Connect GoDaddy DNS

In GoDaddy, open **Domain Portfolio → list2cart.in → DNS → Add New Record**. Add the exact records Vercel displays. Vercel's general-purpose defaults are:

| Type | Name | Value |
|---|---|---|
| A | `@` | `76.76.21.21` |
| CNAME | `www` | `cname.vercel-dns-0.com` |

Use project-specific values from the Vercel Domains screen if they differ. Remove only conflicting A/AAAA/CNAME records for `@` or `www`; leave MX and unrelated records in place. Save the records, then return to Vercel and wait for both domains to verify. Vercel provisions HTTPS automatically after DNS verification.

If GoDaddy says DNS is managed elsewhere, the domain's nameservers point to another DNS provider. Add the records at that provider instead. Avoid changing nameservers unless you intend to move all DNS management, including email records.

## Supabase later

When app functionality is ready, add a Supabase client and environment variables through Vercel project settings. Never place a Supabase service-role key in browser code. This landing page currently collects no visitor information; its calls to action simply navigate within the page.
