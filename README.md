$$
f(x) = sign(w x + b)\\
\hat w = (w, b), \hat x = (x,1)\\
hyperplane : wx+b = \hat w. \hat x = 0\\
predict : y = \hat w . \hat x  \quad   
$$

predict value also equal to the distance between the hyperplane and the predict point (x,y).

## learning strategy 

1. ### Lost Function 

   $$
   L(w,b) = -\sum_{x_i\in M}{y_i(w.x_i+b)}\\
   -y_i(w.x_i+b)>0, x_i \in M
   $$

2. ### gradient descent 

   $$
   d_w = -\sum_{x_i\in M}y_ix_i \qquad d_b  = -\sum_{x_i\in M}y_i
   $$

3. ### original strategy

   1. initiate w,b 
   2. select point $(x_i, y_i)$  from train data.
   3. if  $-y_i(w.x_i+b) > 0$ , refresh w,b as : $ w = w + \theta y_ix_i$    $b = b+\theta y_i $   ,$\theta$is the learning rate.
   4. return step 2 until M become a empty set.

4. ### duality strategy of the original

   In practical calculation process, the strategy could simplify the process.

   1. $w = \sum_{i=1}^N \alpha_i y_i x_i $  $ b = \sum_{i=1} ^N \alpha_i y_i    $  $ \alpha_i = n\times \theta $
   2. initiate  $ \alpha = 0 $ 
   3. select point $(x_i, y_i)$  from train data.
   4. if $-y_i(\sum {\alpha_j y_j x_j }.x_i+b) > 0$ , refresh w,b as : $ \alpha_i =\alpha_i + \theta $   $b = b+\theta y_i $   ,$\theta$  is the learning rate.
   5. return step 3 until M become a empty set. 

5. ### Algorithm Convergence Proof

   the algorithm could regression in finite  times.

   (1) prove if the data is linear splited , there must exists a hyperplane between the data,that could divide the data perfect.  

   > if the data is linear splitable,then there must exists a hyperplane  $ w_{opt.}x +b = 0 $ could divide the data perfect into two classes, which $ y_i(\hat w_{opt} \hat x_i) >=  \gamma > 0 $  $\gamma = min_i \{y_i (w_{opt} x_i + b)\}$   $\gamma$ is the minisit distance of the data point to the hyper plane.

   (2) use the learning strategy above , the algorithm could regression in finite  times.

   > $$
   > w_k = w_{k-1}+\theta y_ix_i,b_k = b_{k-1}+\theta y_i\\
   > \hat {w_k} = \hat w_{k-1} +\hat x_i \theta y_i\\
   > \hat {w_k} \hat {w_{opt}} = \hat {w_{opt}}\hat w_{k-1} +\hat {w_{opt}}\hat x_i \theta y_i>= \hat {w_{opt}}\hat w_{k-1} + \theta \gamma >= k\theta\gamma\\
   > ||w_k||^2 = ||\hat w_{k-1} +\hat x_i \theta y_i||^2 = ||\hat w_{k-1}||^2 + 2\hat w_{k-1} \hat x_i \theta y_i + ||\hat x_i \theta||^2<=||\hat w_{k-1}||^2 + ||\hat x_i \theta||^2 \\<= k||\hat x_i \theta||^2 <=  kR^2\theta^2\\
   > \\k\theta\gamma <=\hat {w_k} \hat {w_{opt}}<=||\hat {w_k}|| \quad ||\hat {w_{opt}}||<= \square{k}\theta R \\
   > \\k<= R^2/\gamma^2
   > $$

   

   

   

   

   

   

   

   

   

   

   

​	





