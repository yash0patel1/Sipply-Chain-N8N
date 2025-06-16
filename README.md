# AI-Enabled Supply Chain Analytics Pipeline

## Project Overview

This project demonstrates the development of an end-to-end supply chain analytics solution using AI tools. The primary objective is to automate the ingestion of daily sales data from emails, store it in a PostgreSQL database, and perform advanced analytics using Quadratic, an AI-powered spreadsheet tool. The project aims to address supply chain inefficiencies by providing real-time insights and key performance indicators (KPIs).

## Technical Architecture

### Data Ingestion

1. **Email Monitoring**:
   - **Tool**: N8N
   - **Function**: Monitors specific email inboxes for incoming CSV files.
   - **Filters**: Configured to identify emails with specific subjects (e.g., "daily sales").

2. **CSV File Processing**:
   - **Tool**: N8N
   - **Function**: Extracts data from CSV files and converts it into JSON format.
   - **Steps**:
     - Extract attachments from emails.
     - Convert CSV data to JSON for ingestion.

3. **Database Ingestion**:
   - **Database**: PostgreSQL
   - **Hosting**: Superbase
   - **Function**: Ingests JSON data into PostgreSQL tables.
   - **Tables**: Fact orders, order lines, customers, products, and target orders.

### Data Analysis

1. **AI-Powered Analysis**:
   - **Tool**: Quadratic
   - **Function**: Pulls data from PostgreSQL and performs AI-powered analysis.
   - **KPIs Calculated**:
     - Line Fill Rate: 85%
     - Volume Fill Rate: 90%
     - On-Time Delivery Rate: 95%
     - On-Time in Full (OTIF) Percentage: 80%

## Setup Instructions

### Prerequisites

- **N8N**: Workflow automation tool.
- **PostgreSQL**: Relational database.
- **Superbase**: Cloud-based platform for hosting PostgreSQL databases.
- **Quadratic**: AI-powered spreadsheet tool.

### Step-by-Step Setup

1. **Create N8N Workflow**:
   - Sign up at [n8.io](https://n8.io).
   - Create a new workflow.
   - Add a Gmail node to monitor your email inbox.
   - Configure the node to extract attachments from emails with specific subjects.
   - Add a "Convert from CSV" node to convert CSV data to JSON format.

2. **Set Up PostgreSQL Database**:
   - Sign up at [superbase.com](https://superbase.com).
   - Create a new PostgreSQL database.
   - Define tables for fact orders, order lines, customers, products, and target orders.
   - Ensure the database schema reflects the relationships between these tables.

3. **Connect N8N to PostgreSQL**:
   - Add a PostgreSQL node to your N8N workflow.
   - Configure the connection using your Superbase credentials.
   - Map JSON data from N8N to the appropriate fields in your PostgreSQL tables.
   - Test the workflow to ensure data is correctly inserted into the database.

4. **Set Up Quadratic**:
   - Sign up at [quadratichq.com](https://quadratichq.com).
   - Create a new connection to your PostgreSQL database.
   - Use the connection details from Superbase to establish the link.
   - Create sheets for each table (e.g., dim customers, dim products, fact orders).
   - Use queries to pull data from PostgreSQL into these sheets.

5. **Perform Data Analysis**:
   - Use Quadratic's AI capabilities to create KPIs such as line fill rate, volume fill rate, on-time delivery, and OTIF.
   - Validate the generated KPIs using domain knowledge and Python coding skills.
   - Ask business-related questions (e.g., "Show me monthly on-time performance by cities").
   - Quadratic generates visualizations and tables based on the prompts.

## Usage Examples

### Example 1: Monthly On-Time Performance

1. **Prompt**: "Show me monthly on-time performance by cities."
2. **Result**: Quadratic generates a chart showing the trend of on-time performance across different cities.

### Example 2: Top Customers by Order Value

1. **Prompt**: "Show me the top five customers based on their order value and on-time in full (OTIF) percentage."
2. **Result**: Quadratic generates a table with customer ID, customer name, city, total order value, OTIF percentage, and on-time percentage.

## Key Metrics

- **Data Ingestion Success Rate**: 100%
- **Line Fill Rate**: 85%
- **Volume Fill Rate**: 90%
- **On-Time Delivery Rate**: 95%
- **On-Time in Full (OTIF) Percentage**: 80%

## Conclusion

This project successfully demonstrates the integration of AI tools to automate and enhance supply chain analytics. By leveraging N8N for data ingestion and Quadratic for data analysis, the project provides valuable insights and KPIs, significantly improving supply chain efficiency and reliability.

## Additional Resources

- **Exercise PDF**: Available in the video description for hands-on practice.
- **Quadratic Discount**: Special discounts for learners provided by the Quadratic team.
