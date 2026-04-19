
#projects 
[[Guitar Pedal]]


# **General Theory**

Filters are mathematical operations applied to a signal to modify its spectral content. They are categorized by their ***frequency response***, essentially which part of the spectrum they let through. There are 4 main categories:

1. Low-pass filters (they let low frequencies pass but cut high frequencies)
2. High-pass filters (they let high frequencies pass and cut low frequencies)
3. Band-pass filters (they let a specific range of frequencies pass and cut everything else)
4. Band-stop filters (they cut a specific range of frequencies and let everything else pass)

There are also two types of filters:

1. Passive filters (they require no power supply and consist only of resistors, capacitors and inductors)
2. Active filters (they are essentially op-amps that can also boost the signal)






#  Filters in the arraignment

A filter that we mostly encounter in the DS-1 circuit is the RC filter. Its a passive filter and its use varies depending on the placement of the resistor and the capacitor. The following photo visualizes the arraignments for a low and high pass filters:

![[Pasted image 20260401234404.png]]

The expression of the RCs transfer function is:

**$$H(s)= \frac{1}{RCs +1}$$**
As we can see the RC filter has a pole in the frequency $\frac{1}{RC}$


---

## Our circuit:

![[Pasted image 20260401233429.png|445]]


We will analyze this part of the circuit, the transistor booster. As you can see there are plenty of filters in this arraignment:

1. C2-R4 are a standard high pass filter
2. C3-R5 is another high pass
3. C4-R7 is a low pass filter


