# Lecture 3 Homework

## Question 1 - Non-Quadratic Remaining
### Completeness
Suppose the $x$ is not the quadratic remaining under the modulus $m$, and since $y$ is multiplied by a quadratic remaining $s^2$, $QR(m,y)=QR(m,x)$, which is consistent with the random bit $b$.
### Soundness
Suppose the $x$ is the quadratic remaining under the modulus $m$, and since $y$ is multiplied by a quadratic remaining $s^2$, the prover will always return bit 1. But the random bit $b$ is selected uniformly. The prover will pass the checking with the prob of $\frac{1}{2}$ if he conforms to the protocol. Or he can only guess the random bit $b$ and pass the check with the same prob.

## Question 2 - Quadratic Remaining
### Completeness and Soundness
The above two properties can be proved with the same method as steps in question 1.
### Knowledge soundness
Note that the prover will send $t$ or $st$ according to the random bit $b$, and if the verifier gets both the $t$ and $st$, he can easily compute the secret $s$ with only one modular inverse.
### Zero-Knowledge

## Question 3 - Self-Pairing disables DDH
We can check these two pairing outcomes: $e(\alpha g,\beta g)=\alpha \beta \cdot g_t =? e(y, g)$.

## Question 4 - BLS signature
### UF-CMA security
Suppose the attacker can forge a signature $\sigma '$, s.t. $\sigma '=\alpha 'g_0=\alpha \cdot H(m) g_0$. He can break the $CDH$ problem: $CDH(\alpha g_0,H(m) g_0)\rightarrow \alpha H(m)\cdot g_0$.
