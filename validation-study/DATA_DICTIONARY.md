# SHS Validation Study — Data Dictionary

Two files accompany this dictionary:

- `SHS_participants_anonymized.csv` — N = 193 participants (test-run entries
  by coordinators excluded), 386 LLM evaluations (each participant × 2 LLMs).
- `SHS_administrator_feedback_anonymized.csv` — N = 47 study coordinators
  ("administrators"), one feedback row each.

Both replace any internal identifiers with anonymous IDs. No file in this
deposit contains real names, matriculation numbers, or other direct
identifiers of participants or coordinators.

## SHS_participants_anonymized.csv

| Column | Meaning |
|---|---|
| `record_id` | REDCap internal record number |
| `cid` | Pseudonymous participant code: `b` + 2-digit coordinator number + 2-digit participant number within that coordinator's group (e.g. `b0103` = coordinator 01, participant 03). Not linkable to any real identity. |
| `q_wissen_1..3` | The participant's own "Verified Knowledge" prompts (verbatim, German) |
| `q_glatteis_1..3` | The participant's own "Glatteis" (trick) prompts (verbatim, German) |
| `llm1_label` / `llm2_label` | The two randomly assigned LLMs for this participant (ChatGPT, Claude, Gemini, Mistral, DeepSeek) |
| `llm1_q1..q10` / `llm2_q1..q10` | Raw SHS item responses (Likert, −2 to +2) for each of the two LLMs |
| `SHS.LLM1` / `SHS.LLM2` | Computed overall SHS score per LLM |
| `age`, `gender`, `country`, `education`, `employment`, `sector` | Demographics (categorical) |
| `tech_skill`, `llm_criticism`, `llm_usage_freq`, `llm_usage_purpose`, `llm_usage_since` | LLM experience / attitude measures |
| `fb_*` | Participant's own feedback on the SHS questionnaire (clarity, relevance, ease, response-option fit, demographic-section length, duration, comments) |

Test-run entries (coordinator self-tests before recruiting real
participants, identified by participant suffix "00" or malformed IDs) have
been removed from this file.

## SHS_administrator_feedback_anonymized.csv

| Column | Meaning |
|---|---|
| `administrator_id` | Anonymous coordinator ID (`ADMIN_01`–`ADMIN_47`), replaces the original student Matrikelnummer field, which has been removed |
| `fb_clarity`, `fb_relevance`, `fb_options_fit`, `fb_easy`, `fb_demo_len` | The coordinator's judgment of the SHS instrument's clarity, relevance, response-option fit, ease of use, and demographic-section length (these are the figures behind Table 2 in the manuscript) |
| `strategies`, `fb_comments` | Free-text observations from running sessions |


