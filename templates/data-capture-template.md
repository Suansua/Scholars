# Data Capture Template - Documentation

This document explains the structure of the data capture CSV template.

## CSV Column Reference

### Identity Fields (Columns 1-6)

| Column | Field | Description | Example |
|--------|-------|-------------|---------|
| A | `scholarship_id` | Unique identifier | SCH001 |
| B | `scholarship_name` | Official scholarship name | Chancellor's Scholarship |
| C | `university_institution` | University or institution name | University of Example |
| D | `country` | Country where university is located | United Kingdom |
| E | `target_intake` | Target intake term/year | Fall 2026 |
| F | `scope` | Program scope | All Undergraduate / Engineering Faculty / Specific Degree |

### Proof Links - Official URLs (Columns 7-13)

| Column | Field | Description | Criteria Covered |
|--------|-------|-------------|------------------|
| G | `eligibility_url` | Official eligibility page | C1 Nationality |
| H | `degree_level_url` | Official degree level page | C2 Undergraduate |
| I | `funding_benefits_url` | Official benefits page | C3, C4, C5 |
| J | `fields_majors_url` | Official eligible majors page | C6 STEM/EE |
| K | `deadline_url` | Official deadline page | C7 Deadline |
| L | `testing_english_url` | Official testing requirements | C8 SAT, C9 IELTS |
| M | `application_process_url` | Official application page | C10 Not Embassy |

### Evidence Snippets - C1 Nationality (Columns 14-17)

| Column | Field | Description |
|--------|-------|-------------|
| N | `c1_nationality_quote` | Exact quote (1-3 sentences) |
| O | `c1_nationality_page_title` | Page title |
| P | `c1_nationality_access_date` | Date accessed (YYYY-MM-DD) |
| Q | `c1_nationality_pass` | PASS / FAIL / MISSING |

### Evidence Snippets - C2 Undergraduate (Columns 18-21)

| Column | Field | Description |
|--------|-------|-------------|
| R | `c2_undergraduate_quote` | Exact quote |
| S | `c2_undergraduate_page_title` | Page title |
| T | `c2_undergraduate_access_date` | Date accessed |
| U | `c2_undergraduate_pass` | PASS / FAIL / MISSING |

### Evidence Snippets - C3 Tuition (Columns 22-25)

| Column | Field | Description |
|--------|-------|-------------|
| V | `c3_tuition_quote` | Exact quote |
| W | `c3_tuition_page_title` | Page title |
| X | `c3_tuition_access_date` | Date accessed |
| Y | `c3_tuition_pass` | PASS / FAIL / MISSING |

### Evidence Snippets - C4 Accommodation (Columns 26-29)

| Column | Field | Description |
|--------|-------|-------------|
| Z | `c4_accommodation_quote` | Exact quote |
| AA | `c4_accommodation_page_title` | Page title |
| AB | `c4_accommodation_access_date` | Date accessed |
| AC | `c4_accommodation_pass` | PASS / FAIL / MISSING |

### Evidence Snippets - C5 Stipend (Columns 30-33)

| Column | Field | Description |
|--------|-------|-------------|
| AD | `c5_stipend_quote` | Exact quote |
| AE | `c5_stipend_page_title` | Page title |
| AF | `c5_stipend_access_date` | Date accessed |
| AG | `c5_stipend_pass` | PASS / FAIL / MISSING |

### Evidence Snippets - C6 STEM/EE (Columns 34-37)

| Column | Field | Description |
|--------|-------|-------------|
| AH | `c6_stem_ee_quote` | Exact quote |
| AI | `c6_stem_ee_page_title` | Page title |
| AJ | `c6_stem_ee_access_date` | Date accessed |
| AK | `c6_stem_ee_pass` | PASS / FAIL / MISSING |

### Evidence Snippets - C7 Deadline (Columns 38-41)

| Column | Field | Description |
|--------|-------|-------------|
| AL | `c7_deadline_quote` | Exact quote with date |
| AM | `c7_deadline_page_title` | Page title |
| AN | `c7_deadline_access_date` | Date accessed |
| AO | `c7_deadline_pass` | PASS / FAIL / MISSING |

### Evidence Snippets - C8 SAT (Columns 42-45)

| Column | Field | Description |
|--------|-------|-------------|
| AP | `c8_sat_quote` | Exact quote |
| AQ | `c8_sat_page_title` | Page title |
| AR | `c8_sat_access_date` | Date accessed |
| AS | `c8_sat_pass` | PASS / FAIL / MISSING |

### Evidence Snippets - C9 IELTS/TOEFL (Columns 46-49)

| Column | Field | Description |
|--------|-------|-------------|
| AT | `c9_ielts_toefl_quote` | Exact quote |
| AU | `c9_ielts_toefl_page_title` | Page title |
| AV | `c9_ielts_toefl_access_date` | Date accessed |
| AW | `c9_ielts_toefl_pass` | PASS / FAIL / MISSING |

### Evidence Snippets - C10 Not Embassy (Columns 50-53)

| Column | Field | Description |
|--------|-------|-------------|
| AX | `c10_not_embassy_quote` | Exact quote |
| AY | `c10_not_embassy_page_title` | Page title |
| AZ | `c10_not_embassy_access_date` | Date accessed |
| BA | `c10_not_embassy_pass` | PASS / FAIL / MISSING |

### Outcome Fields (Columns 54-57)

| Column | Field | Description |
|--------|-------|-------------|
| BB | `total_pass_count` | Number of criteria passed (0-10) |
| BC | `failed_criteria` | List of failed criteria (e.g., "C8, C9") |
| BD | `outcome` | SHORTLIST / NEAR_MISS / REJECTED |
| BE | `notes` | Additional notes or clarifications |

---

## Usage Instructions

### 1. Creating New Entries

1. Generate a new `scholarship_id` (SCH001, SCH002, etc.)
2. Fill in identity fields from lead source
3. Leave evidence fields blank until proof collection

### 2. Recording Evidence

For each criterion:
1. Find the official URL
2. Copy exact quote (1-3 sentences)
3. Record page title (from browser tab)
4. Record access date in YYYY-MM-DD format
5. Evaluate and set PASS/FAIL/MISSING

### 3. Calculating Outcome

```
IF total_pass_count = 10 THEN outcome = "SHORTLIST"
IF total_pass_count = 9 THEN outcome = "NEAR_MISS"
IF total_pass_count < 9 THEN outcome = "REJECTED"
```

### 4. Quality Tips

- Use double quotes around quotes containing commas
- Escape internal quotes with double-double quotes ("")
- Keep quotes concise (1-3 sentences max)
- Use UTC dates for consistency
- Record access date at time of copying quote

---

## Example Entries

### Shortlist Entry (All Pass)
```csv
SCH001,Example Scholarship,Example University,UK,Fall 2026,All UG,...,[all evidence]...,10,,SHORTLIST,All criteria verified
```

### Near Miss Entry (One Fail)
```csv
SCH002,Another Scholarship,Other University,Germany,Fall 2026,Engineering,...,[all evidence]...,9,C9,NEAR_MISS,IELTS required with no clear waiver
```

### Rejected Entry (Multiple Fails)
```csv
SCH003,Third Scholarship,Third University,USA,Fall 2026,All UG,...,[all evidence]...,7,"C8,C9,C3",REJECTED,SAT required; IELTS required; partial tuition only
```
