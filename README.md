# Statitic-Machine-Learning
Summary and implementation of machine learning methods

## 
$$
f(x) = sign(w x + b)\\
\hat w = (w, b), \hat x = (x,1)\\
hyperplane : wx+b = \hat w. \hat x = 0\\
predict : y = \hat w . \hat x  \quad   
$$

predict value also equal to the distance between the hyperplane and the predict point (x,y).

## learning strategy 

1. Lost Function 
   $$
   L(w,b) = -\sum_{x_i\in M}{y_i(w.x_i+b)}\\
   -y_i(w.x_i+b)>0, x_i \in M
   $$

2. gradient descent 
   $$
   d_w = -\sum_{x_i\in M}y_ix_i \qquad d_b  = -\sum_{x_i\in M}y_i
   $$

3. original strategy

   1. initiate w,b 
   2. select point(x_i, y_i) from train data.
   3. if  $-y_i(w.x_i+b) > 0$ , refresh w,b as : $ w = w + \theta y_ix_i$    $b = b+\theta y_i $   ,$\theta$is the learning rate.
   4. return step 2 until M become a empty set.



