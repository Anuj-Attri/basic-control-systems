# Transfer Function Coefficient Tuning for Faster Response

**Given,** 
* Transfer function F(s) = `K/(T*s + 1)` , where T is  the **Time constant**.

Our goal is to optimize the coefficients K & T such that the response of the input signal and the output signal at steady state can be reached in minimum time.
## Simulink Model:

The simulink model can be found [here](https://github.com/Anuj-Attri/basic-control-systems/blob/master/Transfer-Function-Tuning/exp1.slx)

The archiectecture of our model pertains to:
![](https://github.com/Anuj-Attri/basic-control-systems/blob/master/Transfer-Function-Tuning/Images/model.png?raw=true)


## Cases:
We optimize and manually enter the values of K and T, and thus plot the scope after each run.

* The cases use Step signals as input, with **Origin shifted to T = 1 sec**. Thus, with a time constant of t, the corresponding second will occur at (t+1) second.
* The runtime is changed accordingly to get a better estimate of the steady state.

### Case 1: K = 10, T = 5, runtime = 10s

For the above values of coefficients, we obtain the following scope:
![](https://github.com/Anuj-Attri/basic-control-systems/blob/master/Transfer-Function-Tuning/Images/result1.png?raw=true)

As we can deduce, the response is out of scope. Thus, these values are not optimized.

We zoom into these values to obtain the corresponding Value of response after one cycle (at T=6 secs)

![](https://github.com/Anuj-Attri/basic-control-systems/blob/master/Transfer-Function-Tuning/Images/result1zoomed.png?raw=true)

### Case 2: K = 1, T = 5, runtime = 30s

For the above values of coefficients, we obtain the following scope:
![](https://github.com/Anuj-Attri/basic-control-systems/blob/master/Transfer-Function-Tuning/Images/result2.png?raw=true)

These values have the same, improper output as the runtime is beyond 30 seconds. However, we can now conclude that to optimize the response, we need to optimize both K and T.
Thus, in the next case we change the value of T.

### Case 3: K = 1, T = 1, runtime = 10s
 
For the above values of coefficients, we obtain the following scope:
![](https://github.com/Anuj-Attri/basic-control-systems/blob/master/Transfer-Function-Tuning/Images/result3.png?raw=true)

We can see that the faster response in steady state is achieved when both the coefficients are optimized.

### Alternate Case: Ramp Input, runtime = 100s

The below shown output scope is achied through a ramp input with **initial state = 0** and **slope = 1**.

![](https://github.com/Anuj-Attri/basic-control-systems/blob/master/Transfer-Function-Tuning/Images/rampexample.png?raw=true)

# Conclusion
Thus, to optimize a Transfer Function for faster steady state response, we need to optimize both: The Numerator as well as the Time Constant.
