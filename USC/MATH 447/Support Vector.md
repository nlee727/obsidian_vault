$$
\min ||w||^2+ L_{S}^{hinge}(w) \text{ over} \{y_{i}<w,x_{i}>+b \geq 1\} $$
#### Fritz-John
$$
\min f(\bar{x}) 
$$ under positive $g_{i}(x)$
$$
\exists \lambda_{i}:\nabla f(p)=\sum_{i=1}^m \alpha_{i}\nabla g_{i}
$$
only for $i:g_{i}(p)=0$.

So $\{y_{i}<w,x_{i}>+b \geq 1\}$ is $g_{i}(w)\geq 0$
$$
\nabla f=2\lambda w
$$
$$
\nabla g_{i}=y_{i}x_{i}
$$
so
$$
2\lambda w=\sum_{i\in I}\alpha_{i}y_{i}x_{i}, I:\{i,g_{i}(w)=0\}
$$
$$
w=\sum \frac{\alpha_{i}y_{i}}{2 \lambda} x_{i}
$$
The minimum $W=\{y_{i}<w,x_{i>} \geq 1\}$ is always going to be on the boundary (where $y_{i}<w,x_{i}> =1$). In the separating hyperplane example, the lines that are critical are the points that are on the margin that is defined.

We have the problem of $\min( ||w||^2+L^{hinge}(w)$ under $y_{i}<w,x_{i}> \geq 1$
Introduce $$
g(w)=\max_{\alpha \in R^m, \alpha \geq 0} \sum \alpha_{i}(1-y_{i}<w,x_{i}>) = 0, y_{i}<w,x_{i}>\geq 1, \infty \text { else}
$$
$$
\min( ||w||^2+L^{hinge}(w) \iff \min_{w}(\lambda||w||^2+g(w)) < \infty (y_{i}<w,x_{i}\geq 1)
$$
$$
=\min_{w}\left( \lambda||w||^2+\max_{\alpha \geq 0}\sum\alpha_{i}(1-y_{i}<w,x_{i}>) \right)
$$
$$
=\min_{w}\max_{\alpha \in R^m, \alpha \geq 0}(\lambda||w||^2+\sum\alpha_{i}(1-y_{i }<w, x_{i}>)) \geq \max
$$