# Period and Ovulation Prediction    

The predictions are based on the information you provide, including:  
1. Your period start/end dates and flow patterns.  
2. Birth control history.  
3. Fertility treatment usage (e.g., IVF, ovulation induction).  
4. Cycle length consistency or variability.  
5. (Future enhancements) Biomarkers like age, temperature, or hormone levels.  

---

## How It Works  

### Key Assumptions  
- In a regular cycle, ovulation occurs **~14 days before the next expected period**.  
- For irregular cycles, the app estimates ovulation based on available data but lowers confidence if the information is limited or inconsistent.  

---

### What Information You Need to Provide  

1. **Period History** (3 months preferred)  
   - Each cycle includes:  
     - Start Date (e.g., `2024-01-10`)  
     - End Date (e.g., `2024-01-14`)  
     - Flow Intensity (`Light`, `Normal`, `Heavy`, `Clots`)  

2. **Birth Control History**  
   - Used birth control in the last 6 months?  
   - Type of birth control (e.g., pill, IUD).  
   - When did you stop?  

3. **Cycle Consistency**  
   - Are your cycles consistent or do they vary significantly month-to-month?  

4. **Bleeding Duration**  
   - How many days do you usually bleed?  

5. **Fertility Treatments**  
   - Using IVF, IUI, or ovulation-induction medications?

---

## How Predictions Are Made  

1. **Calculate Average Cycle Length**  
   - Uses the start dates of your periods to estimate cycle length.  
   - Notes if cycle lengths vary widely.

2. **Adjust for Birth Control**  
   - Recent birth control cessation may lead to irregular cycles initially.  
   - Predictions gain accuracy after observing multiple natural cycles post-birth-control.

3. **Factor in Fertility Treatments**  
   - Ovulation induction may make ovulation timing more predictable.  
   - IVF/IUI treatments may require special considerations or disclaimers.

4. **Predict Ovulation and Fertile Window**  
   - For regular cycles, Ovulation ≈ 14 days before next expected period.  
   - Fertile Window spans a few days around ovulation.

---

## Example Scenarios (All assume 3 months of data unless stated otherwise)

### 1. Regular Cycles, No Complications  
**User Input:**  
- Periods:  
  - Nov 10-14  
  - Dec 10-14  
  - Jan 10-14  
- No recent birth control  
- Stable ~30-day cycle  
- No fertility treatments

**Prediction:**  
- Average cycle length ≈ 30 days  
- Next period: ~Feb 9-11  
- Ovulation: ~14 days before that (Jan 26-28)  
- Fertile window: Last week of January

**Message Example:**  
*"Your next period may start around Feb 10. Ovulation is likely around Jan 27, making late January a good time to try conceiving."*

---

### 2. Irregular Cycles, Recent Birth Control  
**User Input:**  
- Periods:  
  - Nov 25-30  
  - Jan 2-5 (no December data)  
- Used oral contraceptives until Oct  
- Irregular cycles, fertility treatments (ovulation induction) ongoing

**Prediction:**  
- Cycle length unclear (38-day gap, missing data)  
- Ovulation timing uncertain due to recent birth control cessation and treatments

**Message Example:**  
*"Your cycle may still be adjusting after stopping birth control. Ovulation induction affects timing. Keep logging periods for more accurate predictions."*

---

### 3. Recently Stopped Birth Control but Now Stable  
**User Input:**  
- Periods:
  - Nov 1-5
  - Dec 1-5
  - Jan 1-5  
- Stopped birth control 6 months ago
- Last 3 cycles stable at ~30 days
- No fertility treatments

**Prediction:**  
- Regular 30-day cycles restored  
- Next period: ~Feb 1-3  
- Ovulation ~14 days before (Jan 18-20)

**Message Example:**  
*"Your cycles appear stable after stopping birth control months ago. Expect your next period around Feb 2, with ovulation near Jan 19."*

---

### 4. Regular Cycle + Ovulation Induction Medication  
**User Input:**  
- Periods:
  - Nov 15-18
  - Dec 15-18
  - Jan 15-18  
- No birth control  
- Using ovulation induction meds, stable 30-day cycle

**Prediction:**  
- Regular cycle, meds likely enhance predictability  
- Next period: ~Feb 14-16  
- Ovulation: ~Jan 31-Feb 2

**Message Example:**  
*"Your ovulation induction treatment supports a predictable cycle. Expect ovulation around Feb 1 and next period by mid-February."*

---

### 5. Slightly Irregular Cycles, No Birth Control, No Treatments  
**User Input:**  
- Periods:
  - Nov 10-14
  - Dec 13-17
  - Jan 15-19 (cycles vary: 33 days, then 32 days)
- No birth control, no treatments

**Prediction:**  
- Average cycle ~32-33 days, slightly irregular  
- Next period ~Feb 17-20  
- Ovulation ~14 days before next period (around Feb 3-6)

**Message Example:**  
*"Your cycle length varies slightly. We estimate your next period around Feb 18 and ovulation in early February, but these predictions are slightly less certain."*

---

### 6. Very Short Cycles (~21 Days)  
**User Input:**  
- Periods:
  - Nov 1-3
  - Nov 22-24
  - Dec 13-15
- No birth control, no treatments
- Cycle length ~21 days (very short)

**Prediction:**  
- Next period ~Jan 3-5 (21 days after Dec 13)  
- Ovulation ~14 days before Jan 3 → ~Dec 20 (Short cycle means ovulation occurs relatively soon after last period.)

**Message Example:**  
*"Your cycle is short (~21 days). Expect your next period around Jan 4, with ovulation possibly around Dec 20. This shorter cycle means a narrower planning window."*

---

### 7. Very Long Cycles (~35+ Days)  
**User Input:**  
- Periods:
  - Nov 1-5
  - Dec 7-11
  - Jan 13-17
- No birth control, no treatments
- ~35-36 day cycles

**Prediction:**  
- Next period ~Feb 18-22  
- Ovulation ~14 days before (~Feb 4-8)

**Message Example:**  
*"Your cycles are longer (35+ days). You might ovulate around Feb 6, with your next period near Feb 20. Longer cycles mean fewer ovulation events per year."*

---

### 8. Limited Data (Only 2 Months Logged)  
**User Input:**  
- Periods:
  - Dec 10-14
  - Jan 12-16
- No previous data  
- Unsure about birth control usage, no treatments reported

**Prediction:**  
- Only 2 cycles: ~32-day interval  
- Next period ~Feb 13-17  
- Ovulation ~14 days prior (~Jan 30-Feb 2)
- Low confidence due to limited data

**Message Example:**  
*"We have only two cycles on record. Your next period may start around Feb 15, with ovulation in early February. Log more cycles for better accuracy."*

---

### 9. Heavy/Clot Flow Each Month, Regular Cycle  
**User Input:**  
- Periods:
  - Nov 10-15 (Heavy)
  - Dec 10-15 (Clots)
  - Jan 10-15 (Heavy)
- Regular 30-day cycle  
- No birth control or treatments

**Prediction:**  
- Despite heavy/clot flows, cycle is regular (~30 days)
- Next period ~Feb 9-11  
- Ovulation ~Jan 26-28

**Message Example:**  
*"Your cycle is regular at ~30 days, though your flow is heavy. Expect your next period around Feb 10, with ovulation near Jan 27. Heavy flow doesn’t necessarily change ovulation timing, but discuss any concerns with a doctor."*

---

### 10. Changed Birth Control Methods Recently  
**User Input:**  
- Periods:
  - Nov 5-9 (on Pill)
  - Dec 10-14 (switched from Pill to IUD in mid-Nov)
  - Jan 15-19 (post-switch cycle)
- Irregular intervals due to switching methods

**Prediction:**  
- Cycle length fluctuating: 35 days, then 36 days
- Next period ~Feb 20-24
- Ovulation ~14 days prior (~Feb 6-10)
- Low to moderate confidence due to recent method change

**Message Example:**  
*"You recently changed birth control methods, and your cycles are still adjusting. We estimate your next period around Feb 22, with ovulation in early February, but this may not be fully stable yet."*

---

### 11. On IVF (External Factors Override Predictions)  
**User Input:**  
- Periods:
  - Nov 1-5
  - Dec 5-9
  - Jan 8-12
- User undergoing IVF treatment
- Normally ~34-day cycle but IVF schedules may alter timing

**Prediction:**  
- While we can guess next period ~Feb 11-15, IVF protocols may override natural ovulation timing.
- Provide a disclaimer since IVF timing often follows medical protocols rather than natural rhythms.

**Message Example:**  
*"You are currently undergoing IVF. Standard cycle calculations may not apply. Please follow your medical team’s guidance. We estimate your next period around Feb 13, but IVF may change this timing."*

---

## Questions to be Answered by a Medical Professional:

1. Are predictions based on "ovulation ~14 days before the next period" accurate for most users, or should this be adjusted?
2. How long should we consider cycles "unstable" after stopping birth control (e.g., 1-3 cycles, more)?
3. Does heavy or clot-based flow indicate anything about ovulation timing or fertility? If yes, how should we reflect that in predictions?
4. How should we communicate uncertainty when data is sparse or inconsistent? For example, should we provide a wider window for ovulation or explicitly state a "low confidence" prediction?

These questions will help refine our algorithm and ensure it aligns with medical standards and user expectations.
