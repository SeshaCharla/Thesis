# Thesis Spell Check, Grammar Check & Consistency Report

Generated: Feb 25, 2025  
Tools used: `aspell` (LaTeX mode), `chktex`, custom Python checker  
Files checked: 59 `.tex` content files (excluding template/config files)

---

## 1. Spelling

**Status: Clean** — No misspellings found after applying the custom dictionary from `.hunspell_words.txt` (166 domain-specific words). The aspell LaTeX mode correctly skipped math environments and LaTeX commands.

---

## 2. British vs American Spelling Inconsistencies

These are the **most important** issues to resolve for consistency.

### 2a. `modelling` (British) vs `modeling` (American)

| Variant | Files |
|---------|-------|
| **modelling** (British) | `secs/1-intro/subs/1-2_cstr.tex` (lines 1, 5), `secs/n-conclusion/0-conclusion.tex`, `secs/n-conclusion/0_subs/2_future.tex`, `secs/n-back/3-pubs.tex` (lines 8, 12, 20) |
| **modeling** (American) | `secs/0-front/3-acknowledgments.tex`, `secs/1-intro/subs/1-2_cstr.tex` (line 3), `secs/4-NOx_mdl/1-subs/change_in_nox_model.tex`, `secs/n-conclusion/0_subs/1_contrib.tex` |

**Note:** `1-2_cstr.tex` uses **both** variants — "Modelling" in the section title (line 1) and "modeling" in the body (line 3).

### 2b. `modelled` (British) vs `modeled` (American)

| Variant | Files |
|---------|-------|
| **modelled** (British) | `secs/1-intro/subs/1-2_cstr.tex` (lines 119, 130) |
| **modeled** (American) | `secs/1-intro/subs/1-2_cstr.tex` (line 16), `secs/2-data/3-cross.tex`, `secs/3-governing_eqns/2-NH3ads_proc_dyn.tex`, `secs/3-governing_eqns/3-NOx_proc_dyn.tex`, `secs/3-governing_eqns/4-NH3_proc_dyn.tex`, `secs/5-sat_detect/2-param_dist.tex` |

**Note:** Again, `1-2_cstr.tex` uses both variants.

### 2c. `sulphur` (British) vs `sulfur` (American)

| Variant | Files |
|---------|-------|
| **sulphur** (British) | `secs/1-intro/subs/1-1_OBD.tex` (line 9) |
| **sulfur** (American) | `secs/1-intro/0-intro.tex` |

### 2d. `Organisation` (British)

- `secs/n-back/2-vita.tex` uses "Organisation" (British). American would be "Organization". Since this refers to "Indian Space Research Organisation" (ISRO), the British spelling is correct as it's a proper noun.

**Recommendation:** Standardize to **American** spelling throughout (common for US university theses). Change all `modelling` → `modeling`, `modelled` → `modeled`, `sulphur` → `sulfur`. Keep "Organisation" as-is (proper noun).

---

## 3. Grammar Issues

### 3a. Weak word usage
- `secs/2-data/2-data_units.tex:39` — Uses "very high" — consider a stronger alternative like "substantially high" or just "high"

### 3b. Verbose phrase
- `secs/3-governing_eqns/1-reactions.tex:41` — "in order to" can be simplified to "to"

### 3c. Possible missing comma before "which" (non-restrictive clauses)
These lines use "which" without a preceding comma. If the clause is non-restrictive (adding extra info, not defining), a comma is needed:

- `secs/3-governing_eqns/5-urea_dosing_proc_dyn.tex:43` — "...zero flow rate which makes sense physically"
- `secs/4-NOx_mdl/1_NOx_r_mdl.tex:59` — "...from (\ref{eqn::ads_avg}) for getting a dynamic model for $NO_x$-reduction process which explicitly depends..."
- `secs/5-sat_detect/4-truck_aging.tex:5` — "...Table~\ref{tab::truck_data_summary}) during which the catalyst has aged..." *(OK — "during which" is fine)*
- `secs/5-sat_detect/4-truck_aging.tex:8` — "...driving period from engine start to engine stop..." *(false positive — "which" not present in this pattern)*
- `secs/5-sat_detect/3_subs/2_aging_detection.tex:48` — "...unknown parameter $\theta_{sat}$ which can be estimated" → should be ", which can be estimated"

---

## 4. LaTeX-Specific Issues

### 4a. Missing Non-Breaking Spaces before `\cite` and `\ref` (51 instances)

Using `~\cite` and `~\ref` prevents line breaks between the preceding word and the citation/reference number. This is a best practice.

**Files with missing `~\cite`:**
- `secs/1-intro/0-intro.tex`: lines 15, 27, 58, 63
- `secs/1-intro/subs/1-1_OBD.tex`: lines 10, 18, 23, 24, 25, 26, 37, 42
- `secs/1-intro/subs/1-2_cstr.tex`: lines 5, 11, 12, 17, 18, 27, 43, 128
- `secs/3-governing_eqns/1-reactions.tex`: line 37
- `secs/4-NOx_mdl/1-subs/parametrization.tex`: line 27
- `secs/5-sat_detect/0-sat_detect.tex`: lines 2, 25, 26
- `secs/5-sat_detect/1-wald_test.tex`: lines 45, 73
- `secs/5-sat_detect/5-unconstrained_results.tex`: line 24
- `secs/5-sat_detect/6-detector_performance.tex`: line 5
- `secs/5-sat_detect/3_subs/2_aging_detection.tex`: line 49
- `secs/5-sat_detect/2_subs/2-1_MLE_derivation.tex`: lines 7, 54

**Files with missing `~\ref`:**
- `secs/2-data/2-data_units.tex`: line 102
- `secs/3-governing_eqns/2-NH3ads_proc_dyn.tex`: line 14
- `secs/4-NOx_mdl/25_switching_condition.tex`: lines 2, 75, 76, 102
- `secs/4-NOx_mdl/2_catalyst_saturation.tex`: lines 6, 19, 43
- `secs/4-NOx_mdl/3_validation.tex`: line 6
- `secs/4-NOx_mdl/2-subs/parm_est.tex`: line 45
- `secs/4-NOx_mdl/1-subs/g0.tex`: line 4
- `secs/4-NOx_mdl/1-subs/g1.tex`: line 5
- `secs/4-NOx_mdl/1-subs/g2.tex`: line 9
- `secs/4-NOx_mdl/1-subs/g3.tex`: line 8
- `secs/4-NOx_mdl/1-subs/g4.tex`: line 5
- `secs/5-sat_detect/4-truck_aging.tex`: lines 23, 52
- `secs/5-sat_detect/3_subs/2_aging_detection.tex`: line 25

### 4b. ChkTeX Warnings (from chktex)

**Punctuation inside inner math mode** (Warning 40):
- `secs/4-NOx_mdl/1-subs/change_in_nox_model.tex`: lines 83, 87 — `\item[$A1.$]`, `\item[$A2.$]`
- `secs/4-NOx_mdl/1-subs/parametrization.tex`: lines 8, 10, 13, 18 — `\item[$A3.$]` through `\item[$A6.$]`

**`\min`/`\max` should use LaTeX operators** (Warning 35):
- `secs/4-NOx_mdl/25_switching_condition.tex`: line 73 — `T_{min}` and `T_{max}` in subscripts are fine; this is a false positive for subscript usage.
- `secs/4-NOx_mdl/1-subs/parametrization.tex`: line 34 — Same issue.

**Wrong dash length** (Warning 8):
- `secs/n-conclusion/0_subs/1_contrib.tex`: lines 5, 41, 53 — `SCR--ASC` uses em-dash (`--`) where an en-dash or hyphen may be more appropriate for compound terms.
- `secs/n-conclusion/0-conclusion.tex`: line 3 — Same `SCR--ASC` pattern.
- `secs/n-back/3-pubs.tex`: lines 20, 22, 24, 26 — Dash ranges in page numbers.

**Space before punctuation** (Warning 26):
- `secs/n-back/3-pubs.tex`: line 26 — `Charla, S. , Yao` has extra space before comma.
  - Also on lines 8, 12: `Meckl, P. , Yao` — same issue.

---

## 5. Terminology/Hyphenation Consistency

### 5a. `test cell` vs `test-cell`

Both forms are used across the thesis. Pick one and use it consistently.

| Variant | Files |
|---------|-------|
| **test cell** (no hyphen) | `0-data.tex`, `4-data_preproc.tex`, `0-1_test_cell_data.tex`, `3-testcell_aging.tex`, `5-unconstrained_results.tex`, `2_aging_detection.tex`, `1_contrib.tex` |
| **test-cell** (hyphenated) | `5-abstract.tex`, `0-intro.tex`, `0-data.tex`, `1-res_time.tex`, `4-data_preproc.tex`, `0-1_test_cell_data.tex`, `0-2_truck_data.tex`, `0-governing_eqns.tex`, `3-testcell_aging.tex`, `4-truck_aging.tex`, `5-unconstrained_results.tex`, `6-detector_performance.tex`, and more |

**Recommendation:** Use "test-cell" as a compound adjective (e.g., "test-cell data") and "test cell" as a noun (e.g., "the test cell"). Or pick one form consistently.

### 5b. `rate-constant` vs `rate constant`

| Variant | Files |
|---------|-------|
| **rate-constant** (hyphenated) | `3_validation.tex`, `change_in_nox_model.tex`, `2_aging_detection.tex` |
| **rate constant** (no hyphen) | `6-symbols.tex`, `1-reactions.tex`, `2-NH3ads_proc_dyn.tex`, `1_NOx_r_mdl.tex`, `25_switching_condition.tex`, `change_in_nox_model.tex`, `parametrization.tex`, `0-sat_detect.tex`, `3-testcell_aging.tex`, `1_contrib.tex` |

**Recommendation:** "Rate constant" (no hyphen) is standard in chemistry/engineering. Use it consistently.

---

## 6. Extra Space Before Commas in Publications

In `secs/n-back/3-pubs.tex`:
- Line 8: `Meckl, P. , Yao` → should be `Meckl, P., Yao`
- Line 12: `Meckl, P. , Yao` → should be `Meckl, P., Yao`
- Line 26: `Charla, S. , Yao` → should be `Charla, S., Yao`

---

## Summary of Actionable Items

| Category | Count | Priority |
|----------|-------|----------|
| British/American spelling inconsistencies | 4 patterns | **High** |
| Missing `~` before `\cite`/`\ref` | 51 | Medium |
| Hyphenation inconsistencies | 2 patterns | **High** |
| Extra spaces before commas (pubs) | 3 | **High** |
| Grammar (missing commas, verbose phrases) | 5 | Medium |
| ChkTeX warnings (punctuation in math) | 6 | Low |

