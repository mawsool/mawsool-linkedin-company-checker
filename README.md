# LinkedIn Current Company Checker

**Check current company and headline from LinkedIn profile URLs—without paying to re-enrich an entire profile.**

Use this before a costly CRM refresh. Paste LinkedIn URLs, upload CSV, or process a large file. If your CSV includes `previousCompany`, `needsUpdate` is true only when the employer is actually different. Case, punctuation, legal endings such as LLC, Inc, Ltd, and SA, and a shorter brand inside a longer name are treated as the same employer. `Mawsool`, `Mawsool International`, and `Mawsool International LLC` do not need an update. Omit `previousCompany` when you only want the current company.

**Mawsool LinkedIn data suite:**

- Need all available profile fields? Use **LinkedIn Profile Details from URL**.
- Need recurring monitoring? Use **LinkedIn Job Change Detector & Alerts**.
- Processing a very large profile file? Use **Mass LinkedIn Profile Scraper**.
- Have an email but no URL? Use **Email to LinkedIn Finder**.
- Have a name and company but no URL? Use **LinkedIn Profile Finder by Name & Company**.

## Did this person change jobs?

This Actor returns the current `company`, `headline`, `full_name`, and LinkedIn numeric ID. Compare the company with your CRM value to identify only the records that need deeper enrichment.

## Why check freshness first?

Refreshing every CRM contact wastes enrichment spend when most records have not changed. The cheaper workflow is:

1. Check all LinkedIn URLs here.
2. Filter `needsUpdate = true`.
3. Send only those URLs to LinkedIn Profile Details.

Your CRM database stays in your Apify account. Mawsool receives only the profile URLs and optional previous-company values submitted for lookup.

## Pricing

From **$0.60 per 1,000 URL checks** on FREE; paid Apify plans receive automatic discounts. `cost = URLs checked × your plan price per URL`.

## Inputs

- `urls`: add profile URLs in the form.
- `urlsCsv`: paste `url,previousCompany`.
- `fileUrl`: upload CSV with `url` or `linkedinUrl`.
- `resumeId`: reuse the same ID after a stopped large run to skip completed URLs.
- Up to 1,000,000 unique URLs when your Apify timeout and spending limit allow it.

## Output

`inputUrl`, `full_name`, `company`, `headline`, `linkedin_num_id`, optional `previousCompany`, `needsUpdate`, `success`, `error`, `checkedAt`.

## Common use cases

- Find stale HubSpot, Salesforce, Pipedrive, or Clay contacts.
- Verify that candidates still work at the company in your ATS.
- Refresh company and headline before outbound campaigns.
- Run a cheap freshness check before profile enrichment.

## FAQ

### What does a current-company check return?

The person's name, current company, and headline from a LinkedIn profile URL. From $0.60 per 1,000 checks.

### Does this return the website or the full profile?

No. Use Company website and firmographics for the company domain, and Profile Details for the full profile.

## Where to run it

Run the published Actor on Apify, or start from [mawsool.tech](https://mawsool.tech). This repository does not include the lookup address.
