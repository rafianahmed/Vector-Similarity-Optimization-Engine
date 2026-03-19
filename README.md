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


