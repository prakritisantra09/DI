# 📊 Inventory & Stock Analysis Dashboard

This project is a mini business intelligence dashboard that monitors stock levels, reorder alerts, supplier performance, and inventory movement using *Microsoft Excel* and *Power BI*.

## 📌 Project Overview

The *Inventory & Stock Analysis Dashboard* enables businesses to:
- Track real-time stock levels and reorder status.
- Monitor supplier-wise performance and order lead time.
- Receive alerts for low stock items.
- Visualize key inventory metrics interactively.

## 🛠 Technologies Used

| Tool       | Purpose                                      |
|------------|----------------------------------------------|
| *Excel*  | Store and update inventory data              |
| *Power BI* | Create dynamic visual dashboards and KPIs  |

## 📂 Project Structure


Measures Used in Power BI:
Days Until Next Order
This measure calculates the average lead time for upcoming orders.
Average Lead Time
Days Until Next Order = AVERAGE(Inventory_Data[Lead Time (Days)])


Total Stock
This measure calculates the sum of all available stock in the inventory.
Total Stock
Total Stock = SUM(Inventory_Data[Stock Quantity])


Low Stock Alert Count
This measure counts the number of products where stock is below the reorder level, triggering alerts.
Low Stock Alert Count
Low Stock Alert Count = 
VAR LowStock = COUNTROWS(
    FILTER(Inventory_Data, 
        Inventory_Data[Stock Quantity] < Inventory_Data[Reorder Level]
    )
)
RETURN IF(ISBLANK(LowStock), 0, LowStock)

## 📸 Key Visuals

### 📈 Dashboard Overview
<img src="./screenshots/dashboard_overview.png" width="600">

- Bar chart for *Stock Quantity by Product*
- Pie chart showing *Reorder Level vs Stock*
- Low stock alert KPI
- Lead Time visualization

### 📊 Inventory Data in Excel
<img src="./screenshots/excel_data_sheet.png" width="600">

- Manages stock, reorder levels, and supplier info.
- Contains real-time updates feeding into Power BI.

## 🔄 How It Works

1. 📥 Warehouse staff updates stock levels in *Excel*.
2. ⚡ Power BI auto-refreshes using live Excel data.
3. 🔔 Low stock alerts trigger when inventory drops below reorder level.
4. 📊 Dashboards update in real-time to reflect stock movement and supplier metrics.

## 📌 Features

- 📉 Stock Quantity Trend
- 📦 Reorder Alerts
- ⏱ Lead Time Analysis
- 👨‍💼 Supplier-based Segmentation
- 🔁 Monthly/Quarterly Stock Patterns

## ✅ Requirements

- Microsoft Power BI Desktop
- Microsoft Excel (2016 or newer)

## 💡 Use Cases

- Small warehouse management
- Retail inventory tracking
- Supply chain optimization reports

## 📬 Contact

For feedback or questions, reach out via:
- ✉ Email: your.email@example.com
- 📁 GitHub: [Your GitHub Profile](https://github.com/yourprofile)

---

🔁 *Clone this Repo*
```bash
git clone https://github.com/yourusername/inventory-stock-dashboard.git
