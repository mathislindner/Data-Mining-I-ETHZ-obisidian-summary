Like we have similarity on vectors, we also have similarties on sets.

- Jaccard coefficient $$j(A,B) = \frac{A\cap B}{A \cup B}$$
- Jaccard Distance $$d(A,B) = 1- j(A,B) = \frac{A \cup B- A \cap B}{A \cup B}$$
- Overlap coefficient $$o(A,B) = \frac{|A\cap B|}{min(|A|,|B|)}$$
- Sorensen-Dice coefficient $$s(A,B) = \frac{2|A\cap B|}{|A| + |B|}$$
- Single link distance function $$d(A,B) = min_{a\in A, b\in B} \space d_{vector}(a,b)$$
- Complete link distance function $$d(A,B) = max_{a\in A, b\in B} \space d_{vector}(a,b)$$
- Average link distance function $$d(A,B) = \frac{1}{|A||B|} \sum_{a \in A}\sum_{b\in B}d_{vector}(a,b)$$