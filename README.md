# 📅 Date and Time Analysis Using DAX in Power BI
![Date and time analysis image](https://github.com/user-attachments/assets/e7b7a47e-277f-43ba-9c56-69245938dfd2)

## 📌 Overview  
This project provides a comprehensive guide on **Date and Time functions in DAX**, essential for **Power BI** and **business intelligence analytics**. It covers **date creation, manipulation, and advanced time-based calculations**.

## 🚀 Features  
✔ **Create dynamic Date Tables** using `CALENDAR` and `CALENDARAUTO`.  
✔ **Extract date parts** (`YEAR`, `MONTH`, `DAY`).  
✔ **Perform time calculations** (`DATEDIFF`, `NOW`, `TODAY`).  
✔ **Manipulate dates dynamically** (`EOMONTH`, `EDATE`).  
✔ **Calculate working/business days** (`NETWORKDAYS`).  
✔ **Week-based operations** (`WEEKDAY`, `WEEKNUM`).  

---
Detailed README.md
markdown
Copy
Edit
# 📅 Date and Time Analysis Using DAX in Power BI

## 📌 Overview  
This project provides a comprehensive guide on **Date and Time functions in DAX**, essential for **Power BI** and **business intelligence analytics**. It covers **date creation, manipulation, and advanced time-based calculations**.

## 🚀 Features  
✔ **Create dynamic Date Tables** using `CALENDAR` and `CALENDARAUTO`.  
✔ **Extract date parts** (`YEAR`, `MONTH`, `DAY`).  
✔ **Perform time calculations** (`DATEDIFF`, `NOW`, `TODAY`).  
✔ **Manipulate dates dynamically** (`EOMONTH`, `EDATE`).  
✔ **Calculate working/business days** (`NETWORKDAYS`).  
✔ **Week-based operations** (`WEEKDAY`, `WEEKNUM`).  

---

## 📂 File Structure  
dax-date-time-analysis/ │── README.md # Detailed project documentation │── LICENSE # Open-source license (MIT recommended) │── docs/ # Documentation and reports │ ├── Date and Time Analysis.docx # Original document │── scripts/ # DAX formulas and queries │ ├── calendar-dax.dax # CALENDAR & CALENDARAUTO formulas │ ├── date-functions.dax # DATE, DATEDIFF, DATEVALUE, etc. │ ├── time-functions.dax # NOW, TODAY, NETWORKDAYS, etc. │── examples/ # Sample Power BI reports or visualizations │ ├── date-analysis.pbix # Power BI file with applied functions │ ├── screenshots/ # Screenshots of results │── .gitignore # Ignore unnecessary files (e.g., Power BI cache)


## 📊 DAX Functions Used  

### **🗓️ Creating a Date Table**

DateTable = CALENDAR(DATE(2025,1,1), DATE(2025,12,31))

📆 Auto-Generating a Date Table

CalendarAutoTable = CALENDARAUTO()
📅 Date Extraction Functions

DAX

Year = YEAR('Calendar'[Date])

MonthNum = MONTH('Calendar'[Date])

MonthName = FORMAT('Calendar'[Date], "MMMM")

DayNum = DAY('Calendar'[Date])

⏳ Date Differences
DAX

DaysBetween = DATEDIFF('Sales'[StartDate], 'Sales'[EndDate], DAY)

🕒 Getting Current Date & Time

DAX

CurrentDate = TODAY()

CurrentDateTime = NOW()

🕵️‍♂️ Last Day of Month (EOMONTH)

DAX

EndOfMonth = EOMONTH('Calendar'[Date], 0)

StartOfNextMonth = EOMONTH('Calendar'[Date], 0) + 1

📅 First Day of the Month

DAX

FirstDayOfMonth = DATE(YEAR('Calendar'[Date]), MONTH('Calendar'[Date]), 1)

📅 Workdays Calculation

DAX

WorkDays = NETWORKDAYS(DATE(2023,1,1), TODAY(), 1, HolidaysTable)

🗓️ Week-Based Calculations

DAX

WeekdayNumber = WEEKDAY('Calendar'[Date], 1)

WeekNumber = WEEKNUM('Calendar'[Date], 2)

📸 Screenshots
![Date and time analysis image](https://github.com/user-attachments/assets/ff6952a1-cc77-4d69-8af3-cb4800f440af)

⚖️ License

This project is licensed under the MIT License – feel free to use, modify, and contribute!

🤝 Contributing

Want to add more time-based functions? Feel free to submit a Pull Request! 🚀

📩 Contact

📧 Email: allanotieno2001@gmail.com

🌐 GitHub: AllanOtieno254

 
