# Frank-Wolf-Algorithm-for-Recommender-Systems

## Overview  
This project implements and evaluates the **Frank-Wolfe algorithm** for **matrix completion** in recommender systems under nuclear-norm constraints. The method is tested on two benchmark datasets—**MovieLens Slim** and **X-Wines Slim**—and explores two step-size strategies:  
- **Diminishing Step-Size**  
- **Exact Line Search**  

Our results highlight the trade-off between accuracy and computational efficiency, with insights into the impact of **class imbalance** on model performance.  

## Features  
✅ **Matrix Completion** using the **Frank-Wolfe algorithm**  
✅ **Two Step-Size Strategies**: Diminishing step-size vs. Exact line search  
✅ **Benchmark Datasets**: MovieLens Slim & X-Wines Slim  
✅ **Performance Metrics**: Loss, R² score, duality gap, CPU time  
✅ **Class Imbalance Analysis**  

## Dataset  
The project uses two datasets:  
- **MovieLens Slim**: A refined version of the MovieLens dataset with 100,000 user ratings on a subset of movies.  
- **X-Wines Slim**: A structured subset of the X-Wines dataset with 150,000 user ratings on 1,007 wines.  

Both datasets are preprocessed to reduce sparsity while retaining meaningful patterns for evaluation.  

## Implementation Details  
The **Frank-Wolfe algorithm** is applied to matrix completion using a **nuclear-norm constraint** as a convex surrogate for rank minimization. The optimization process involves:  
1. **Linear Minimization Oracle (LMO)**: Finding top singular vectors of the gradient.  
2. **Step-Size Selection**:  
   - **Diminishing step-size**: $$\( \alpha_k = \frac{2}{k+1} \) $$ 
   - **Exact line search**: Dynamically computed per iteration.  
3. **Update Rule**:  
   $$\
   x_{k+1} = x_k + \alpha_k (s_k - x_k)
   \ $$ 
   where \( s_k \) is the rank-one update direction.  

## Results  
- **Both step-size strategies show convergence**, with exact line search achieving higher accuracy but at a higher computational cost.  
- **Class imbalance** impacts performance, with lower accuracy observed in underrepresented classes.  
- **Diminishing step-size is more computationally efficient**, while exact line search performs better for X-Wines.  



## Future Work  
🚀 Improve performance using advanced **Frank-Wolfe variants**  
🚀 Address **class imbalance** through sampling techniques  
🚀 Extend to **larger-scale datasets**  

