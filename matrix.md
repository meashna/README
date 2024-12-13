**Table Columns:**

1. Cycle Regularity (CR)  
   - Values: Regular, Slightly Irregular, Highly Irregular

2. Avg Cycle Length (ACL)  
   - Values: Short (<25d), Normal (25–35d), Long (>35d)

3. Flow Patterns (FP)  
   - For simplicity, one of: Very Less, Normal, Heavy, Clots, Heavy + Clots  
   *(In reality, each of the 3 months could have a different flow pattern, exponentially increasing combinations.)*

4. Birth Control (BC)  
   - Values: None, Stopped >3m Ago, Stopped ≤3m Ago, Currently Using  
   *(If “Currently Using,” could split into Pill, IUD, Implant, Injection, etc.)*

5. Fertility Treatment (FT)  
   - Values: None, Ovulation Induction (OI), IUI, IVF, Others

6. Variability (User-Reported) (V)  
   - Values: Stable, Varies a lot

7. Bleeding Duration (BD)  
   - Values: Short (1–3d), Normal (3–5d), Long (>5d)

8. Example Prediction Notes (PN)  
   - A brief note on prediction confidence or adjustments.


**Sample Rows (Just a Few Examples):**

| CR (Cycle Regularity) | ACL (Avg Cycle) | FP (Flow Pattern) | BC (Birth Control)    | FT (Fertility Treatment) | V (Variability) | BD (Bleed Duration) | PN (Prediction Notes)                                                                                 |
|------------------------|-----------------|-------------------|-----------------------|--------------------------|-----------------|---------------------|------------------------------------------------------------------------------------------------------|
| Regular                | Normal (~28d)   | Normal            | None                  | None                     | Stable          | Normal (3–5d)       | High confidence. Ovulation ~14d before next period. Clear fertile window prediction.                   |
| Regular                | Normal (~30d)   | Heavy             | Stopped ≤3m Ago       | None                     | Stable          | Normal (3–5d)       | Moderate confidence. Recent BC stop may shift ovulation slightly. Suggest logging more cycles.         |
| Slightly Irregular     | Normal (~29d)   | Very Less         | None                  | OI (Ovulation Induction) | Varies a lot     | Short (1–3d)        | Medium confidence. OI may help regulate ovulation despite reported variability. Give approximate range.|
| Highly Irregular       | Long (>35d)     | Clots             | Currently Using (IUD) | IVF                      | Varies a lot     | Long (>5d)          | Low confidence. IVF overrides natural cycle predictions; advise following clinic guidelines.           |
| Slightly Irregular     | Short (<25d)    | Heavy+Clots       | Stopped >3m Ago       | IUI                      | Stable          | Long (>5d)          | Medium confidence. Short cycle means ovulation occurs earlier. IUI guidelines may provide more accuracy.|
| Regular                | Short (~23d)    | Normal            | None                  | None                     | Stable          | Short (1–3d)        | High confidence short cycle prediction. Ovulation ~day 9. Inform user about earlier fertile window.    |
| Regular                | Long (~36d)     | Heavy             | None                  | None                     | Stable          | Normal (3–5d)       | Medium confidence. Long cycle = later ovulation (~day 22). Remind user of fewer ovulations per year.   |
| Slightly Irregular     | Normal (~27d)   | Very Less         | Currently Using (Pill)| None                     | Varies a lot     | Normal (3–5d)       | Low confidence. Pill use often suppresses ovulation prediction. Suggest relying on medical advice.     |
| Highly Irregular       | Normal (~30d)   | Clots             | Stopped >3m Ago       | IVF                      | Varies a lot     | Normal (3–5d)       | Low confidence. IVF cycle timing may differ from natural ovulation. Emphasize uncertainty.             |
| Regular                | Normal (~28d)   | Heavy+Clots       | None                  | Others (e.g., meds)      | Stable          | Normal (3–5d)       | Moderate confidence. Special treatments might affect timing slightly. Ovulation ~14d before next period.|
