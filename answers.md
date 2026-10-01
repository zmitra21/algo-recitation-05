# CMPS 2200 Recitation 05
## Answers

**Name:**Zack Mitra

Place all written answers from `recitation-05.md` here for easier grading.




- **3) (2 pts)** What is the work and span of `get_positions`? (assume our more efficient version of `scan` from class)

    Work is in $O(k)$  
    Span is in $O(\log k)$


- **5) (2 pts)** What is the work and span of `construct_output`?

  Work is in $O(n)$  
  Span is in $O(n)$


- **6) (2 pts)** What is the work and span of `supersort`?


  supersort calls count_values, `get_positions, and construct_output sequentially.

  - count_values has work $O(n)$ and span $O(n)$.
  - get_positions has work $O(k)$ and span $O(\log k)$.
  - construct_output has work $O(n)$ and span $O(n)$.

  Therefore, the total work is:

  $O(n) + O(k) + O(n) = O(n + k)$

  and the total span is:

  $O(n) + O(\log k) + O(n) = O(n)$

  Work is in $O(n + k)$  
  Span is in $O(n)$


- **8) (2 pts)** What is work and span of `count_values_mr`?

  The map step processes all $n$ elements independently, so it has $O(n)$ work and low span. 
  The collect step groups equal keys and is essentially a parallel sort, so it dominates the map-reduce operation with $O(n \log n)$ work and $O(\log^2 n)$ span. The reduce step has $O(n)$ total work and $O(\log n)$ span.

  Therefore:

  Work is in $O(n \log n + k)$  
  Span is in $O(\log^2 n + k)$