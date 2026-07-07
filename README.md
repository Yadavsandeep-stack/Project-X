# AgriMarket Profit Optimizer

## 📋 Overview

**AgriMarket Profit Optimizer** is an intelligent agricultural market analysis tool designed to help farmers maximize their profits by identifying the most profitable markets for their produce. The tool analyzes market data across different regions, accounts for transportation costs, and recommends the best markets based on commodity prices and logistics.

## 🎯 Key Features

- **Market Analysis**: Analyzes agricultural commodity prices across multiple markets and districts
- **Profit Calculation**: Calculates profit differences accounting for transportation costs
- **Smart Recommendations**: Identifies the most profitable market for your produce
- **Distance Calculation**: Uses geolocation to calculate distances between markets
- **Transportation Cost Analysis**: Factors in real-world transportation costs (₹3.6/kg/km)
- **User-Friendly Interface**: Interactive CLI for easy navigation through states, districts, and markets

## 🚀 Getting Started

### Prerequisites

- Python 3.7 or higher
- Required Python packages:
  - `pandas` - Data manipulation and analysis
  - `geopy` - Geolocation services

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Yadavsandeep-stack/Project-X.git
cd Project-X
```

2. Install required dependencies:
```bash
pip install pandas geopy
```

3. Prepare your dataset:
   - Place CSV files containing market data in a designated folder
   - CSV files should include columns: `State Name`, `District Name`, `Market Name`, `Group` (commodity), `Variety`, `Modal Price (Rs./Quintal)`, `Reported Date`

### Configuration

Update the `DATASET_FOLDER` variable in `AgriMarket Profit Optimizer.py`:
```python
DATASET_FOLDER = r"path/to/your/dataset/folder"
```

## 📖 Usage

Run the program:
```bash
python "AgriMarket Profit Optimizer.py"
```

### Interactive Workflow

1. **Select Your State** - Choose from available states in the database
2. **Select Your District** - Choose your district within the selected state
3. **Select Your Market** - Choose your local market
4. **Select Commodity** - Choose the type of commodity you want to sell
5. **Select Variety** - Choose the specific variety of the commodity
6. **Enter Quantity** - Specify the quantity (in kg) you want to sell

### Output

The program will:
- Display the selling price at your chosen market
- Analyze all markets selling the same commodity and variety
- Calculate profits relative to your market (accounting for transportation costs)
- Recommend the most profitable market
- Show the distance to the recommended market (if applicable)

## 📊 Project Structure

```
Project-X/
├── AgriMarket Profit Optimizer.py          # Main application script
├── AgriMarket Profit Optimizer Presentation.pptx  # Project presentation
├── AgriMarket Profit Optimizer Report.pdf  # Detailed project report
└── README.md                                # This file
```

## 🔧 How It Works

### Data Processing
1. Loads all CSV files from the specified dataset folder
2. Filters data to show only the latest reported date
3. Provides hierarchical selection (State → District → Market → Commodity)

### Profit Calculation
The algorithm calculates profit differences by:
- Getting the selling price at the user's chosen market
- For each alternative market:
  - Calculating distance using geolocation
  - Computing transportation costs: `distance × weight × ₹3.6/kg/km`
  - Subtracting transportation costs from the market price
  - Calculating profit relative to the user's market
- Identifying and recommending the market with maximum profit

### Transportation Cost Formula
```
Transport Cost = Distance (km) × Weight (kg) × ₹3.6/kg/km
```

## 📈 Use Cases

- **Farmers**: Identify the best markets to sell their produce for maximum profit
- **Agricultural Cooperatives**: Analyze market trends and recommend optimal selling locations
- **Market Analysts**: Study regional price variations and transportation impact
- **Policy Makers**: Understand agricultural market dynamics

## 🔍 Key Technologies

- **Python**: Core programming language
- **Pandas**: Data manipulation and analysis
- **Geopy**: Geolocation and distance calculation
- **Nominatim**: Open-source geocoding service

## 📝 Data Requirements

The CSV files should contain the following columns:
- `State Name` - State of the market
- `District Name` - District of the market
- `Market Name` - Name of the market
- `Group` - Commodity category
- `Variety` - Specific variety of the commodity
- `Modal Price (Rs./Quintal)` - Price in Rupees per Quintal
- `Reported Date` - Date of the price report

## ⚠️ Limitations

- Requires active internet connection for geolocation services
- Distance calculation accuracy depends on Nominatim service availability
- Transportation cost is a fixed estimate (₹3.6/kg/km)
- Works best with complete and recent market data

## 🎓 Educational Value

This project demonstrates:
- Real-world data analysis using pandas
- Geolocation and distance calculation using geopy
- Interactive CLI application development
- Problem-solving for agricultural economics

## 📄 Additional Resources

- **Presentation**: View `AgriMarket Profit Optimizer Presentation.pptx` for visual overview
- **Report**: Read `AgriMarket Profit Optimizer Report.pdf` for detailed analysis and insights

## 🤝 Contributing

Contributions are welcome! Please feel free to:
- Report bugs or issues
- Suggest improvements
- Submit pull requests
- Enhance documentation

## 📧 Contact

For questions or suggestions, please reach out to the project maintainer.

## 📜 License

This project is open source and available for educational and commercial use.

---

**Made with ❤️ for farmers and agricultural communities**
