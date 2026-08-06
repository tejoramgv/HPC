# Observations: Bubble Sort vs Quick Sort on Randomly Generated Data

## Experimental Setup

The program generates random datasets of varying sizes and measures the execution time of **Bubble Sort** and **Quick Sort**. The code was compiled with different optimization levels (`-O0`, `-O2`, and `-O3`) to analyze the impact of compiler optimizations on performance.

## Observations

### Bubble Sort

* Bubble Sort exhibited quadratic time complexity (O(n²)), making it increasingly inefficient as the input size grew.
* Execution time increased rapidly with larger randomly generated datasets because every element may need to be compared with every other adjacent element multiple times.
* Even with compiler optimizations enabled, the overall growth trend remained the same since the algorithm itself dominates the execution time.
* Optimizations mainly reduced instruction overhead rather than changing the algorithm's computational complexity.

### Quick Sort

* Quick Sort consistently outperformed Bubble Sort on randomly generated data.
* Its average-case time complexity of O(n log n) allowed it to scale much better with increasing input sizes.
* Random input generally produced well-balanced partitions, resulting in performance close to the average case.
* Execution times remained significantly lower than Bubble Sort, especially for medium and large datasets.

## Effect of Compiler Optimizations

### -O2

Compiling with -O2 enabled several optimizations without significantly increasing compilation time. Common optimizations include:

* Function inlining where beneficial.
* Dead code elimination.
* Loop optimizations.
* Better register allocation.
* Constant propagation and common subexpression elimination.

These optimizations reduced execution time for both algorithms by eliminating unnecessary instructions and improving CPU utilization.

### -O3

The O3 optimization level applies all O2 optimizations along with more aggressive techniques such as:

* Automatic loop unrolling.
* Additional function inlining.
* Vectorization (SIMD instructions) when applicable.
* More aggressive loop transformations.

For this experiment:

* Quick Sort generally benefited more from `-O3` because its recursive structure and partitioning routines allowed the compiler to optimize critical execution paths.
* Bubble Sort also became faster, but the improvement was relatively modest since the algorithm's O(n²) complexity remained the dominant performance bottleneck.

## Conclusion

The experiment demonstrates that algorithm selection has a much greater impact on performance than compiler optimization alone. 
While O2 and O3 reduced execution times by generating more efficient machine code, they could not compensate for the inherent inefficiency of Bubble Sort. 
Quick Sort remained substantially faster across randomly generated datasets due to its superior average-case time complexity. 
Compiler optimizations provide incremental performance gains, but choosing an efficient algorithm yields the most significant improvement.
