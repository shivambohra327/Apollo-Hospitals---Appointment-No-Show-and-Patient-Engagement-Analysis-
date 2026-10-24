# 🏥 Apollo Hospitals | Appointment Analytics Using Python

## 📌 Project Overview

Every missed hospital appointment represents a challenge for patient care, doctor scheduling, and operational efficiency.

This project explores appointment data from **Apollo Hospitals across 15 cities in India** to understand patient attendance, booking behaviour, reminder effectiveness, financial performance, and doctor utilisation.

Using **Python and Exploratory Data Analysis (EDA)**, this project identifies patterns associated with appointment no-shows and translates data into actionable recommendations for improving healthcare operations.

🎯 **Main objective:** Understand why patients miss appointments and identify opportunities to improve attendance, resource utilisation, and financial performance.

---

## 📊 Dataset at a Glance

| Dataset | Records | Columns | Purpose |
|---|---:|---:|---|
| `apollo_appointments_fact.csv` | 75,000 | 52 | Appointment-level analysis |
| `apollo_doctors_dim.csv` | 320 | 15 | Doctor attributes and service analysis |

**Data relationship:** `doctor_id` is used to join appointment records with doctor-level information when required.

**Analysis period:** 2022–2024

---

## 💼 Business Questions

This project investigates six important areas of healthcare performance.

### 📅 01. Appointment Trends
- How does appointment volume change across months and quarters?
- What proportion of appointments are completed, missed, cancelled, or still scheduled?
- Which booking channels contribute the most appointments?

### 🚨 02. No-Show Analysis
- Which specialties and cities have the highest no-show rates?
- Does longer booking lead time increase the likelihood of a missed appointment?
- Are evening and weekend appointments associated with higher no-show rates?
- Which booking channels and appointment types show higher dropout?

### 📲 03. Reminder & Patient Engagement
- How do reminder types compare with appointments receiving no reminder?
- Does previous no-show history help identify patients who may miss future appointments?
- Do members and repeat patients demonstrate different attendance patterns?

### 👥 04. Patient Segmentation
- How do age, gender, and chronic condition status relate to attendance?
- Which visit reasons are most common?
- How does the age distribution vary across Paediatrics, Gynaecology, and Psychiatry?

### 💰 05. Financial Performance
- What is the estimated financial exposure associated with no-shows?
- Which specialties, appointment types, and cities generate the most realised revenue?
- How are payments distributed across payment methods?
- How does insurance coverage relate to out-of-pocket payments?

### 🩺 06. Doctor Utilisation & Service Quality
- Which specialties have the highest and lowest doctor utilisation?
- How does patient waiting time vary by specialty and time of day?
- Is consultation duration associated with patient satisfaction?
- How does doctor experience relate to standard consultation fees?

---

## 🛠️ Tools & Technologies

| Tool | Application |
|---|---|
| 🐍 Python | Analysis and data processing |
| 🧮 Pandas | Data cleaning, merging, grouping, and aggregation |
| 🔢 NumPy | Numerical operations and derived metrics |
| 📈 Matplotlib | Charts and trend visualisation |
| 🎨 Seaborn | Statistical and comparative visualisations |
| 📓 Jupyter Notebook | Interactive analysis and documentation |
| 📊 SciPy | Statistical analysis, where applicable |

---

## 🔍 Project Workflow

```text
Raw Datasets
     ↓
Data Loading & Inspection
     ↓
Data Cleaning & Validation
     ↓
Feature Engineering
     ↓
Exploratory Data Analysis
     ↓
No-Show & Patient Behaviour Analysis
     ↓
Financial & Operational Analysis
     ↓
Business Insights & Recommendations
```

---

## 🌟 Key Insights

The following figures are **preliminary results reported by the uploaded notebook** and should be revalidated after correcting the data-processing issues.

### 📌 Appointment Outcomes

| Appointment Status | Reported Count | Share |
|---|---:|---:|
| Completed | 55,275 | 73.7% |
| No-Show | 11,584 | 15.4% |
| Cancelled | 5,793 | 7.7% |
| Scheduled | 2,348 | 3.1% |

### 🚨 No-Show Patterns

- **Specialty:** Psychiatry has a reported no-show rate of 24.5%, while Neurology has 10.7%.
- **City:** Lucknow has a reported no-show rate of 17.2%, compared with 13.3% in Pune.
- **Booking lead time:** The reported no-show rate increases from 13.2% for one-day-ahead bookings to 20.0% for bookings made 15–30 days in advance.
- **Appointment timing:** Evening appointments have a reported 18.4% no-show rate, compared with 13.7% for morning appointments.
- **Previous behaviour:** Patients with three or more prior no-shows have a reported 32.7% no-show rate, compared with 15.2% for patients with no prior no-shows.

### 📲 Reminder Effectiveness

The notebook reports an 11.4% no-show rate for appointments receiving SMS, WhatsApp, and call reminders, compared with 30.2% for appointments receiving no reminder.

That represents an **18.8 percentage-point observed difference**. Further testing is needed to determine how much of the difference is attributable to reminders rather than other patient or booking characteristics.

### 💰 Financial Analysis

The notebook reports approximately ₹1.97 crore in listed consultation-fee value associated with no-show appointments and a separate estimate of approximately ₹1.57 crore in potential revenue exposure based on completed-appointment revenue assumptions.

These are different estimates, not confirmed accounting losses. They require validation before being used for financial reporting.

> **Data quality note:** All figures above are provisional. The notebook contains an appointment-status case mismatch and inconsistent lead-time labels. Correct these issues and rerun all cells before publishing final results.

---

## 💡 Business Recommendations

Based on the patterns explored, the following opportunities could be tested:

- **Smart reminders:** Test reminder strategies for patient segments with higher observed no-show rates.
- **Advance-booking follow-ups:** Introduce appointment reconfirmation for bookings made well in advance.
- **Specialty-level investigation:** Review workflows in specialties with higher no-show rates.
- **Flexible rescheduling:** Make it easier for patients to cancel or reschedule before their appointment time.
- **Patient engagement:** Offer supportive follow-ups to patients with repeated no-shows.
- **Capacity optimisation:** Use historical attendance patterns to improve doctor scheduling and manage waitlists.
- **Financial monitoring:** Track realised revenue separately from estimated missed-appointment value.

These are proposed actions for evaluation, not interventions proven by this analysis.

---

## ⚙️ Important Data Handling Rules

To maintain accurate analysis, this project follows the dataset's stated business rules:

- **No-show rate:**  
  `No-Show Count / (Completed + No-Show + Cancelled Count)`

- Scheduled appointments are excluded from the no-show rate denominator.

- Waiting time, satisfaction, consultation duration, and doctor utilisation are analysed only for **Completed** appointments.

- Revenue analysis is restricted to **Completed** appointments because revenue values are zero for non-completed records.

- Doctor attributes are joined using `doctor_id` when required.

- `None` in chronic condition, membership type, insurance provider, and cancellation reason may mean **not applicable**, rather than missing data.

---

## 🚀 How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/apollo-hospitals-appointment-eda.git
cd apollo-hospitals-appointment-eda
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scipy jupyter
```

### 3. Download the Datasets

Obtain the two CSV files from the authorised project data source and place them in a local `data/` directory.

### 4. Open the Notebook

```bash
jupyter notebook
```

Open `Apollo_Hospitals_EDA_Notebook.ipynb`, update the file paths if needed, and run all cells from beginning to end.

---

## 📁 Recommended Repository Structure

```text
apollo-hospitals-appointment-eda/
│
├── README.md
├── Apollo_Hospitals_EDA_Notebook.ipynb
├── requirements.txt
├── data/
│   └── README.md
└── images/
    ├── appointment_trends.png
    ├── no_show_analysis.png
    └── reminder_effectiveness.png
```

*The `images/`, `requirements.txt`, and `data/README.md` files are recommended additions. Add them only after creating the files.*

---

## 🎓 Skills Demonstrated

- Exploratory Data Analysis (EDA)
- Data cleaning and validation
- Data manipulation with Pandas and NumPy
- Feature engineering and segmentation
- Appointment and time-series analysis
- Healthcare operational analytics
- Financial KPI analysis
- Data visualisation and statistical interpretation
- Business insight generation
- Communicating findings to non-technical stakeholders

---

## ⚠️ Limitations

- Findings are based on the supplied dataset and may not represent current Apollo Hospitals performance.
- Observed relationships do not establish causation.
- Revenue exposure is an estimate, not an audited financial loss.
- Final results require successful rerunning and validation of the notebook.
- This project is for educational and portfolio purposes, not clinical decision-making.

---

## 🏁 Conclusion

This project demonstrates how Python-based analytics can help healthcare organisations understand appointment attendance, patient engagement, scheduling behaviour, financial exposure, and doctor utilisation.

By examining patterns across booking channels, reminders, lead times, specialties, cities, and patient segments, the analysis provides a foundation for data-driven operational improvements and further investigation.

**The goal is not just to analyse appointment data, but to turn it into practical questions and measurable opportunities for better healthcare service delivery.**

---

## 👨‍💻 Author

**Shivam Bohra**

*Aspiring Data Analyst | Python | SQL | Power BI | Data Analytics*
  <sub>Built with Python, curiosity, and a data-driven mindset.</sub>
</p>
