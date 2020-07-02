We put the proofs to questions in Problem 1 here. For the questions, please refer to __a2.pdf__ in this folder.

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

### f

#### i

#### ii

#### iii