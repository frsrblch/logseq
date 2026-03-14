- Each simplex has a coefficient vector $\bold a$ that combines with the quintic expansion of the coordinates
- \begin{bmatrix}\end{bmatrix}
- $$\bold D \bold a = \bold h$$
- $$\bold a = \bold D^{-1} \bold h$$
- $$\bold D = \begin{bmatrix}\bold D_0 & \bold D_1 & ...\end{bmatrix}^T$$
	- $$\bold D_i = \begin{bmatrix}
	  1 & x_i & y_i & x_i^2 & x_i y_i & y_i^2 & ...
	  \end{bmatrix}$$
	- $$\bold D_{i}^x = \begin{bmatrix}
	  0 & 1 & 0 & 2x_i & y_i & 0 & ...
	  \end{bmatrix}$$
- $$\bold a = \begin{bmatrix}a_{00} &  a_{10} & a_{01} & a_{20} & ...\end{bmatrix}^T$$
- $$f(x_i, y_i) = f(\bold x_i) = f_i = \begin{bmatrix}1 & x_i & y_i & x_i^2 & ...\end{bmatrix} \cdot \bold a$$
- $$\bold h = \begin{bmatrix}
  f_1 & f_1^x & f_1^y & f_1^{xx} & f_1^{xy} & f_1^{yy} & f_2 & f_2^x & ...
  \end{bmatrix}^T$$
- $$\bold D_4 = []$$
- ```
  $$
  A = \begin{bmatrix}
  a & b \\
  c & d
  \end{bmatrix}
  $$
  ```