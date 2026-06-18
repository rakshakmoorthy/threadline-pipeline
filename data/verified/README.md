# Threadline — Verified Data Folder

**Project:** Threadline — Adaptive Fashion Market Intelligence Pipeline  
**Course:** INFO7375 Branding & AI — Assignment 5B  
**Student:** Raksha Krishna Moorthy  
**Last updated:** 2026-06-18

---

## Folder Structure

```
data/verified/
  reddit-community-posts/     -- 25 records | Updated 2026-06-17 | Condition-specific Reddit posts about clothing struggles
  amazon-adaptive-reviews/    -- 36 records | Updated 2026-06-16 | Verified Amazon reviews for adaptive garments
  README.md
```

---

## Source 1: reddit-community-posts/

**Record count:** 25 verified records  
**Last update date:** 2026-06-17  
**File:** `reddit_verified.csv`

**Subreddit breakdown:**
- r/breastcancer: 18 records
- r/ostomy: 5 records
- r/rheumatoid: 2 records

**What each record represents:**  
A single public post or comment from a condition-specific subreddit in which a person describes a clothing or dressing struggle in their own words — what they cannot wear, what garment features they need, or what they wish existed.

**Quality gate applied:**  
A record passes if it has ALL of the following:
1. Subreddit source (one of: r/breastcancer, r/ostomy, r/Thritis, r/rheumatoid)
2. Post date within the last 3 years (2023 or later)
3. Stable post ID (from the URL)
4. At least 20 words of body text
5. Body text references clothing, dressing, or a garment-related struggle

**Records rejected and why:**  
Raw collection pulled approximately 60–70 candidate posts across all four subreddits. The following categories of posts were rejected:

| Rejection reason | Approximate count |
|---|---|
| No clothing or dressing reference (emotional support, treatment, medication posts) | ~30 posts |
| Under 20 words of body text (short celebration or update posts) | ~5 posts |
| Post older than 3 years | ~3 posts |
| Duplicate or bot post | ~2 posts |

**Total rejected:** approximately 40 posts  
**Total passing:** 25 posts

---

## Source 2: amazon-adaptive-reviews/

**Record count:** 36 verified records  
**Last update date:** 2026-06-16  
**File:** `amazon_verified.csv`

**Product category breakdown:**
- Post-surgery bra (front closure zip): 8 records
- Post-mastectomy drain pocket shirt: 8 records
- Post-surgical front closure bra: 9 records
- Post-surgery adaptive wear (ostomy): 11 records

**What each record represents:**  
A single customer review for an adaptive garment — including star rating, verified-purchase confirmation, product category, review date, and review text describing the customer's experience with the garment's functional features.

**Quality gate applied:**  
A record passes if it has ALL of the following:
1. Star rating (1–5)
2. Verified-purchase flag set to true
3. Product category (front-closure bras, post-surgery shirts with drain pockets, or post-surgery adaptive wear for ostomy management)
4. Review date (2023 or later)
5. At least 15 words of review text

**Records rejected and why:**  
Raw collection pulled approximately 60+ candidate reviews across product pages. The following categories were rejected:

| Rejection reason | Approximate count |
|---|---|
| Unverified purchase | ~10 reviews |
| Under 15 words of review text (single word or short phrase reviews) | ~8 reviews |
| No meaningful product feature reference (generic "good product" with no garment detail) | ~6 reviews |
| Non-English reviews without sufficient translation context | ~3 reviews |

**Total rejected:** approximately 27 reviews  
**Total passing:** 36 reviews

---

## GIGO Gate Summary

Both sources were cleaned and validated against their respective quality gates before being placed in `data/verified/`. No raw or unvalidated records are present in this folder. All records in both CSVs have `gate_passed = yes`.

The reject log above documents what failed and why, making the cleaning process auditable rather than a black box.

---

## Access

This repository is public. Access has been granted to course instructors for grading review.

**Repository:** https://github.com/rakshakmoorthy/threadline-pipeline
