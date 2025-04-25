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
