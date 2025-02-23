# Cleaning Bank Marketing Campaign Data

## Project Overview
This project focuses on cleaning and preparing bank marketing campaign data for efficient storage and analysis. The dataset was provided in a raw CSV format, and the goal was to ensure it adheres to a specific structure and data types before being stored in a PostgreSQL database.

## Dataset and Cleaning Process
The original dataset, `bank_marketing.csv`, contained information about clients, their responses to marketing campaigns, and economic indicators. The data was cleaned and split into three structured CSV files:

### 1. `client.csv`
Contains information about individual clients.

| Column Name | Data Type | Description | Cleaning Process |
|-------------|----------|-------------|-------------------|
| `client_id` | Integer  | Unique Client ID | N/A |
| `age` | Integer  | Client's age in years | N/A |
| `job` | Object  | Client's job type | Replaced `.` with `_` |
| `marital` | Object  | Marital status | N/A |
| `education` | Object  | Education level | Replaced `.` with `_`, changed `unknown` to `NaN` |
| `credit_default` | Boolean  | Credit default status | Converted `"yes"` to `1`, otherwise `0` |
| `mortgage` | Boolean  | Existing mortgage status | Converted `"yes"` to `1`, otherwise `0` |

### 2. `campaign.csv`
Contains details of marketing campaign interactions.

| Column Name | Data Type | Description | Cleaning Process |
|-------------|----------|-------------|-------------------|
| `client_id` | Integer  | Unique Client ID | N/A |
| `number_contacts` | Integer  | Contact attempts in current campaign | N/A |
| `contact_duration` | Integer  | Last contact duration (seconds) | N/A |
| `previous_campaign_contacts` | Integer  | Contacts in previous campaign | N/A |
| `previous_outcome` | Boolean  | Outcome of previous campaign | Converted `"success"` to `1`, otherwise `0` |
| `campaign_outcome` | Boolean  | Outcome of current campaign | Converted `"yes"` to `1`, otherwise `0` |
| `last_contact_date` | Datetime  | Last contact date | Created from `day`, `month`, and fixed `year=2022`, formatted as `YYYY-MM-DD` |

### 3. `economics.csv`
Contains economic indicators related to the campaign period.

| Column Name | Data Type | Description | Cleaning Process |
|-------------|----------|-------------|-------------------|
| `client_id` | Integer  | Unique Client ID | N/A |
| `cons_price_idx` | Float  | Consumer price index | N/A |
| `euribor_three_months` | Float  | Three-month Euribor rate | N/A |

## Technologies Used
- **Python** (for data cleaning and preprocessing)
- **Pandas** (for data manipulation)
- **NumPy** (for handling missing values)
- **PostgreSQL** (target database for cleaned data)

## Acknowledgments
This project is part of a DataCamp learning module on data cleaning. Special thanks to DataCamp for providing the dataset and structured learning materials.

---
