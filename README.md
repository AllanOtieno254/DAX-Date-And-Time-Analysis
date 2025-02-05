# 📅 Date & Time Analysis Using DAX in Power BI

## 📌 Overview  
This project is a **comprehensive guide to Date & Time functions in DAX**, essential for **Power BI** and **business intelligence analytics**.  
It covers **date creation, manipulation, and advanced time-based calculations** for analytics, reporting, and performance tracking.  
![Date and time analysis image](https://github.com/user-attachments/assets/c51e6626-5aa2-49ae-9d76-1e48dd8fe54a)

---

## 🚀 Key Features  
✔ **Automatically create a Date Table** using `CALENDAR` & `CALENDARAUTO`.  
✔ **Extract date parts** (`YEAR`, `MONTH`, `DAY`, `WEEKNUM`).  
✔ **Perform time-based calculations** (`DATEDIFF`, `NOW`, `TODAY`).  
✔ **Manipulate dates dynamically** (`EOMONTH`, `EDATE`).  
✔ **Calculate working/business days** (`NETWORKDAYS`).  
✔ **Week-based operations** (`WEEKDAY`, `WEEKNUM`).  
✔ **Fiscal Year & Quarter calculations** for **financial reports**.  

---


---

## 📊 **DAX Functions Used & Examples**  

### **1️⃣ Creating a Date Table (Fundamental Step)**
This generates a **complete Date Table** in Power BI:  

2️⃣ Automatically Generating a Date Table
If you want Power BI to detect the earliest & latest dates automatically:

DAX
Copy
Edit
CalendarAutoTable = CALENDARAUTO()
✅ No need to define start & end dates.
✅ Power BI determines dates based on existing data.

3️⃣ Extracting Date Parts
Use these DAX functions to extract specific parts of a date:

DAX
Copy
Edit
Year = YEAR('Calendar'[Date])
MonthNumber = MONTH('Calendar'[Date])
MonthName = FORMAT('Calendar'[Date], "MMMM")
DayNumber = DAY('Calendar'[Date])
WeekNumber = WEEKNUM('Calendar'[Date], 2)  -- Uses Monday as start of the week
DayOfWeek = FORMAT('Calendar'[Date], "dddd") -- Returns "Monday", "Tuesday", etc.
✅ Helps in grouping data by year, month, day, or week.
✅ WEEKNUM([Date],2) ensures ISO standard weeks (Monday as start).

4️⃣ Calculating Date Differences
To find the number of days, months, or years between two dates:

DAX
Copy
Edit
DaysBetween = DATEDIFF('Sales'[StartDate], 'Sales'[EndDate], DAY)
MonthsBetween = DATEDIFF('Sales'[StartDate], 'Sales'[EndDate], MONTH)
YearsBetween = DATEDIFF('Sales'[StartDate], 'Sales'[EndDate], YEAR)
✅ Useful for subscription duration, customer retention, and project timelines.

5️⃣ Getting the Current Date & Time
To fetch the current system date & time:

DAX
Copy
Edit
CurrentDate = TODAY()   -- Returns today's date (No time)
CurrentDateTime = NOW() -- Returns current date & time
✅ TODAY() gives today's date without time.
✅ NOW() includes the time component.

6️⃣ End of Month (EOMONTH)
To get the last day of the month:

DAX
Copy
Edit
EndOfMonth = EOMONTH('Calendar'[Date], 0)  -- Last day of the same month
NextMonthEnd = EOMONTH('Calendar'[Date], 1) -- Last day of next month
PreviousMonthEnd = EOMONTH('Calendar'[Date], -1) -- Last day of previous month
✅ Critical for financial reporting and tracking month-end values.

7️⃣ First Day of the Month
To get the first day of any given month:

DAX
Copy
Edit
FirstDayOfMonth = DATE(YEAR('Calendar'[Date]), MONTH('Calendar'[Date]), 1)
✅ Ensures consistency in monthly trend analysis.

8️⃣ Calculating Working Days (NETWORKDAYS)
To find the number of business days between two dates:

DAX
Copy
Edit
WorkDays = NETWORKDAYS(DATE(2023,1,1), TODAY(), 1, HolidaysTable)
The 1 means that weekends are Saturday & Sunday.
You can exclude holidays using a separate HolidaysTable.
✅ Used for project deadlines, workforce planning, and business analytics.

9️⃣ Fiscal Year & Quarter Calculations
Fiscal Year (starting in July):

DAX
Copy
Edit
FiscalYear = "FY" & YEAR('Calendar'[Date]) + IF(MONTH('Calendar'[Date]) >= 7, 1, 0)
Fiscal Quarter (aligned with fiscal year start):

DAX
Copy
Edit
FiscalQuarter = 
    "FQ" & 
    SWITCH(
        TRUE(),
        MONTH('Calendar'[Date]) IN {7,8,9}, 1,
        MONTH('Calendar'[Date]) IN {10,11,12}, 2,
        MONTH('Calendar'[Date]) IN {1,2,3}, 3,
        MONTH('Calendar'[Date]) IN {4,5,6}, 4
    )
✅ Essential for financial analysis & quarterly reports.

📸 Screenshots of the Analysis
![Date and time analysis image](https://github.com/user-attachments/assets/ef99572b-34d2-49df-a963-f95d2197b2ec)

🛠 How to Use
1️⃣ Import the DateTable DAX formula into Power BI.
2️⃣ Mark it as a Date Table (Modeling → Mark as Date Table).
3️⃣ Use the functions above to enhance your Power BI reports.

⚖️ License
This project is licensed under the MIT License – feel free to use, modify, and contribute!

🤝 Contributing
Want to add more time-based functions?

Fork the repo
Make your changes
Submit a Pull Request 🚀
📩 Contact
📧 Email: allanotieno2001@gmail.com
🌐 GitHub: AllanOtieno254

yaml
Copy
Edit


