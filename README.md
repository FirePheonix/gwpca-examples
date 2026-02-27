## This repository contains simple implementations and experiments with **Geographically Weighted PCA (GWPCA)**, along with 3D visualization using **GeoLatent**, the 3D visualization Library I built on my own.

It demonstrates how dimensionality reduction changes when spatial structure is incorporated.

---

## What Is GWPCA?

Traditional PCA assumes a single global covariance matrix:

Σ = (1 / n) XᵀX

This produces one global set of eigenvectors for the entire dataset.

However, in spatial datasets, relationships vary across location.

GWPCA computes a **location-specific covariance matrix**:

Σᵢ = Σⱼ wᵢⱼ (xⱼ − μᵢ)(xⱼ − μᵢ)ᵀ

Where:

- wᵢⱼ = spatial weight between location i and j  
- μᵢ = local mean  
- Σᵢ = local covariance matrix  

Spatial weights are typically computed using a Gaussian kernel:

wᵢⱼ = exp( − d(i, j)² / h² )

Each location i gets:

- Its own covariance matrix  
- Its own eigenvalues  
- Its own principal components  

This makes the latent space spatially adaptive.
