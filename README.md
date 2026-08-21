# Support Operations Analytics Dashboard

## Project Overview

This project is a Power BI dashboard built to analyze support ticket data and identify operational insights such as ticket volume trends, ticket status, priority distribution, recurring issues, and resolution performance.

The goal is to use support data to identify opportunities for improving support operations and Knowledge Management.

## Key Features

- Total Tickets KPI
- Open Tickets KPI
- Closed Tickets KPI
- Average Resolution Days
- Resolution Rate
- Monthly Ticket Volume Trend
- Open vs Closed Ticket Analysis
- Ticket Priority Distribution
- Top Recurring Issues
- Average Resolution Days by Category
- Ticket Distribution by Channel

## Data Preparation

Power Query was used for:

- Cleaning and transforming raw support ticket data
- Handling blank values in Priority and Category
- Replacing missing categorical values with "Unknown"
- Ensuring date columns had the correct data type
- Creating a Resolution_Days column
- Handling unresolved tickets appropriately

## DAX Measures

The following measures were created:

### Total Tickets

```DAX
Total Tickets = COUNTROWS(SupportTickets)
Open Tickets
Open Tickets =
CALCULATE(
    COUNTROWS(SupportTickets),
    SupportTickets[Status] = "Open"
)
Closed Tickets
Closed Tickets =
CALCULATE(
    COUNTROWS(SupportTickets),
    SupportTickets[Status] = "Closed"
)
Average Resolution Days
Avg Resolution Days =
CALCULATE(
    AVERAGE(SupportTickets[Resolution_Days]),
    SupportTickets[Status] = "Closed"
)
Resolution Rate
Resolution Rate =
DIVIDE(
    [Closed Tickets],
    [Total Tickets],
    0
)
## Key Insights

The dashboard helps identify:

Changes in support ticket volume over time
The proportion of open and closed tickets
Distribution of tickets by priority
Frequently recurring support issues
Categories with longer resolution times
Distribution of tickets across support channels
Knowledge Management Opportunity

Recurring high-volume issues can indicate potential knowledge gaps. These issues can be prioritized for:

Knowledge base articles
FAQs
Troubleshooting guides
Self-service content

This can potentially reduce repetitive support effort and improve customer self-service.

Tech Stack
Power BI
Power Query
DAX
Excel / CSV
SQL
Future Improvements
Add interactive slicers
Add SLA tracking
Add ticket aging analysis
Add agent performance analysis
Implement AI-based ticket categorization
Recommend knowledge articles based on ticket descriptions


## My recommendation


**First save your `.pbix` file properly**, then upload it with this README.


If you want, I can next help you **create the README.md file step-by-step and also tell you how to take a screenshot of your final dashboard and add it to the GitHub README**, which will make your project look much more professional to interviewers.