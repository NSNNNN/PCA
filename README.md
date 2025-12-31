# PCA

Why PCA Reduces Noise (Simple Mathematical Explanation)

Assume the observed data is:

X = S + N

where
S is the true signal,
N is random noise with zero mean,
X is the measured data.

PCA is based on the covariance matrix of X:

C_X = (1/n) * XᵀX

Substituting:

C_X = C_S + C_N

For white noise:

C_N = σ² I

This means noise has equal and small variance in all directions, while the true signal has strong variance only in a few directions.

PCA performs eigenvalue decomposition on the covariance matrix:

C_X = U Λ Uᵀ

The eigenvalues are sorted in descending order:

λ1 ≥ λ2 ≥ ... ≥ λd

Large eigenvalues correspond mainly to the signal,
Small eigenvalues correspond mainly to noise.

When we keep only the first k principal components:

X_PCA = U_k U_kᵀ X

we remove components with very small variance, which are mostly noise.

As a result:

Noise power decreases
Signal power remains almost unchanged

So the signal-to-noise ratio increases:

SNR = Signal Power / Noise Power

This is why PCA effectively reduces noise.

Do Artifacts Increase or Decrease Noise?

Artifacts are unwanted but structured distortions in data (for example: eye movement in EEG, motion blur in images, camera shake in video).

Noise is random and unstructured, but artifacts usually have strong structure and large energy.

Properties comparison:

Noise: random, low variance, spread across components
Artifacts: structured, often high variance, appear in dominant components

Artifacts do not reduce noise.
If not removed, artifacts may dominate the principal components and significantly degrade data quality.
