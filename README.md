# A/B/C Testing Analysis: Fast-Food Promotion Effectiveness

---

## Project Overview

This project analyzes the effectiveness of three distinct promotional strategies (Promotion 1, Promotion 2, and Promotion 3) implemented by a fast-food chain. The primary goal was to determine which promotion yielded the highest total sales per store location over a four-week period and to provide data-driven recommendations for future marketing campaigns. The analysis uses **A/B/C testing methodology**, a statistical approach to compare the performance of multiple experimental groups.

---

## Project Objectives

-   **Assess Statistical Significance:** Determine if there are statistically significant differences in total sales performance among the three promotions.
-   **Identify Best Performers:** Pinpoint which specific promotions perform better or worse than others.
-   **Provide Actionable Recommendations:** Offer data-backed guidance for the fast-food chain's promotional strategy.

---

## Dataset

The analysis uses simulated sales data from a multi-week promotional campaign across various fast-food store locations. Key variables include:

-   `MarketID` and `LocationID`: Identifiers for markets and individual stores.
-   `MarketSize`: Categorical classification of the market (Small, Medium, Large).
-   `AgeOfStore`: Store age in years.
-   `Promotion`: The specific promotion assigned to the store (1, 2, or 3).
-   `SalesInThousands`: Weekly sales, which was aggregated to **Total Sales per Location** as the primary outcome metric.

---

## Methodology

-   **Data Preprocessing:** Weekly sales data was aggregated to `Total Sales per Location` to represent each store as a single experimental unit.
-   **Exploratory Data Analysis (EDA):** Visualizations (e.g., box plots) were used to understand sales distributions across promotion groups. Covariate balance checks were performed on `MarketSize` and `AgeOfStore` to ensure fair comparisons between groups.
-   **Statistical Hypothesis Testing:**
    -   **ANOVA (Analysis of Variance):** An ANOVA test was conducted to determine if there was an overall statistically significant difference in mean total sales among the three promotion groups.
    -   **Tukey's HSD Post-Hoc Test:** Since ANOVA indicated an overall significant difference, **Tukey's Honestly Significant Difference (HSD) test** was used for pairwise comparisons between promotions, controlling the family-wise error rate.

---

## Key Findings

The statistical analysis revealed clear differences in promotional effectiveness:

-   **Overall Significance:** The ANOVA test showed a **statistically significant difference** in total sales among the three promotions (p-value < 0.05), indicating that the promotion choice does impact sales.
-   **Promotion 2 Underperforms:**
    -   Promotion 1 generated approximately **$43,078 more** in total sales per location than Promotion 2, a **statistically significant** difference (p < 0.05).
    -   Promotion 3 generated approximately **$32,140 more** in total sales per location than Promotion 2, also a **statistically significant** difference (p < 0.05).
-   **Promotion 1 and Promotion 3 are Similar:** There was **no statistically significant difference** in total sales between Promotion 1 and Promotion 3 (p > 0.05). Both performed similarly well.

---

## Recommendations

Based on these findings, we recommend:

-   **Discontinue Promotion 2:** This promotion consistently leads to significantly lower sales and should be **avoided** in future campaigns.
-   **Focus on Promotions 1 and 3:** Both Promotion 1 and Promotion 3 are effective in driving sales. The choice between these two should be guided by other business considerations, such as implementation cost, operational complexity, or long-term strategic goals, as their sales performance is statistically comparable.

---

## Limitations

-   **No Cost Data:** This analysis focused solely on sales volume and did not account for the **cost of implementing each promotion**. A promotion with slightly lower sales but significantly lower costs might still be more profitable.
-   **Short Duration:** The sales data covers only four weeks, limiting insights into **long-term effects**, customer loyalty, or sustained promotional impact.
-   **External Factors:** Unmeasured external variables (e.g., local events, competitor activities, seasonality) may have influenced sales and were not controlled for.
-   **Covariate Balance:** A slight imbalance in `MarketSize` distribution across promotion groups was observed, which could potentially confound results in more complex analyses.
-   **Generalizability:** Findings are based on the provided sample and might not perfectly apply to all store locations or future campaigns without further validation.

---

## Future Work

To enhance this analysis and provide more robust recommendations, consider:

-   **Cost-Benefit Analysis:** Integrate promotional cost data to determine the **Return on Investment (ROI)** for each strategy.
-   **Longer-Term Tracking:** Conduct A/B tests over extended periods (e.g., 8-12 weeks) to assess sustained impact and customer behavior.
-   **Advanced Statistical Modeling:** Utilize techniques like ANCOVA or mixed-effects models to explicitly control for confounding variables.
-   **Qualitative Feedback:** Collect insights from store managers and customers regarding operational challenges and promotion appeal.
-   **Targeted A/B Test (P1 vs. P3):** If needed, design a dedicated, larger-scale A/B test specifically comparing Promotion 1 and Promotion 3 to potentially uncover smaller, subtle differences.

---

## Technologies Used

-   **Python**
-   **Pandas** (for data manipulation)
-   **NumPy** (for numerical operations)
-   **SciPy** (for statistical tests)
-   **Statsmodels** (for ANOVA and Tukey HSD)
-   **Matplotlib** (for visualizations)
-   **Seaborn** (for enhanced visualizations)
-   **Jupyter Notebook** (for reproducible analysis)

---

## How to Run the Analysis

-   **Clone the Repository:** Download or clone this project's repository to your local machine.
-   **Install Dependencies:** Ensure you have Python installed and install the required libraries using `pip`:
    ```bash
    pip install pandas numpy scipy statsmodels matplotlib seaborn jupyter
    ```
-   **Place Data:** Ensure your dataset CSV file (e.g., `FAST_FOOD_Marketing-Campaign.csv`) is in the same directory as the Jupyter Notebook.
-   **Open Notebook:** Launch Jupyter Notebook from your terminal in the project directory:
    ```bash
    jupyter notebook
    ```
    Then open the `Fast_Food_A-B_Testing.ipynb` file.
-   **Run Cells:** Execute each cell in the notebook sequentially to reproduce the analysis.
