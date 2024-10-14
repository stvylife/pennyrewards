# pennyrewards
tracking/earning commision while monitoring a budget

Project Scope: Task Sidekick

The goal of this project is to build an interactive app that displays dynamic task data from a Google Sheet, handles financial calculations, and tracks tasks and periods for the user. The system includes elements such as a task list, financial summaries, period tracking, a progress bar, and a bouncing ball animation as a loading indicator.

Sheets Structure:

	1.	user_data Sheet:
	•	Columns A-I: General user information (Name, User ID, Pin, etc.).
	•	Column P: Cumulative commission earned (CREDIT 1).
	•	Column Q: Spent amount (DEBIT 1).
	•	Columns AU and AV: Date and period stamp to track button clicks.
	2.	task Sheet:
	•	Columns A-G: Task details (Label, Stock, Type, Price, Extra, Quantity, Total Cost).
	•	The first row contains headers, and subsequent rows contain the data for up to 5 tasks.
	3.	budget Sheet:
	•	Column F2: Number of periods per day (1-4).
	•	Column G2: Operational days (e.g., “0111111” to represent SMTWTFS).
	•	Columns K-N: Period headers and times (e.g., start times for each period).
	•	Column I2: Monthly allowance.
	4.	payscale Sheet:
	•	Column A: Rank (single-digit numbers).
	•	Column B: Corresponding rate to calculate commission.
	5.	history Sheet:
	•	Column A: Date stamp.
	•	Column B: User name stamp.
	•	Column D: Aggregated tasks from the task sheet.
	•	Column E: Quantity.
	•	Columns F-H: Group, Period, and Title of the period.
	•	Columns I-J: Total, Commission.

Functionality Requirements:

	1.	Task Table:
	•	Display task headers and 5 rows of task data from the task sheet (columns A-G).
	•	Dynamically fetch column headers and rows upon page load.
	2.	Financial Calculations:
	•	Display the allowance, commission, spent, subtotal, and remainder (allowance - spent).
	•	Commission is cumulative and calculated based on the user’s rank and the pay scale (from the payscale sheet).
	•	Spent is updated with each task and saved back to the user_data sheet.
	•	Subtotal is calculated as the sum of the Total Cost column in the task sheet.
	3.	Progress Bar:
	•	Reflect the time lapse within the current period dynamically.
	•	Each period lasts for 2 hours, or 8 hours if there is only 1 period per day (as specified in F2 of the budget sheet).
	•	The progress bar updates based on the time remaining in the active period.
	4.	Bouncing Ball Animation:
	•	Used as a loading indicator while data is being fetched.
	•	Should disappear once the task table and financials are fully loaded.
	5.	Period Tracking:
	•	Display the current period and start time based on the active period.
	•	Dynamically update the period header and start time from the budget sheet, columns K-N.
	•	If the button is clicked outside the active period, the button should turn red and display “NOT READY”.
	6.	Button Logic:
	•	Button can only be clicked once per period.
	•	After a valid click, the button text should change to “Task Completed” and turn green.
	•	The date and period stamp are saved to user_data (columns AU and AV), and clicking the button within the same period again should be prevented.
	7.	Error Handling:
	•	Handle and display errors if there are issues with fetching data or if the button is clicked outside the active period.
	•	Display a message to the user if the system is in a “Day Off” (non-operational) based on the value in G2 of the budget sheet.
	8.	Mobile Optimization:
	•	Ensure the UI is responsive and optimized for mobile devices.
	•	Adjust table layout and financial summary to fit smaller screens without breaking the layout.
	9.	History Logging:
	•	After each valid task completion, log the following to the history sheet:
	•	Date, User name, aggregated task description, period number, total, and commission.
	10.	User-Friendly Interface:

	•	Horizontal summary display for allowance, commission, and spent values at the top of the page.
	•	Subtotal and progress bar displayed below the task table.
