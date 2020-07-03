We put the solutions to the written part here. For the questions, please refer to [a2.pdf](https://github.com/huijunzhao-ds/cs224n/blob/master/a2/a2.pdf) in this folder.

### a 

Note that 
- if $w=o$, then $y_w=y_o=1$;
- otherwise, i.e., if $w\neq o$, then $y_w=0$.

So

$$ -\sum_{w\in\text{Vocab}}y_w\log(\hat{y}_w) = -1\cdot \log(\hat{y}_o) - \sum_{w\neq o}0\cdot \log(\hat{y}_w) = -\log(\hat{y}_o)$$

### b
Let $\theta$ = $U^Tv_c$ and $\hat{y}=\text{softmax}(\theta)$. Then $J=\text{CrossEntropy}(y, \hat(y))$. Then we have 

$$ \frac{\partial{J}}{\partial{\theta}} = (\hat{y}-y)^T $$

By chain rule,

$$ \frac{\partial{J}}{\partial{v_c}} = \frac{\partial{J}}{\partial{\theta}}\frac{\partial{\theta}}{\partial{v_c}}= (\hat{y}-y)^T \frac{\partial{(U^Tv_c)}}{\partial{v_c}} = U(\hat{y}-y)$$
### c
Similar to (b)

$$ \frac{\partial{J}}{\partial{u_w}} = \frac{\partial{J}}{\partial{\theta}}\frac{\partial{\theta}}{\partial{u_w}}= (\hat{y}-y)^T \frac{\partial{(U^Tv_c)}}{\partial{U}} = (\hat{y}-y)v_c$$

### d

$$ \sigma(x)' = \sigma(x)(1-\sigma(x)) $$

### e

$$ \frac{\partial{J}}{\partial{v_c}} = (\sigma(u_o^Tv_c)-1)u_o-\sum_{k=1}^K(\sigma(-u_k^Tv_c)-1)u_k$$

$$ \frac{\partial{J}}{\partial{u_o}} = (\sigma(u_o^Tv_c)-1)v_c$$

$$ \frac{\partial{J}}{\partial{u_k}} = (\sigma(u_k^Tv_c)-1)v_c$$

Instead of computing the full matrix $U$, negativa sampling only calculates a subset of size $K$. Therefore, it is more efficient.

### f

$$ \partial J_\text{skip-gram}/\partial U = \sum_{-m\leq j\leq m, j\neq 0}\frac{J}{\partial U}$$

$$ \partial J_\text{skip-gram}/\partial v_c = \sum_{-m\leq j\leq m, j\neq 0}\frac{J}{\partial v_c}$$

$$ \partial J_\text{skip-gram}/\partial w_c (w\neq c) = 0$$
