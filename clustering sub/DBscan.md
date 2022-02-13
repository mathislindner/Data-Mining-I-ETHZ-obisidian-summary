# Density-Based Spatial Clustering of Applications with Noise
[video](https://youtu.be/RDZUdRSDOok)
The main idea is to make a graph based clustering algorithm more robust to noise and works well with nested clusters (datapoints of one cluster wrap around another cluster of datapoints)

## Core idea
- Two objects $v_i$ and $v_j$ with distance $d(vi , vj) < \epsilon$  belong to the same cluster if either $v_i$ or $v_j$ are a core object. 
- $v_i$ is a core object iff there are *MinPoints* points within a distance of $\epsilon$ from $v_i$ . 
- A cluster is defined by iteratively checking this core object property.