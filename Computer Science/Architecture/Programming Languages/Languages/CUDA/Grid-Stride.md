---
date: 2026-06-10
---
A *grid-stride loop* is a [[CUDA]] kernel pattern in which each thread processes multiple elements by stepping through the data in increments equal to the total number of threads in the grid:

```cuda
for (int i = blockIdx.x * blockDim.x + threadIdx.x;
     i < n;
     i += gridDim.x * blockDim.x)
{
    // process element i
}
```

The naive alternative is a 1-to-1 mapping where thread $i$ handles exactly element $i$, requiring exactly as many threads as elements. The grid-stride pattern decouples thread count from data size, allowing each thread to handle elements $i,\ i + \text{grid size},\ i + 2 \cdot \text{grid size},\ \ldots$
