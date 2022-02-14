# Wrapper Approaches
- simple wrapper: do prediction only using 1 feature only. Use classification accuracy as measure of quality (it won't take into account dependent features well)
- Extend this to groups of features by heuristic search strategies (e.g. [[Greedy Selection]], Monte-Carlo)
## Two Flavours
- [[Wrapper not embedded]] The learning Algorithm is employed as a *quality of measure* 
- [[Wrapper embedded]] The selection process is really integrated **into** the learning algorithm