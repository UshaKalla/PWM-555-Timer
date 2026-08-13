# PWM With 555 Timer

Generating PWM using a discrete 555 timer.

A **555 timer** is an IC chip that is used in various applications, including oscillators, clocks, blinking LEDs, pulse generators, and more.

Essentially, a 555 timer is a little electronic circuit that lets you **control time** using a capacitor charging and discharging.

Think of it as a **tiny automatic timing machine**. You use resistors and a capacitor to control how long something happens, and the 555 timer produces an output signal accordingly.

## Three Common Modes

### 1. Monostable — "One-Shot"

You trigger it, and the output turns ON for a set amount of time, then turns OFF.

**Example:**

> Press a button → LED stays ON for 2 seconds → LED turns OFF.

### 2. Astable — "Oscillator"

The 555 timer continuously switches its output **ON and OFF**, producing a repeating signal.

**Example:**

> LED blinker or square-wave clock signal.

### 3. Bistable — "Two-State"

The 555 timer acts somewhat like a simple memory element. It stays **ON or OFF** until triggered to change.

**Example:**

> Press button → ON  
> Press button again → OFF

---

## What's Actually Happening?

Inside the 555 timer are several important components:

1. **Two voltage comparators** — monitor the capacitor's voltage.
2. **A flip-flop** — remembers whether the output should be ON or OFF.
3. **A discharge transistor** — controls the capacitor's discharge.
4. **A voltage divider** — establishes reference voltage levels.

### Astable Mode

For this project, the 555 timer is used in **astable mode**.

In astable mode, the capacitor continuously charges and discharges:

**Capacitor charges → reaches a threshold → 555 switches → capacitor discharges → reaches another threshold → 555 switches again → repeat.**

This causes the 555 timer to produce a repeating **square-wave output**.

The frequency and timing of the square wave are determined by the values of the resistors and capacitor in the circuit.

---

# Application

## Generating PWM With a 555 Timer

In this project, we will use a **555 timer in astable mode** to generate a **PWM (Pulse Width Modulation)** signal that controls the speed of a fan.

### What Is PWM?

**Pulse Width Modulation (PWM)** is a technique used to control the amount of power delivered to a device by rapidly switching the power **ON and OFF**.

A PWM signal looks like a repeating square wave:

```text
HIGH  ────┐      ┌────┐      ┌────
          │      │    │      │
LOW       └──────┘    └──────┘




25% Duty Cycle

HIGH  ──┐          ┌──
        │          │
LOW     └──────────┘
       <--- cycle --->


50% Duty Cycle

HIGH  ─────┐    ┌─────
           │    │
LOW        └────┘
       <--- cycle --->

75% Duty Cycle

HIGH  ─────────┐  ┌────
               │  │
LOW            └──┘
         <--- cycle --->

Low duty cycle → less average power → slower fan
50% duty cycle → approximately half the average power
High duty cycle → more average power → faster fan
100% duty cycle → continuously ON



