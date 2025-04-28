

# 🎯 Tumhara Final README Content:

```markdown
# Panic Attacks Data Analysis Dashboard

### 📊 Dashboard Link
[View the Dashboard](https://app.powerbi.com/links/ZX9NBiqbKi?ctid=902549a3-b690-4dc6-b1fc-d8522ac75e80&pbi_source=linkShare)

---

## 🛠 Problem Statement

Panic attacks are sudden, intense episodes of fear that significantly impact the well-being of individuals.  
Analyzing patterns related to panic attacks — their symptoms, triggers, demographics, and severity — can help healthcare providers better design interventions and treatment plans.

This dashboard aims to uncover key insights into panic attack occurrences, associated symptoms, and patient behavior patterns using real-world healthcare data sourced from a Snowflake database.

---

## 🛤 Steps Followed

- Data ingestion from **Snowflake Cloud Data Warehouse** into Power BI Desktop.
- Data transformation and cleansing using **Power Query Editor**:
  - Handled missing values, corrected data types.
- Development of critical **DAX Measures** for:
  - Symptom-wise patient distribution
  - Average Panic Scores
  - Attack Frequency analysis across demographics
- Visualization design split into 3 major dashboards focusing on symptoms, miscellaneous lifestyle factors, and demographic influences.
- Slicers implemented for gender, trigger reasons, medical history, and panic score levels.
- Published to **Power BI Service** for online sharing and collaboration.

---

## 📈 Insights Derived

- **Common Symptoms:**  
  Dizziness, trembling, shortness of breath, sweating, and chest pain were commonly reported symptoms among patients.

- **Lifestyle Factors:**  
  - Number of drinks consumed per week and lesser sleep hours showed some correlation with panic attack intensity and frequency.
  - Shorter sleep durations (4–6 hours) were common among high-frequency patients.

- **Panic Attack Duration:**  
  Most panic attacks lasted between 20–30 minutes.

- **Age Group Analysis:**  
  - Adolescents and Adults showed varied average sleep hours, panic scores, and attack frequencies.
  - Social Anxiety and Phobia were among the most common trigger reasons across age groups.

- **Gender Distribution:**  
  Slight variations were observed among male, female, and non-binary patients across symptom reporting.

---

## 📸 Dashboard Visuals

### Dashboard 1 - Number of Patients by Symptom Selected

Analysis of the number of patients reporting different symptoms such as dizziness, trembling, sweating, and chest pain.

![Image](https://github.com/user-attachments/assets/49ffcd29-4298-49c3-9a7e-db1f081db7ae)

---

### Dashboard 2 - Number of Patients by Miscellaneous Reasons

Breakdown of patients based on lifestyle factors like:
- Number of Drinks per Week
- Sleep Hours per Day
- Panic Attack Duration (minutes)

![Image](https://github.com/user-attachments/assets/85bd18af-eb66-4aa5-a3fd-cb19ac22fc56)

---

### Dashboard 3 - Average of Sleep Hours, Panic Score, and Panic Attack Frequency by Age Groups

Comparative analysis of averages based on triggers like Caffeine, Phobia, PTSD, and Social Anxiety across different age groups.

![Image](https://github.com/user-attachments/assets/38a22088-e641-40a4-80a6-1f29eac300b6)

---

## 🧠 Key DAX Measures Used

1. **Number of Patients Having Dizziness:**
```DAX
Dizziness_Count = 
CALCULATE(
    COUNTROWS('Panic_Attack_Data'),
    'Panic_Attack_Data'[Dizziness] = TRUE()
)
```

2. **Number of Patients by Sleep Hours:**
```DAX
Patients_by_Sleep_Hours = 
SUMMARIZE(
    'Panic_Attack_Data',
    'Panic_Attack_Data'[SleepHours],
    "Patient_Count", COUNT('Panic_Attack_Data'[PatientID])
)
```

3. **Average Panic Score by Age Group:**
```DAX
Avg_Panic_Score = 
AVERAGEX(
    FILTER('Panic_Attack_Data', NOT(ISBLANK('Panic_Attack_Data'[PanicScore]))),
    'Panic_Attack_Data'[PanicScore]
)
```

4. **Average Panic Attack Frequency by Trigger Reason:**
```DAX
Avg_Panic_Attack_Frequency = 
AVERAGEX(
    FILTER('Panic_Attack_Data', NOT(ISBLANK('Panic_Attack_Data'[AttackFrequency]))),
    'Panic_Attack_Data'[AttackFrequency]
)
```



# 📢 Notes

- This healthcare-focused dashboard provides a real-time overview of panic attack patterns among patients.
- It enables healthcare professionals to:
  - Identify critical symptoms
  - Understand risk factors related to lifestyle
  - Strategize effective intervention methods for different patient groups
- Developed using Power BI Desktop with cloud-based data ingestion from Snowflake.




