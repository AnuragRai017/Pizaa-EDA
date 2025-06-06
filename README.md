# 🍕 Pizza Delivery Analytics Dashboard

A comprehensive analytics platform for pizza delivery operations featuring exploratory data analysis, machine learning models, and interactive dashboards.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Data Requirements](#data-requirements)
- [Usage](#usage)
- [Components](#components)
- [Dashboard Types](#dashboard-types)
- [Machine Learning Models](#machine-learning-models)
- [Key Metrics](#key-metrics)
- [Contributing](#contributing)
- [License](#license)

## 🔍 Overview

This project provides a complete analytics solution for pizza delivery businesses, enabling data-driven decision making through:

- **Comprehensive EDA**: Deep dive into sales patterns, delivery performance, and customer behavior
- **Machine Learning**: Predictive models for delivery time estimation and customer segmentation
- **Interactive Dashboards**: Real-time visualizations for operational insights
- **Performance Analytics**: KPI tracking and business intelligence reporting

## ✨ Features

### 📊 Exploratory Data Analysis (EDA)
- Sales trends and patterns analysis
- Delivery performance metrics
- Customer behavior insights
- Geographic distribution analysis
- Time series analysis (hourly, daily, weekly, monthly)

### 🤖 Machine Learning
- **Delivery Time Prediction**: Random Forest, Gradient Boosting, Linear Regression
- **Demand Forecasting**: Time series forecasting for order volume
- **Customer Segmentation**: K-means clustering based on order behavior
- **Route Optimization**: Delivery efficiency analysis

### 📈 Interactive Dashboards
- **Executive Dashboard**: High-level KPIs and business metrics
- **Operational Dashboard**: Day-to-day operational insights
- **Performance Dashboard**: Delivery performance and efficiency metrics
- **Time Series Dashboard**: Temporal patterns and trends
- **Geographic Dashboard**: Location-based analytics

## 🚀 Installation

### Prerequisites
```bash
Python 3.8+
```

### Required Libraries
```bash
pip install pandas numpy matplotlib seaborn plotly
pip install scikit-learn openpyxl xlrd
pip install datetime warnings os random
```

### Installation Steps
1. Clone or download the project files
2. Install required dependencies
3. Ensure your Excel data file is in the project directory
4. Run the main analysis scripts

## 📄 Data Requirements

### Expected Data Format
The system expects an Excel file with the following columns:

| Column Name | Type | Description |
|-------------|------|-------------|
| Order ID | String | Unique order identifier |
| Restaurant Name | String | Name of the restaurant |
| Order Time | DateTime | Timestamp of order placement |
| Delivery Time | DateTime | Timestamp of delivery completion |
| Location | String | Delivery address |
| Pizza Type | String | Type of pizza ordered |
| Pizza Size | String | Size of pizza (Small, Medium, Large, etc.) |
| Distance (km) | Float | Delivery distance in kilometers |
| Delivery Duration (min) | Float | Total delivery time in minutes |
| Delay (min) | Float | Delay from expected delivery time |
| Traffic Level | String | Traffic condition (Low, Medium, High) |
| Payment Method | String | Payment method used |
| Toppings Count | Integer | Number of toppings |
| Pizza Complexity | Float | Complexity score of the pizza |

### Sample Data Structure
```
Order ID, Restaurant Name, Order Time, Pizza Type, Pizza Size, Distance (km), Delivery Duration (min), ...
ORD001, Pizza Palace, 2024-01-15 12:30:00, Margherita, Large, 5.2, 25, ...
```

## 💻 Usage

### Basic Analysis
```python
# Run complete EDA analysis
from pizza_eda import PizzaSalesAnalyzer

analyzer = PizzaSalesAnalyzer('your_data_file.xlsx')
analyzer.run_complete_analysis()
```

### Machine Learning Analysis
```python
# Run ML analysis
from pizza_eda import PizzaMLAnalyzer

ml_analyzer = PizzaMLAnalyzer('your_data_file.xlsx')
ml_analyzer.run_complete_ml_analysis()
```

### Interactive Dashboard
```python
# Launch interactive dashboards
from pizza_eda import PizzaDashboard

dashboard = PizzaDashboard('your_data_file.xlsx')
dashboard.run_all_dashboards()
```

## 🧩 Components

### 1. PizzaSalesAnalyzer
Main EDA class providing:
- Data preparation and cleaning
- Sales analysis and trends
- Time series analysis
- Delivery performance analysis
- Customer behavior analysis
- Business recommendations

### 2. PizzaMLAnalyzer
Machine learning class offering:
- Delivery time prediction models
- Demand forecasting
- Customer segmentation
- Optimization recommendations

### 3. PizzaDashboard
Interactive dashboard class featuring:
- Multiple dashboard types
- Real-time visualizations
- Interactive filters and controls
- Comprehensive reporting

## 📊 Dashboard Types

### 👨‍💼 Executive Dashboard
- Daily order trends
- Restaurant performance comparison
- Key performance indicators
- Geographic distribution
- High-level business metrics

### ⚙️ Operational Dashboard
- Traffic impact analysis
- Distance vs delivery time correlation
- Peak hour performance
- Payment method preferences
- Pizza size distribution

### 📈 Performance Dashboard
- On-time delivery rate KPI gauge
- Weekly performance trends
- Restaurant efficiency rankings
- Delay analysis by traffic level
- Delivery speed metrics

### ⏰ Time Series Dashboard
- Daily order volume trends
- Hourly pattern heatmaps
- Monthly trends with dual metrics
- Seasonal performance analysis

### 🗺️ Geographic Dashboard
- City-wise order distribution
- Location-based performance metrics
- Distance vs duration analysis
- Regional efficiency comparison

## 🤖 Machine Learning Models

### Delivery Time Prediction
- **Random Forest Regressor**: Best performing model for delivery time estimation
- **Gradient Boosting**: Alternative ensemble method
- **Linear Regression**: Baseline model for comparison

### Performance Metrics
- Mean Absolute Error (MAE)
- Root Mean Square Error (RMSE)
- R² Score

### Feature Importance
Top factors affecting delivery time:
1. Distance (km)
2. Traffic Level
3. Pizza Complexity
4. Order Hour
5. Restaurant efficiency

## 📏 Key Metrics

### Business KPIs
- **On-Time Delivery Rate**: Target >90%
- **Average Delivery Time**: Minutes from order to delivery
- **Customer Satisfaction**: Based on delivery performance
- **Operational Efficiency**: Orders per hour, delivery speed

### Performance Indicators
- Daily order volume
- Peak hour identification
- Restaurant efficiency rankings
- Geographic performance patterns
- Seasonal trends

## 📁 File Structure
```
pizza_delivery_analytics/
├── pizza_eda.ipynb          # Main Jupyter notebook with all analysis
├── README.md                # This file
├── Enhanced_pizza_sell_data_2024-25.xlsx  # Sample data file
└── outputs/                 # Generated visualizations and reports
    ├── dashboards/          # Dashboard screenshots
    ├── charts/              # Static charts
    └── reports/             # Analysis reports
```

## 🔧 Configuration

### Customization Options
- Modify color palettes in dashboard classes
- Adjust KPI thresholds (default: 15 min delay threshold)
- Configure peak hours (default: 11-13, 18-20)
- Set top N items for charts (default: 7-10)

### Dashboard Styling
```python
# Customize dashboard appearance
dashboard.plot_template = 'plotly_white'  # or 'plotly_dark'
dashboard.color_palette = px.colors.qualitative.Plotly
```

## 🚨 Troubleshooting

### Common Issues

1. **File Not Found Error**
   ```python
   # Ensure your Excel file path is correct
   file_path = 'path/to/your/data.xlsx'
   ```

2. **DateTime Parsing Issues**
   - Check Excel date format
   - Ensure datetime columns are properly formatted

3. **Missing Dependencies**
   ```bash
   pip install --upgrade plotly pandas scikit-learn
   ```

4. **Memory Issues with Large Datasets**
   - Consider data sampling for initial analysis
   - Use chunked processing for very large files

## 📈 Future Enhancements

- [ ] Real-time data integration
- [ ] Advanced forecasting models (ARIMA, Prophet)
- [ ] Automated report generation
- [ ] API integration for live dashboards
- [ ] Mobile-responsive dashboard design
- [ ] Advanced customer segmentation algorithms

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 Support

For questions or issues:
- Create an issue in the repository
- Contact the development team
- Check the troubleshooting section

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Built with Python, Pandas, Plotly, and Scikit-learn
- Inspired by real-world pizza delivery operations
- Thanks to the open-source community for excellent libraries

---

**Made with ❤️ for pizza delivery optimization**

*Last updated: December 2024*
