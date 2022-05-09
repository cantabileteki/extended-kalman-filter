# extended-kalman-filter
Apply Extended Kalman Filter to track the motion of object  

This project is to implement Extended Kalman Filter to estimate motion states of the object based on the radar measurements, also including: linearize the measurement system, analyze estimations obtained. 

Due to the copyright of the assignment, I cannot show the questions and my complete answers here.
Just give a short description: 
 the  Kalman  Filter  tries  to estimate the state 𝑥 of a discrete-time controlled process which is constrained by linear stochastic difference equations.  But  what  happens  if  the  process  to  be  estimated  and/or  the  measurement relationship are/is non-linear? The  solution  is  to linearize the  function  about  the  current  mean  and  covariance,  and  a  filter  that works is called an Extended Kalman Filter(EKF). We can linearize the estimation by using the partial derivatives of the process and/or  measurements to compute  estimates.
 
 In summary, in this project, For  this  system, with  linear  process equationsand  nonlinear  measurement  equations,  Eq. (1)  and (2) can be simplified as:𝑥(𝑘+1)=𝐴𝑥(𝑘)+𝑤(𝑘)𝑤(𝑘)~𝑁([0000]𝑇,𝑄)(12)𝑧(𝑘)=[ℎ1(𝑥(𝑘),𝑣(𝑘))ℎ2(𝑥(𝑘),𝑣(𝑘))]𝑇=ℎ(𝑥(𝑘),𝑣(𝑘))(13)
