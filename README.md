# First Signal calls

This repository is a public, timestamped record of the companies and researchers First Signal ranked highly.

- **What a pick is.** A lead near the top of a thesis list, after investability gates (not already funded, not an SBIR
  mill, thesis match from the company's own awards). Each pick lists its score, model estimate and the stored records
  behind it.
- **Timestamps.** Each snapshot is its own git commit. The commit time is the time of the call.
- **What it predicts.** It depends on the file. Weekly picks and briefs with `"mode": "first_raise"` predict a first
  Form D filing with the SEC. Briefs with `"mode": "next_raise"` predict another Form D filing within 24 months by a
  company that already has one. Briefs with `"mode": "scouting"` predict nothing: they are lists of companies and labs
  to look at. None of them predicts a priced round. The `caveat` field in each file says which applies.
- **Verify a call later.** Find the pick's date in `picks/` (weekly) or `briefs/` (per fund). For first_raise picks,
  check the name against SEC EDGAR Form D filings dated after the commit: the first one counts. For next_raise picks,
  look for a Form D filed after the commit date (the company's earlier filings do not count). For scouting picks there
  is nothing to verify as a prediction. next_raise picks publish a lift over a base rate, never a bare probability.
  The `sha256` in each JSON file is the hash of the sorted pick list.
- **No contacts.** Nothing here contains an email, phone number or private note.

## Expected hit rate

About 2% of company picks file a first Form D within 24 months (the serve base rate is 1.7%). Top-tenth picks file about 1 time in 20. For a weekly snapshot, the expected number of hits is well under one. Judge the record on totals against the sum of the stated chances, not on named wins.

Researcher picks use a different target: a company PI on an SBIR or STTR award, or a Form D executive or director, within 36 months. They are not first-Form-D predictions, so they are not counted in the first-filing total.

## Verification window

For first_raise picks, a filing counts if it is dated after the commit date and up to 24 months after the end of the SEC data stated in the file. For the 2026-11-16 snapshot, the SEC data end on 2026-03-31, so the window closes on 2028-03-31.

## Corrections

Dated corrections are in [corrections/](corrections/). The first is [corrections/2026-11-18.md](corrections/2026-11-18.md). It covers the 2026-11-16 snapshot. The original snapshot files are not edited.

No license is granted by this note. It is a record, not a data release.
