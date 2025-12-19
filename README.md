# Peak Mountain Resort: Sentiment Analysis and Topic Modelling

This project performs sentiment analysis and topic modelling on review data using Google Cloud Natural Language API and Vertex AI.

## Relevant Documents

- **Project Presentation**: [Google Slides](https://docs.google.com/presentation/d/1a7cz1MJohllrkrjDxezuYfDvn8xzavciGf9Mm6TsqDg/edit?usp=sharing)

> [!TIP]
> For a quick overview of the project and results, start with the Google Slides presentation above.

## Prerequisites

> [!IMPORTANT]
> Ensure you have the following before starting:

- Python 3.8+
- Google Cloud account with:
  - Cloud Storage API enabled
  - Natural Language API enabled
  - Vertex AI API enabled
- Service account with appropriate permissions

## Setup

### 1. Create Python Environment

**Create and activate a virtual environment:**

```bash
# Create virtual environment
python -m venv venv

# Activate on Linux/Mac
source venv/bin/activate

# Activate on Windows
# venv\Scripts\activate
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Google Cloud Authentication

1. Download your service account JSON key from Google Cloud Console:
   - Go to IAM & Admin → Service Accounts
   - Create or select a service account with the required permissions
   - Keys tab → Add Key → Create new key → JSON format

2. Save the downloaded file as `service-account-key.json` in the project root
   - This file is automatically gitignored for security
   - The notebook expects this exact filename and location

### 4. Configure Project Settings

> [!NOTE]
> Update the following variables in the notebook to match your Google Cloud project:

- `bucket_name`: Your GCS bucket name (currently `ubc-bolt-case`)
- `project`: Your Google Cloud project ID (currently `sent-analysis-452609`)

## Usage

1. Open `reviews_notebook.ipynb` in Jupyter or VS Code
2. Run the cells sequentially:
   - **Section 1**: Sentiment Analysis - Computes sentiment scores for reviews
   - **Section 2**: Topic Modeling - Classifies reviews into categories
   - **Section 3**: Data Visualization - Creates plots and insights

## Security Note

- The `.gitignore` file is configured to exclude all `*.json` credential files
- Always use environment variables or local files excluded from git
- Rotate your keys immediately if they are accidentally exposed

## Data

> [!NOTE]
> Data files are expected in your Google Cloud Storage bucket.

The notebook expects:
- Input: `reviews.csv` in your GCS bucket
- Output: `reviews_final_model_results.csv` saved to GCS

## License

See LICENSE file for details.

## Acknowledgement
Contributor: Mikail Durrani, Jacky Zhong and me (ofc)
