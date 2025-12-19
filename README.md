# Review Sentiment Analysis and Topic Modeling

This project performs sentiment analysis and topic modeling on review data using Google Cloud Natural Language API and Vertex AI.

## Prerequisites

- Python 3.8+
- Google Cloud account with:
  - Cloud Storage API enabled
  - Natural Language API enabled
  - Vertex AI API enabled
- Service account with appropriate permissions

## Setup

### 1. Install Dependencies

```bash
pip install google-cloud-storage google-cloud-language google-cloud-aiplatform pandas numpy matplotlib seaborn scikit-learn
```

### 2. Google Cloud Authentication

**Option A: Environment Variable (Recommended)**

1. Download your service account JSON key from Google Cloud Console:
   - Go to IAM & Admin → Service Accounts
   - Create or select a service account
   - Create a new JSON key

2. Set the environment variable:
   ```bash
   export GOOGLE_APPLICATION_CREDENTIALS="/path/to/your/service-account-key.json"
   ```

**Option B: Local File**

1. Download your service account JSON key
2. Save it as `service-account-key.json` in the project root (this file is gitignored)
3. The notebook will automatically detect it

### 3. Configure Project Settings

Update the following in the notebook:
- `bucket_name`: Your GCS bucket name (currently `ubc-bolt-case`)
- `project`: Your Google Cloud project ID (currently `sent-analysis-452609`)

## Usage

1. Open `reviews_notebook.ipynb` in Jupyter or VS Code
2. Run the cells sequentially:
   - **Section 1**: Sentiment Analysis - Computes sentiment scores for reviews
   - **Section 2**: Topic Modeling - Classifies reviews into categories
   - **Section 3**: Data Visualization - Creates plots and insights

## Security Note

⚠️ **Never commit your service account credentials to version control!**
- The `.gitignore` file is configured to exclude all `*.json` credential files
- Always use environment variables or local files excluded from git

## Data

The notebook expects:
- Input: `reviews.csv` in your GCS bucket
- Output: `reviews_final_model_results.csv` saved to GCS

## License

See LICENSE file for details.
