# Color Similarity ML Engine

A single-file GitHub Pages project that:

- treats RGB colors as vectors
- visualizes the vectors
- computes Euclidean distance, Manhattan distance, cosine similarity, cosine distance, and dot product
- suggests a third color that is more cosine-similar to the first color
- includes a Bayesian-inspired optimization engine that minimizes validation classification error on a synthetic color-similarity task

## Files

- `index.html` — the full app
- `.nojekyll` — optional GitHub Pages compatibility file

## Deploy on GitHub Pages

1. Create a new GitHub repository.
2. Upload `index.html` and `.nojekyll`.
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, choose:
   - **Source:** Deploy from a branch
   - **Branch:** `main` (or `master`)
   - **Folder:** `/root`
5. Save.
6. GitHub will publish your site with a public URL.

## What the ML engine does

This is not a true Bayes error minimizer, because Bayes error is theoretical and typically unknown.

Instead, the app uses a practical surrogate:

1. It generates labeled color-pair data.
2. It extracts pairwise features:
   - normalized Euclidean distance
   - normalized Manhattan distance
   - cosine similarity
   - normalized dot product
   - hue difference
   - saturation difference
   - value difference
3. It trains a Gaussian Naive Bayes classifier.
4. It performs grid search over:
   - feature weights
   - probability threshold
   - probability shift
5. It selects the setting with the lowest validation error.

That gives you a Bayesian-inspired error-minimizing similarity engine that is lightweight enough to run directly in the browser.

## Portfolio framing

**Color Similarity ML Engine — JavaScript / GitHub Pages**  
Built a browser-based machine learning application that represents RGB colors as feature vectors, computes similarity metrics, and uses a Bayesian-inspired optimization engine to reduce validation classification error. Implemented vector visualization, feature extraction, Gaussian Naive Bayes classification, and grid-search-based threshold optimization in a single-file deployable web app.
