# onegoal.website

The public pages One Goal is required to link to from its paywall. Apple and
Google both reject subscription apps whose paywall has no working Terms and
Privacy links.

- `/privacy` — the privacy policy. Must stay true to what the app actually does.
- `/terms` — licence and subscription terms.

The app links to these from `src/lib/legal.ts` in the `onegoal` repo. If a URL
here changes, change it there too.

## Publishing (GitHub Pages)

This repo must be **public** for GitHub Pages to serve it on a free plan.

1. Create a public repo `onegoal-website` under `meta5table` and push this folder.
2. Repo → Settings → Pages → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`.
3. Under *Custom domain*, enter `onegoal.website` and save. The `CNAME` file here
   already declares it.
4. Once DNS resolves, tick *Enforce HTTPS*.

## DNS (Namecheap)

Domain List → **Manage** → **Advanced DNS**.

Delete the default `CNAME  www → parkingpage.namecheap.com` and any
`URL Redirect Record` on `@`, then add:

| Type | Host | Value | TTL |
|---|---|---|---|
| A Record | @ | 185.199.108.153 | Automatic |
| A Record | @ | 185.199.109.153 | Automatic |
| A Record | @ | 185.199.110.153 | Automatic |
| A Record | @ | 185.199.111.153 | Automatic |
| CNAME Record | www | meta5table.github.io. | Automatic |

Propagation is usually under an hour. Verify both links resolve before
submitting the app:

- https://onegoal.website/privacy
- https://onegoal.website/terms

## Email

The pages give `hello@onegoal.website` as the contact address. Namecheap offers
free email forwarding: Domain List → Manage → **Redirect Email**. Point
`hello@` at a mailbox you actually read. The privacy policy promises a response
within 30 days, so it needs to reach someone.
