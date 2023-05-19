# Lecture 5

## Question 1 - Setup leakage
If the $\tau$ in the CRS is leaked, we will know where the polynomial is evaluated. For the KZG commitment $p(\tau)G$, we choose another polynomial with the same evaluation on $\tau$, and they will share the same commitment value: $p(\tau)G=p'(\tau)G$.

## Question 2 - Vector commitment
Say we have to compute a commitment on vector $\textbf{v}=(v_1,v_2,...,v_n)$. We first interpolate a polynomial $p(x)$, s.t. $p(i)=v_i$. Then we commit to this polynomial.

## Question 3 - MultiCommitment
For batch opening on a set of points { $x_i,p(x_i)$ }, we define three algorithms.\
$\textbf{BatchCommit} (\textbf{Setup},p(x))$ $\rightarrow \mathcal{C}$:\
$\quad \mathcal{C}=p(\alpha)G$\
$\textbf{BatchWitness}(\textbf{Setup},p(x),$ { $x_i$ } $)$ $\rightarrow w$:\
$\quad w=\frac{\phi ( \alpha ) -r( \alpha )}{\prod_{x\in \{ x_i \}}{( \alpha -x )}}G$ \
  where $r(x)$ is the remainder of division $\phi ( x ) /\prod{( x-x_i )}$ and $\alpha$ is the hidden value in CRS, whose related computation can be done using elements like $\alpha G$ in CRS.\
$\textbf{BatchVerify}(\textbf{Setup},r(x),\mathcal{C},w,$ { $x_i$ } $)$ $\rightarrow 1/0$:\
$\quad e( \mathcal{C} ,G ) \overset{?}{=}e( \prod{( \alpha -x_i )},w ) \cdot e( G,r( \alpha ) G ) $
