# Stochastics_Review

In this repository I keep some simulations, using Montecarlo techniques and posteriorly, if possible comparing them to the teoric solution.

## Gamblers ruin

Consider a game with two players where player one has a probability $p$ chance of winning at every round. After each round loser transfers one penny to the winner. The game ends when one player has all the pennies.  

If there are no other limitations on the rounds, the probability that the game will eventually end this way is 1. (This is due to 0 and N are absorbing states and demonstrations of this probability can be found in most text books that have _random walks_ or _Markov Chain_).

Player one starts with $k$ points, and the probability of him winning each round is $p$. Player 2 starts with $N-k$ points, so the number of points in the game will always be constant $N$.

Let $u_k$ represent the expectation that the game is absorbed by state 0. Formally, let $\tau = min\{ n \geq 0 : X_n = 0 or X_n = N \}$ then:

<!-- $u_k = P(X_{\tau} = 0 \; |\;  X_0 = k \}$ -->
![u_k = P(X_{\tau} = 0 \; |\;  X_0 = k \}](https://render.githubusercontent.com/render/math?math=u_k%20%3D%20P(X_%7B%5Ctau%7D%20%3D%200%20%5C%3B%20%7C%5C%3B%20%20X_0%20%3D%20k%20%5C%7D)

Then  

<!-- $$
u_k = 
     \begin{cases}
       \frac{N - k}{N} & \quad \text{if} \quad p = 1/2\\
       \frac{(q/p) ^ k - (q/p) ^ N}{1 - (q/p) ^ N} & \quad \text{if} \quad  p \neq 1/2 \\

     \end{cases}
$$ -->
![u_k =       \begin{cases}        \frac{N - k}{N} & \quad \text{if} \quad p = 1/2\\        \frac{(q/p) ^ k - (q/p) ^ N}{1 - (q/p) ^ N} & \quad \text{if} \quad  p \neq 1/2 \\       \end{cases}](https://render.githubusercontent.com/render/math?math=u_k%20%3D%20%20%20%20%20%20%20%5Cbegin%7Bcases%7D%20%20%20%20%20%20%20%20%5Cfrac%7BN%20-%20k%7D%7BN%7D%20%26%20%5Cquad%20%5Ctext%7Bif%7D%20%5Cquad%20p%20%3D%201%2F2%5C%5C%20%20%20%20%20%20%20%20%5Cfrac%7B(q%2Fp)%20%5E%20k%20-%20(q%2Fp)%20%5E%20N%7D%7B1%20-%20(q%2Fp)%20%5E%20N%7D%20%26%20%5Cquad%20%5Ctext%7Bif%7D%20%5Cquad%20%20p%20%5Cneq%201%2F2%20%5C%5C%20%20%20%20%20%20%20%5Cend%7Bcases%7D)

And let $m_k$ represent the expected number of rounds before game ending
<!-- $$
m_k = 
     \begin{cases}
       K(N - k) & \quad \text{if} \quad p = 1/2\\
       \frac{1}{q-p} (k - N \frac{1 - (q/p)^k }{1 - (q/p)^N}) & \quad \text{if} \quad  p \neq 1/2 \\

     \end{cases}
$$ -->
![m_k =       \begin{cases}        K(N - k) & \quad \text{if} \quad p = 1/2\\        \frac{1}{q-p} (k - N \frac{1 - (q/p)^k }{1 - (q/p)^N}) & \quad \text{if} \quad  p \neq 1/2 \\       \end{cases}](https://render.githubusercontent.com/render/math?math=m_k%20%3D%20%20%20%20%20%20%20%5Cbegin%7Bcases%7D%20%20%20%20%20%20%20%20K(N%20-%20k)%20%26%20%5Cquad%20%5Ctext%7Bif%7D%20%5Cquad%20p%20%3D%201%2F2%5C%5C%20%20%20%20%20%20%20%20%5Cfrac%7B1%7D%7Bq-p%7D%20(k%20-%20N%20%5Cfrac%7B1%20-%20(q%2Fp)%5Ek%20%7D%7B1%20-%20(q%2Fp)%5EN%7D)%20%26%20%5Cquad%20%5Ctext%7Bif%7D%20%5Cquad%20%20p%20%5Cneq%201%2F2%20%5C%5C%20%20%20%20%20%20%20%5Cend%7Bcases%7D)

#### Numeric Approximation
Done using Montercarlo simulation, shown in the *jupyter notebook*. Data of the simulations is also loaded.

![](./Gamblers_Ruin/imgs/uk_vs_k.png)
![](./Gamblers_Ruin/imgs/mk_vs_k.png)  

#### Teoric Approximation

![](./Gamblers_Ruin/imgs/teoric_uk_vs_k.png)
![](./Gamblers_Ruin/imgs/teoric_mk_vs_k.png)  


