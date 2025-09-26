# MOT Embeddings Demo

A practical demonstration of how to transform messy MOT (Ministry of Transport) defect notes into structured insights using text embeddings and machine learning.

## What This Demo Shows

This notebook demonstrates how to use **embeddings** to analyse unstructured text data - specifically MOT defect notes. You'll learn how to:

- **Convert text to numbers**: Transform defect notes into numerical vectors that capture meaning
- **Find hidden patterns**: Use clustering to group similar defects automatically  
- **Search by meaning**: Find related defects using semantic search instead of keyword matching

## The Problem

MOT testers write defect notes in their own words: "brake pipe corroded", "brake hose deteriorated", "brakes imbalanced". Traditional keyword searches miss the connection between these different phrasings. Embeddings solve this by understanding that these all describe brake-related issues.

## Real-World Application

This is a simplified example of techniques used in [CarHunch](https://www.carhunch.com), a vehicle insights platform that analyses millions of MOT records to provide vehicle insights and help people make better decisions about their vehicles.

## Getting Started

### Option 1: Run in Google Colab (Recommended)

Click the badge below to open the notebook in your browser. No setup required - just sign in to Google and start experimenting:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DonaldSimpson/mot_embeddings_demo/blob/main/mot_embeddings_demo.ipynb)

**Note**: Google Colab requires a Google account to save your work and provide computational resources. Your data remains private, and you can always download your work or run it locally if you prefer.

### Option 2: Run Locally

Clone this repository and install the dependencies:

```bash
git clone https://github.com/DonaldSimpson/mot_embeddings_demo.git
cd mot_embeddings_demo
```

Install the required dependencies:

```bash
pip install sentence-transformers scikit-learn matplotlib jupyter
```

Then open the notebook:

```bash
jupyter notebook mot_embeddings_demo.ipynb
```

## What You'll Learn

### Step 1: Generate Embeddings
Convert MOT defect notes into 384-dimensional vectors using the MiniLM model. Each note gets a unique "fingerprint" that captures its semantic meaning.

### Step 2: Clustering
Use K-means clustering to automatically group similar defects together. Visualise the results with PCA to see how brake issues, lighting problems, and steering defects cluster separately.

### Step 3: Semantic Search
Find defects similar in meaning to any query - not just exact word matches. Search for "brake failure" and discover brake-related defects even when they don't contain the word "failure".

## Experimentation Ideas

Once you understand the basics, try these modifications:

1. **Add your own defect notes** - Replace the sample data with notes from your own vehicle's MOT history
2. **Change the number of clusters** - Try `n_clusters=2`, `4`, or `5` to see how groupings change
3. **Experiment with different queries** - Try "safety concern", "performance issue", or "electrical fault"
4. **Try a different model** - Replace `"all-MiniLM-L6-v2"` with `"multi-qa-mpnet-base-dot-v1"` for potentially better results

## Scaling Up

- **Larger datasets**: Try with hundreds or thousands of MOT records
- **Different domains**: Apply the same techniques to customer feedback, support tickets, or any unstructured text
- **Production deployment**: Check out the [MLOps blog post](https://www.donaldsimpson.co.uk/2025/09/22/mlops-for-devops-engineers-minilm-mlflow-demo/) to see how to turn this into a production pipeline

## Technical Details

- **Model**: [all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) from Hugging Face
- **Clustering**: K-means with scikit-learn
- **Visualisation**: PCA for dimensionality reduction
- **Search**: Cosine similarity for semantic matching

## Data

Contains public sector information licensed under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).

## Author

**Donald Simpson** - DevOps engineer who got interested in ML through building [CarHunch](https://www.carhunch.com). This demo shares what I've learned about embeddings through that journey, presented in a way that other DevOps engineers and people interested in AI/ML can understand and experiment with.

## Related Content

- **Blog Post**: [From MOT Notes to Insights with MiniLM: A Practical Guide to Text Embeddings](https://www.donaldsimpson.co.uk) - Detailed explanation of the concepts and real-world applications
- **MLOps Demo**: [MLOps for DevOps Engineers - MiniLM & MLflow demo](https://www.donaldsimpson.co.uk/2025/09/22/mlops-for-devops-engineers-minilm-mlflow-demo/) - How to turn this into a production pipeline
- **CarHunch**: [Vehicle insights platform](https://www.carhunch.com) - Real-world application of these techniques

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
