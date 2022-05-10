# extended-kalman-filter
Apply Extended Kalman Filter to track the motion of object by #MATLAB#

This project is to implement Extended Kalman Filter to estimate motion states of the object based on the radar measurements, also including: linearize the measurement system, analyze estimations obtained. 

Due to the copyright of the assignment, I cannot show the questions and my complete answers here.

Just give a short description: 

  the  Kalman  Filter  tries  to estimate the state 𝑥 of a discrete-time controlled process which is constrained by linear stochastic difference equations.  But  what  happens  if  the  process  to  be  estimated  and/or  the  measurement relationship are/is non-linear? Like below equations:
                                         
                                            𝑥(𝑘+1) = 𝑓(𝑥(𝑘),𝑢(𝑘),𝑤(𝑘))         
                                            𝑧(𝑘)=ℎ(𝑥(𝑘),𝑣(𝑘))                   
                             where the random variables 𝑤(𝑘)and 𝑣(𝑘) again represent the process and measurement noise.
  
  The  solution  is  to linearize the  function  about  the  current  mean  and  covariance,  and  a  filter  that works is called an Extended Kalman Filter(EKF). We can linearize the estimation by using the partial derivatives of the process and/or  measurements to compute  estimates.
 
  In summary, in this project, the  system we should solve out is with  linear  process equations and  nonlinear  measurement  equations, respectively are:
  
                                            𝑥(𝑘+1)=𝐴𝑥(𝑘)+𝑤(𝑘)           𝑤(𝑘)~𝑁([0  0  0  0]𝑇, 𝑄)      (1)
                                            𝑧(𝑘)=[ℎ1(𝑥(𝑘),𝑣(𝑘))     ℎ2(𝑥(𝑘),𝑣(𝑘))]𝑇 = ℎ(𝑥(𝑘),𝑣(𝑘))      (2)
  The time updation equations are:
  
                                             𝑥̂−(𝑘) = 𝐴𝑥̂−(𝑘−1) + 𝐵𝑢(𝑘−1)                (3)
                                             𝑃−(𝑘) = 𝐴𝑘𝑃(𝑘−1)𝐴𝑘𝑇 + 𝑄𝑓(𝑘−1)             (4)
                             where 𝐴𝑘 is the process Jacobians at step 𝑘 and 𝑄𝑓(𝑘) is the process noise covariance at step 𝑘
  
  The measurement updation equations are:
  
                                             𝐾(𝑘)=𝑃−(𝑘)𝐶𝑘𝑇[𝐶𝑘𝑃−(𝑘)𝐶𝑘𝑇+𝑅𝑓(𝑘)]−1       (5)
                                             𝑥̂(𝑘)=𝑥̂−(𝑘)+𝐾(𝑘)[𝑧(𝑘)−ℎ(𝑥̂−(𝑘),0)]          (6)
                                             𝑃(𝑘)=[𝐼−𝐾(𝑘)𝐶𝑘]𝑃−(𝑘)                      (7)
                            𝐼 is the identity matrix, ℎ isthe function in (2), 𝑅𝑓(𝑘) is the measurement noise covariance at step 𝑘. The Jacobian 𝐶𝑘 at time step 𝑘 is given by:
                                           
                                           𝐶𝑘[𝑖,𝑗] = 𝜕ℎ[𝑖]𝜕𝑥[𝑗](𝑥̂−(𝑘),𝑢(𝑘−1))
                            Thus, 𝐶 is the Jacobian matrix of partial derivatives of ℎ with respect to the state 𝑥.
  
   Implement and apply the Extended Kalman Filter to the two given measurements in 'RadarMeasurements.mat'. Set 𝜎q2=1. Use 𝜎r2=1 to analyse the first measurement and 𝜎r2=100 to analyse the second measurement. See  the code extended_km.mlx
   
   Here I also attach the figure of motion track of the object, and the figure of Kalman gains obtained, and the figure of NIS plotting. 
   
   
  
