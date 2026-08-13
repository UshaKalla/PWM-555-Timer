# Schematic of Op Amp Comparator
<img width="577" height="590" alt="image" src="https://github.com/user-attachments/assets/60aa7f5b-bc7f-4d18-aaa0-9d9cceb24506" />
# 555 Timer Comparators

The 555 timer uses **two op-amp comparators** to monitor the voltage of the timing capacitor.

The comparators compare the capacitor voltage against two reference voltages:

- **Lower threshold:** \(1/3VCC\)
- **Upper threshold:** \(2/3VCC\)

For a 5 V supply:

- \(1/3VCC  1.67V\)
- \(2/3VCC  3.33V\)

---
# Where Do the Reference Voltages Come From?

The circuit is powered by a constant **5 V DC supply**. The AD3 can provide this 5 V supply.

The 5 V supply is called (VCC).

Three equal resistors create a voltage divider:

```text
             VCC = 5 V
                 │
               5.1 kΩ
                 │
                 ├──── 2/3 VCC ≈ 3.33 V
                 │
               5.1 kΩ
                 │
                 ├──── 1/3 VCC ≈ 1.67 V
                 │
               5.1 kΩ
                 │
                GND

___________
Lower Threshold
Vcap < 1.67 V
      ↓
Lower Comparator
      ↓
SET
      ↓
SR Latch
      ↓
Q = HIGH

Upper Threshold
Vcap > 3.33 V
      ↓
Upper Comparator
      ↓
RESET
      ↓
SR Latch
      ↓
Q = LOW
