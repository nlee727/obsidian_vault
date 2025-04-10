
$$
x_{1}=x_{0}+Z \quad Z \sim N(0,1)
$$
$$
x_{2}=x_{1}+Z
$$
$$
x_{2}=x_{0}+2Z
$$
$$
X_{T}=X_{0}+T\cdot Z
$$

#### Reparameterization Trick

$$
Z\sim N(0,1)
$$
$$
\alpha Z\sim N(0,\alpha^2)
$$
$$
\beta Z\sim N(0,\beta^2)
$$
$$
\alpha Z+\beta Z = N(0,\alpha^2+\beta^2) = \sqrt{ \alpha^2 +\beta^2} = Z
$$
So,
$$
x_{1}=\alpha x+\beta Z \quad\alpha^2+\beta^2=1
$$
$$
x_{1}=x_{0}\sqrt{ \beta_{1} }+\sqrt{ 1-\beta_{1} }Z
$$
$$
x_{2}=x_{1}\sqrt{ \beta_{2} }+\sqrt{ 1-\beta_{2} }Z
$$
$$
x_{2}=(x_{0}\sqrt{ \beta_{1} }+\sqrt{ 1-\beta_{1} }Z)\sqrt{ \beta_{2} }+\sqrt{ 1-\beta_{2} }Z
$$
$$
x_{2}=\sqrt{ \beta_{1} \beta_{2}}x_{0}+\sqrt{ \beta_{2}-\beta_{1} }\beta_{2}Z+\sqrt{ 1-\beta_{2} }Z
$$
$$
=\sqrt{ \beta_{1}\beta_{2} }x_{0}+\sqrt{ 1-\beta_{1}\beta_{2} }Z
$$
So,
$$
x_{T}=\prod_{t=1}^T(\beta_{t})^{1/2}\cdot x_{0}+\sqrt{ 1-\prod_{t=1}^T (\beta_{t})^{1/2}}\cdot Z
$$
$$
D_{KL}(q(x^{1\dots T}|x^0)||p_{\theta}(x^{1\dots T}|x^0)) \approx \frac{1}{N}\sum_{i=1}^N \log\left[ \frac{q(x^{1\dots T}|x^0)}{p_{\theta}(x^{1\dots T}|x^0)} \right]
$$
$$
=\log\left[ \frac{\prod_{t=1}^Tq(x_{t}|x_{t-1})}{p(x^T)\prod_{t=1}^T p_{\theta}(x_{t-1}|x_{t})} \right]+\log(p_{0}(x^0))
$$
$$
\log(p_{\theta}(x^0))=-\log\left[ \frac{\prod_{t=1}^Tq(x_{t}|x_{t-1})}{p(x^T)\prod_{t=1}^T p_{\theta}(x_{t-1}|x_{t})} \right]+D_{KL}(q(x^{1\dots T}|x^0)||p_{\theta}(x^{1\dots T}|x^0))
$$
$$
\log(p_{\theta}(x^0))\geq -\log\left[ \frac{\prod_{t=1}^Tq(x_{t}|x_{t-1})}{p(x^T)\prod_{t=1}^T p_{\theta}(x_{t-1}|x_{t})} \right]
$$

