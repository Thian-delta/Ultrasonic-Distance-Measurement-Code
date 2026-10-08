**Ultrasonic distance measurement signal:** 

For the longest distance, 1.5m,

echo high time = 8746 us = 8.746 ms

So, our period can be slightly higher than that (not necessarily too far off).



**The trigger input signal:**

Connected to PB8 driven by TIM16 set up for 10 μs pulse with a period of 30 ms



So, setting up in TIM16:

Period of 30 ms

Period of 10 us



Clock frequency = 10 MHz

Pre-scaler = 9 (Timer updates at a rate of 1 MHz, i.e. 1us between increments)

Pulse = 10 (10 us)

Counter Period = 29999 (30 ms)



**The echo output signal:**

Connected to PB14 driven by TIM15 set up the same as TIM16



Clock frequency = 10 MHz

Pre-scaler = 9 (Timer updates at a rate of 1 MHz, i.e. 1us between increments)

Counter Period = 29999 (30 ms)



In this case, every 'tick' is 1us.

Distance = (number of 'tick')\*1us\*10^(-6)s/us\*343 m/s

