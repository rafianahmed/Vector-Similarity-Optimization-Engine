# Semantic Visual Similarity Search Engine

A single-file GitHub Pages application that finds the closest uploaded images to a target image using:

- TensorFlow.js + MobileNet embeddings
- semantic label filtering
- color histogram similarity
- grayscale mismatch penalties
- Bayesian-inspired Gaussian Naive Bayes score calibration

## Main fixes included

Compared with the previous version, this one adds:

1. **Semantic class filtering**
   - Uses MobileNet predicted labels
   - Penalizes or filters results with weak semantic alignment

2. **Combined scoring**
   - Embedding cosine similarity
   - Embedding distance features
   - Color histogram similarity
   - Average-color similarity
   - Label similarity

3. **Grayscale mismatch penalty**
   - Penalizes grayscale vs color mismatches that can otherwise rank too high from texture alone

4. **Improved optimizer**
   - Randomized Bayesian-inspired calibration over feature weights, threshold, and probability shift
   - Minimizes validation classification error on a pseudo-labeled split

## Deploy on GitHub Pages

1. Create a GitHub repository
2. Upload:
   - `index.html`
   - `.nojekyll`
3. Open **Settings → Pages**
4. Choose **Deploy from a branch**
5. Select `main` and `/root`
6. Save

## Resume / LinkedIn wording

Built a browser-based semantic image retrieval system that ranks the most similar uploaded images to a target image using deep embeddings, semantic label filtering, histogram features, and a Bayesian-inspired score optimization engine. Implemented client-side feature extraction with TensorFlow.js and MobileNet, along with calibration logic to reduce misranking caused by low-level texture similarity.

## Notes

This is Bayesian-inspired optimization, not direct Bayes error minimization. In practice, the app minimizes validation classification error using a probabilistic calibration layer.
