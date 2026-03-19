
# Visual Similarity Search Engine

Built a Visual Similarity Search Engine that identifies the most similar images to a target image using deep learning and vector-based similarity. The system extracts feature embeddings using TensorFlow.js (MobileNet), computes similarity through cosine distance and other metrics, and ranks images based on learned relevance.

To enhance performance, I implemented a Bayesian-inspired optimization engine using Gaussian Naive Bayes and randomized hyperparameter search to minimize validation classification error and calibrate similarity scoring. The application runs fully in the browser and is deployed as a single-file GitHub Pages project.

This project demonstrates practical applications of feature embeddings, similarity learning, probabilistic modeling, and optimization in real-world AI systems such as visual search and recommendation engines.

A single-file GitHub Pages app that lets you:

- upload a target image and candidate images
- extract deep image embeddings using **TensorFlow.js + MobileNet**
- compute image similarity using **cosine similarity**, Euclidean distance, and color histograms
- rank the closest uploaded images to the target image
- run a **Bayesian-inspired optimizer** that calibrates weights and thresholds to reduce validation error

## Files

- `index.html` — complete app
- `.nojekyll` — GitHub Pages compatibility file

## Deploy on GitHub Pages

1. Create a new GitHub repository.
2. Upload `index.html` and `.nojekyll`.
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, choose:
   - **Source:** Deploy from a branch
   - **Branch:** `main`
   - **Folder:** `/root`
5. Save.

Your app will be published to GitHub Pages.

## What the optimizer does

This app cannot directly minimize true Bayes error, because Bayes error is theoretical and unknown in practice.

Instead, it uses a **Bayesian-inspired calibration engine**:

1. Build pairwise similarity features from the uploaded images.
2. Create pseudo labels using a similarity threshold.
3. Train a lightweight **Gaussian Naive Bayes** model.
4. Random-search over:
   - feature weights
   - decision threshold
   - probability shift
5. Choose the configuration with the lowest validation error.

This gives you an efficient browser-side approximation of probabilistic score optimization.

## Suggested project names

- Visual Similarity Search Engine
- Image Embedding Retrieval System
- Bayesian-Inspired Image Similarity Optimizer

## Resume bullet

**Visual Similarity Search Engine — JavaScript / TensorFlow.js / GitHub Pages**  
Built a browser-based image retrieval system that identifies the most similar uploaded images to a target image using deep feature embeddings, cosine similarity, and histogram features. Implemented a Bayesian-inspired Gaussian Naive Bayes calibration engine with randomized threshold optimization to reduce validation classification error, and deployed the application as a single-file GitHub Pages project.
