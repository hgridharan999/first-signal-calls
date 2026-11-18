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

No license is granted by this note. It is a record, not a data release.
