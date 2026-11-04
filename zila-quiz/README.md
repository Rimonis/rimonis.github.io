# Zila Quiz (deshcheno.com)

This folder is the whole website. Cloudflare Pages serves it at https://deshcheno.com.

## How it is hosted

- **Code:** the `zila-quiz/` folder of the GitHub repo `Rimonis/rimonis.github.io`.
- **Hosting:** a Cloudflare Pages project called `zila-quiz`, linked to that repo. Its settings are:
  - Production branch: `main`
  - Build command: none
  - Build output directory: `zila-quiz`
- **Domain:** deshcheno.com was bought at Namecheap, but its nameservers point to Cloudflare, so all DNS is managed in Cloudflare.
- **Accounts:** Firebase project `deshcheno`, which handles Google sign-in and stores scores in Firestore. Its authorised domains include deshcheno.com and www.deshcheno.com.

## Updating the site

Push a change to `main`. Cloudflare rebuilds the site by itself within about a minute. You can watch it under Cloudflare dashboard > Workers & Pages > zila-quiz > Deployments.

## Google Search Console

1. Go to https://search.google.com/search-console and click **Add property**.
2. Choose **Domain** and type `deshcheno.com`.
3. Google shows a TXT record. Copy it.
4. In Cloudflare, open deshcheno.com > DNS > **Add record**.
5. Set Type to TXT and Name to `@`, then paste the record as the content and click Save.
6. Back in Search Console, click **Verify**.
7. Open **Sitemaps**, enter `sitemap.xml`, and click Submit.
