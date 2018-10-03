# Week 5
## 02/10/2018
### Learning of Trilateration
1. Linear and nonlinear. Linear requires matrix calculation.
2. The key to understand the algorithm of nonlinear least squares is that, when it tries to find the min value of F, it requires the derivative of F to be 0 (hence a peak value of F). Thus using Newton method on the derivative of F (Jacobian) needs a second derivative (Hessian).
3. Also note that the Hessian is not relate to function F, but its approximation (in PPT, d). [3]
4. A Hessian matrix H can be calculated by a Jacobian matrix J following: H = J.T * J

### Reference
1. Least Squares: https://blog.csdn.net/tengweitw/article/details/41745923
2. Jacobian matrix and Hessian matrix: http://jacoxu.com/jacobian%E7%9F%A9%E9%98%B5%E5%92%8Chessian%E7%9F%A9%E9%98%B5/
3. Jacobian matrix and Hessian matrix and nonlinear least squares: https://blog.csdn.net/u011494690/article/details/43274301
4. Sample Java Code https://github.com/lemmingapex/trilateration

## 03/10/2018
### Implementation of NLSQ
1. Use linear squares functions and models provided in Apache Commons Math library. Refer to [1].

### Reference
1. Least squares in Apache Commons Math http://commons.apache.org/proper/commons-math/userguide/leastsquares.html
2. Levenberg-Marquardt Algorithm https://blog.csdn.net/liu14lang/article/details/53991897