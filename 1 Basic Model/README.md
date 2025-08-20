# Ideal Model

This project implements a simple vertical motion control model for a quadcopter.

## Equations

The vertical dynamics are given by:

$$ m \ddot{h}(t) = T(t) - mg $$

where:
- \( h(t) \) = altitude
- \( m \) = mass
- \( T(t) \) = thrust
- \( g \) = gravitational acceleration

The control law is a combination of feedforward and feedback:


$$ T(t) = mg + m \ddot{h}_{des}(t) + K_p \big(h_{des}(t) - h(t)\big) + K_d \big(\dot{h}_{des}(t) - \dot{h}(t)\big) $$

a
