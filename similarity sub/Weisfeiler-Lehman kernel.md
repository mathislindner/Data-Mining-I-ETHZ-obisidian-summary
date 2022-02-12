# Weisfeiler-Lehman kernel
https://ethz.ch/content/dam/ethz/special-interest/bsse/borgwardt-lab/documents/slides/CA10_WeisfeilerLehman.pdf
## Algorithm
1) Represent each node $v$ as sorted list $L_v$ of its neighbors $O(m)$
2) Compress this list into a hash value $h(L_v)$ $O(m)$
3)  Relabel $v$ by the hash value $h(L_v)$ $O(n)$
### Runtime analysis
- Per Graph pair: $O(m h)$
- For $N$ graphs: $O(Nmh + N²nH) \approx O(N²mh)$
## Visuals 
![[Pasted image 20220212183133.png]]
![[Pasted image 20220212183149.png]]