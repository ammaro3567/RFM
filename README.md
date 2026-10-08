# Online Retail RFM Segmentation

Customer analytics project using the Online Retail transaction dataset. The notebook documents data-quality decisions, exploratory analysis, customer-level feature engineering, rule-based RFM segments, and a comparison of clustering approaches.

## Project files

- `Online_Retail_RFM_Analysis.ipynb` - complete, executed analysis and visualizations.
- `Online Retail.xlsx` - source transaction dataset used by the notebook.
- `RFM_Segmentation_Guideline.md` - project requirements and analytical guidance.
- `reports/Online_Retail_RFM_Segmentation_Report.pdf` - concise report of findings, clustering results, and recommendations.
- `requirements.txt` - Python packages needed to run the notebook.

## Run the analysis

Use Python 3.11 or newer. From this directory:

```bash
python -m venv .venv
```

Activate the environment, then install dependencies and launch Jupyter:

```bash
python -m pip install -r requirements.txt
jupyter notebook Online_Retail_RFM_Analysis.ipynb
```

The notebook reads `Online Retail.xlsx` from this directory. It can also locate the workbook at `RFM/Online Retail.xlsx` when started from the parent project directory.

## Main results

- 541,909 raw transaction lines, reduced through documented data-quality rules while retaining returns.
- 20 business-focused EDA insights covering sales, customers, products, time, geography, returns, and bulk behavior.
- 4,322 customers with positive net monetary value included in RFM scoring and clustering.
- Eight interpretable rule-based RFM segments for more targeted campaign hypotheses.
- K-Means K=2 selected among tested K=2..8 by highest sampled silhouette (0.429). This is a broad behavioral split; it complements rather than replaces the rule-based groups.
- Ward hierarchical clustering and DBSCAN are included as comparison methods.

## Important limitation

The transaction data covers December 2010 through December 9, 2011. The segments describe historical behavior and should not be treated as current customer profiles or as churn predictions. Validate results with newer data and controlled campaign tests before operational use.

## Repository hygiene

Temporary work in `tmp/`, Python environments, notebook checkpoints, and local editor files are excluded by `.gitignore`.
