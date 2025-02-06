# **Machine Learning Explainability: PDP, ICE, and ALE Plots**

## **Overview**
This repository contains an analysis of feature effects on housing prices using **Partial Dependence Plots (PDP)**, **Individual Conditional Expectation (ICE) plots**, and **Accumulated Local Effects (ALE) plots**. The goal is to understand how different features influence house prices while considering interactions and dependencies among variables.

## **Dataset**
The analysis is based on the **California Housing Dataset**, which contains the following key features:
- **Longitude & Latitude**: Geographic coordinates of housing locations.
- **HouseAge**: Median age of houses in a given area.
- **AveRooms**: Average number of rooms per house.
- **AveBedrms**: Average number of bedrooms per house.
- **Population**: Total population in the given area.
- **AveOccup**: Average number of occupants per household.
- **MedInc**: Median income in the area.
- **Target**: House price (dependent variable).

## **Methodology**
### **1. Model Training**
- A **Random Forest Regressor** is trained on the dataset after splitting into training and testing sets.

### **2. Feature Effect Analysis**
- **PDP (Partial Dependence Plots):**
  - Shows the **average effect** of each feature on the target variable while marginalizing over others.

- **ICE (Individual Conditional Expectation Plots):**
  - Displays **instance-specific predictions** and their variations with feature changes.

- **ALE (Accumulated Local Effects Plots):**
  - Corrects for **feature dependencies** and provides a **localized effect estimation**.
  - More reliable than PDP when features are correlated.

## **Key Insights**
| Feature      | ICE Findings | PDP Findings | ALE Findings |
|-------------|-------------|-------------|-------------|
| **Longitude** | Strong variability, possible location-based interactions | Negative correlation, westward houses are costlier | Smooth decline, confirming PDP but adjusted for interactions |
| **Latitude**  | Price drops beyond certain latitudes, indicating spatial influence | Higher latitudes = lower house prices | Reliable downward trend, reinforcing PDP |
| **HouseAge**  | Some price appreciation with age, but varies significantly | Older homes tend to be valued higher | Confirms upward trend with more stable effect |
| **AveRooms**  | Some instances show steep increases, but overall stable | More rooms = higher prices, but not significant | Positive effect, but small magnitude |
| **AveBedrms** | Weak direct effect but interacts with other factors | Slight increase in price with more bedrooms | Minor effect, correlation adjustments make it clearer |
| **Population** | Weak impact with localized variability | No strong overall trend | Slight positive effect but not a key driver |
| **AveOccup**  | Higher occupancy leads to lower house prices | Clear downward trend | Negative effect, stabilizing at higher values |
| **MedInc**    | Strong positive effect, high-income areas drive prices up | Median income is a key price determinant | Steady increase, confirms importance of income |

## Installation and Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/johnjoel2001/ML_Explainability_II.git
   cd ML_Explainability_II
   ```
2. Run the Explainable_Techniques_II.ipynb
3. The requirements are listed in the first cell.

## References

1) https://github.com/AIPI-590-XAI/Duke-AI-XAI/blob/main/explainable-ml-example-notebooks/global_explanations.ipynb

2) https://scikit-learn.org/stable/auto_examples/inspection/plot_partial_dependence.html

3) https://christophm.github.io/interpretable-ml-book/ale.html

# **Note**

**AI Tools were not used in this Assignment**
