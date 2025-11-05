# Martha's Vineyard Snowflake Tutorial

This tutorial demonstrates Snowflake fundamentals including database/schema/table creation, stage management, data loading, and visualization.

## 📋 Files Included

1. **MarthasVineyard_Tutorial.ipynb** - Main tutorial notebook
2. **grape_types.csv** - Grape variety data (5 records)
3. **annual_yield.csv** - 5-year production and financial data (10 records)

## 🚀 Quick Start

### Step 1: Execute SQL Setup (SQL Cell)
Run the first SQL cell to create:
- Database: `MarthasVineyard`
- Schema: `MyVineyard`
- Table 1: `grape_types` - stores grape varieties
- Table 2: `annual_yield` - tracks production metrics, costs, earnings, and profits
- Stage: `vineyard_stage` - for file storage

### Step 2: Upload Files to Stage
Upload the CSV files using Snowflake UI:
1. Navigate to: Data → Databases → MarthasVineyard → MyVineyard → Stages → vineyard_stage
2. Upload `grape_types.csv`
3. Upload `annual_yield.csv`

### Step 3: Execute COPY INTO Commands (SQL Cells)
Run the two COPY INTO cells to load data from stage into tables:
- Cell 1: Loads grape types
- Cell 2: Loads annual yield data

### Step 4: Establish Connection (Python Cell)
Runs the connection cell using `snowflake.connector.get_active_connection()`

### Step 5: Verify Data & Visualizations
The remaining Python cells:
- Query and display loaded data
- Create 5-year yield trend visualization
- Create profitability analysis chart
- Generate revenue summary with bar charts

## 📊 Data Schema

### grape_types Table
| Column | Type | Description |
|--------|------|-------------|
| grape_id | INT | Unique identifier |
| grape_name | VARCHAR | Grape variety name |
| grape_type | VARCHAR | Red or White wine grape |
| description | VARCHAR | Grape characteristics |

### annual_yield Table
| Column | Type | Description |
|--------|------|-------------|
| year | INT | Year (2020-2024) |
| grape_id | INT | Foreign key to grape_types table |
| yield_tons | DECIMAL | Production in tons |
| production_cost | DECIMAL | Cost in USD |
| earnings | DECIMAL | Revenue in USD |
| profit | DECIMAL | Net profit in USD |

## 🔧 Troubleshooting

### Connection Issues
- Ensure you're using Snowflake Notebooks or connected via `get_active_connection()`
- Update warehouse configuration if needed

### File Upload Issues
- Verify CSV files are in the workspace directory
- Use full paths if files are in different locations
- Check stage permissions in Snowflake

### Data Load Issues
- Verify file format (comma-separated, header row)
- Check for encoding issues (UTF-8 recommended)
- Review error messages in COPY INTO output

## 📈 Visualizations Generated

1. **Five-Year Yield Trend** - Line chart showing yield tons by grape variety
2. **Profitability Trend** - Line chart showing profit trends over 5 years
3. **Revenue Comparison** - Bar charts comparing total earnings and profits

## 🧹 Cleanup (Optional)

Uncomment the SQL in the "Optional: Additional Cleanup Commands" section to drop:
- Tables
- Schema
- Database

## 📝 Notes

- The tutorial uses `get_active_connection()` which works in Snowflake Notebooks
- All SQL is compatible with standard Snowflake SQL
- Data formats use IF NOT EXISTS for idempotency
- Visualizations use matplotlib for rendering

## ✅ Requirements

- Snowflake account with appropriate permissions
- Snowflake Notebooks or Python with `snowflake-connector-python` installed
- pandas and matplotlib libraries for Python cells

