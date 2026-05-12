# Airbnb vs Hotel Pricing Analysis

Comparative analysis of accommodation platforms using statistical methods to understand pricing strategies, booking behaviors, and market positioning differences.

## Project Overview

This project performs a comprehensive data science analysis comparing two major accommodation sectors: traditional hotels and Airbnb short-term rentals. The analysis focuses on the USA market to ensure geographic comparability and employs multiple statistical techniques to extract meaningful insights.

### Research Objectives

1. Analyze pricing distribution patterns across both platforms
2. Identify factors influencing hotel cancellation rates
3. Examine the relationship between room type and pricing in Airbnb listings
4. Provide data-driven recommendations for stakeholders in both sectors

## Data Sources

### Dataset 1: Hotel Booking Demand
- Source: https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand
- Records: 119,390 hotel bookings
- Time Period: July 2015 - August 2017
- Coverage: Two hotel types (City Hotels and Resort Hotels)
- Key Features: Booking details, cancellation status, lead time, ADR (Average Daily Rate), guest counts, stay duration

### Dataset 2: Airbnb Open Data
- Source: https://www.kaggle.com/datasets/arianazmoudeh/airbnbopendata
- Records: Property listings with pricing and availability data
- Coverage: Multiple property types and room configurations
- Key Features: Listed prices, room types, location data, review information

Both datasets are independent sources, meeting the requirement for multi-source analysis.

## Methodology

### Data Processing
1. Data loading and initial exploration
2. Missing value analysis and treatment
3. Outlier detection using IQR method
4. Data standardization for geographic focus (USA market)
5. Feature engineering for comparative metrics

### Analytical Techniques

#### Exploratory Data Analysis
- Distribution analysis using percentiles and quartiles
- Price variability measurement (coefficient of variation)
- Market segmentation by price tiers
- Cancellation pattern analysis

#### Statistical Hypothesis Testing
Three formal hypothesis tests were conducted at significance level alpha = 0.05:

1. Chi-squared Test of Independence
   - Question: Do cancellation rates differ by hotel type?
   - Variables: Hotel type (categorical) vs Cancellation status (binary)
   
2. Independent Samples T-test
   - Question: Does booking lead time affect cancellation likelihood?
   - Variables: Lead time (continuous) for canceled vs completed bookings
   
3. One-way ANOVA
   - Question: Do different Airbnb room types command different prices?
   - Variables: Room type (categorical) vs Price (continuous)

## Key Findings

### 1. Hotel Booking Patterns

#### Cancellation Analysis
- Overall cancellation rate observed in dataset
- Significant variation between City Hotels and Resort Hotels (Chi-squared test)
- Lead time correlation with cancellation probability identified (T-test)

#### Strategic Insight
Hotels face substantial cancellation rates that vary systematically by property type and booking advance time, requiring differentiated cancellation management strategies.

### 2. Airbnb Pricing Structure

#### Price Distribution
- Market exhibits moderate to high price variability
- Significant clustering in mid-range pricing segment
- Statistical differences detected across room types (ANOVA, p<0.05)

#### Critical Finding
While room types show statistically significant price differences, the absolute gaps are relatively small compared to overall market price dispersion. This indicates that factors beyond room configuration drive substantial pricing variation.

### 3. Comparative Market Structure

#### Hotels
- More standardized pricing within hotel categories
- Clear relationship between lead time and cancellation risk
- Segmentation primarily by hotel type and timing

#### Airbnb
- Higher price heterogeneity reflecting diverse property types
- Room type explains only partial price variation
- Differentiation requires factors beyond basic room configuration

## Statistical Results Summary

### Hypothesis Test 1: Hotel Cancellation by Type
- Test: Chi-squared test of independence
- Result: Statistically significant relationship detected
- Interpretation: Cancellation rates differ between City and Resort hotels

### Hypothesis Test 2: Lead Time Impact
- Test: Independent samples T-test
- Result: Significant difference in lead times between canceled and completed bookings
- Interpretation: Booking advance time is associated with cancellation probability

### Hypothesis Test 3: Room Type Pricing
- Test: One-way ANOVA
- Result: Significant price differences across room types
- Effect Size: Moderate (room type explains portion but not majority of price variance)
- Interpretation: Room type matters but other factors dominate pricing

## Business Recommendations

### For Hotel Operators

#### Cancellation Management
- Implement differentiated cancellation policies by hotel type
- Consider lead-time-based deposit requirements
- Focus retention efforts on high-risk booking segments

#### Revenue Optimization
- Adjust pricing based on cancellation risk profiles
- Implement dynamic pricing considering lead time patterns
- Calculate optimal overbooking levels based on observed cancellation rates

### For Airbnb Hosts

#### Pricing Positioning
Market analysis reveals:
- 25th percentile: Price threshold for budget positioning
- 50th percentile: Median market price (high competition zone)
- 75th percentile: Premium tier entry point

#### Differentiation Strategy
Key finding: Room type alone insufficient for premium pricing

Recommended differentiation factors:
- Location quality and accessibility
- Property-specific amenities and features
- Service responsiveness and guest experience
- Unique characteristics not captured in room type classification

Since room type price gaps are modest relative to overall market spread, hosts must compete on dimensions beyond basic property configuration.

## Project Structure
airbnb-hotel-pricing-analysis/ | |-- data/ | |-- raw/ # Original datasets | | |-- hotel_bookings.csv | | |-- airbnb__data.csv | | | |-- processed/ # Cleaned data outputs | |-- notebooks/ | |-- Data_Science_Final_Exam.ipynb # Main analysis notebook | |-- visualizations/ # Generated plots (if saved) | |-- README.md # This file |-- requirements.txt # Python dependencies


## Technical Requirements

### Python Dependencies
pandas==2.0.3 numpy==1.24.3 matplotlib==3.7.2 seaborn==0.12.2 scipy==1.11.1 scikit-learn==1.3.0 jupyterlab==4.0.3 plotly==5.17.0 openpyxl==3.1.2

