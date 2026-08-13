# SR Latch and Hysteresis
<img width="546" height="370" alt="image" src="https://github.com/user-attachments/assets/38646b57-05fb-4f8c-897c-9e557adbe246" />

The key idea is that hysteresis is created by having two different switching thresholds, and the SR latch remembers which state the circuit is in.

# What is Hysteresis
Hysteresis refers to a property where the output of a system depends not only on the current input value but also on the system's history.

For the 555 timer:
It switches one way at 1/3VCC and 2/3VCC where VCC=5V. 

- Lower threshold = 1.67 V
- Upper threshold = 3.33 V

--------
# What does the SR Latch do 
The SR latch is the memory element of the 555 timer.

The comparators detect the capacitor crossing the thresholds, but the latch remembers what state the circuit should stay in.
