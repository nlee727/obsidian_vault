## How to determine if Vector Field is conservative
#### Example:
Is $\vec{F}(x,y)=(x^2y+y^3,xe^y)$ conservative?

Traditional Way:
$$
\frac{\partial{f}}{\partial{x}} = x^2y+y^3
$$
$$
\frac{\partial{f}}{\partial{y}} = xe^y
$$

However, we know:
$$
F_{xy} = F_{yx}
$$
so,
$$
\frac{\partial}{\partial{y}}\left(\frac{\partial{f}}{\partial{x}}\right) = x^2+3y^2
$$
and
$$
\frac{\partial}{\partial{x}}\left(\frac{\partial{f}}{\partial{y}}\right) = e^y
$$
since $x^2+3y^2 \neq e^y$, the vector field is **not conservative**

## 2 Methods
#### In 2D:
If $\vec{F}(x,y)=(P(x,y),Q(x,y))$

If $\frac{\partial{P}}{\partial{y}}$ = $\frac{\partial{Q}}{\partial{x}}$ 
Then the vector field ($\vec{F}$) is conservative

#### In 3D:
If $\vec{F}(x,y,z)=(P(x,y,z),Q(x,y,z),R(x,y,z))$

If $curl(\vec{F})=0$
Then the vector field ($\vec{F}$) is conservative

## Definition
Given a curve, parametrized by $r(t)=(x(t),y(t),z(t))$, going from A (=$\vec{r}(a))$ to B (=$\vec{r}(b))$

Given $\vec{F}(x,y,z)=(P,Q,R)$ we define the **line integral** of $\vec{F}$ along $C$ as:
$$
\int_{C}\vec{f}\,dr = \int_{a}^{b} \vec{F}(\vec{r}(t)) \cdot \vec{r} \,'(t)
$$
If $F$ is a forcefield, $\int_{C}\vec{f}\,dr$ is the work done (=energy spent) to move from point **a** to point **b** along curve $C$ using the force $\vec{F}$.

##### Example:
$C$ is the upper half of a circle of radius 2 going counterclockwise
$\vec{F} = (-y,x)$

Compute $\int_{C}\vec{f}\,dr$

$$r(t) = (2\cos t, 2\sin t) \quad 0 \leq t \leq \pi$$

$$\vec{F}(\vec{r}(t)) =  (-2\sin t, 2\cos t)$$
$$r'(t) = (-2\sin t, 2\cos t)$$

Therefore:
$$
\begin{align}
 \int_{C}\vec{f}\,dr &= \int_0^{\pi}(-2\sin t, 2\cos t) \cdot(-2\sin t, 2\cos t) \, dt \\ 
 &=\int_0^{\pi} (4\sin^2t\,+\,4\cos^2t)\, dt \\
 &=\int_0^{\pi} 4\, dt \\
 &= 4\pi
\end{align}
$$ 

## Theorem
#### Fundamental Theorem of calculus for conservative fields
If $C$ is a Path from **a** to **b** ***and*** vector field $(\vec{F})$ is conservative ($\vec{F}= \nabla f$) then:
$$
\int_C \vec{f} \, d\vec{r} = F(B) - F(A)
$$

#### Remarks:
1) Line integrals of conservative field are **path-independent**, $C$ only depends on end points (The path it takes does not matter)
2) If path is a closed loop (A=B) then
$$
\oint_C \vec{f}\, d\vec{r}
 = 0$$