
#projects 
[[Guitar Pedal]]


# **General Info:**

Op-Amp is a sort name for Operational Amplifier, built in the 1940s. Its widely used in all analog electronic fields. Essentially, t takes small electrical signals and stretches, adds, subtracts, or smooths them out to perform a specific task.

**Core equations:**

The main equation that the op amp follows is:

$$
V_{out} = A_0(V_{in1}-V_{in2})
$$

Where $V_{out}$ acts as the output voltage,  $V_{in1}$ and $V_{in2}$  being the inputs of the block and $A_0$ being the gain. Schematically:

Because its sometimes difficult to calculate and evaluate conditions mathematically, there some simplifications that everyone does so that the calculations become easier, often called the ***golden rules of operational amplifiers***.

1. Ιf you know the voltage at the non-inverting input (V+​), you can assume the voltage at the inverting input (V−​) is ***exactly the same***.
2. The input impedance is considered infinite. his means that the ***current flowing inside the op-amp from the non-inverting and inverting input is actually 0***.


In this specific projects, we will use another notation. The model that the pedal is designed to is:


![[op-amp-in-schematics.png|466]]

In this photo, the inverting and non inverting ports are the inputs and V+, V- indicate the power supply. Its common that V- is ground and V+ is the positive voltage applied to the amplifier.



# **This projects arrangement**

The DS-1 guitar pedal has a specific section for the op-amps called *you guessed it* op-amp gain stage. It consists of two Operational Amplifiers. The first one is a relatively easy one, its a closed loop non inverting amplifier:

![[Pasted image 20260401002119.png|271]]

Ignoring the D8 diode which is used for safety reasons, the circuit is quite ease to analyze. for the equation shown above, we can see that:$$ \frac{V_{out}}{V_{in}}=\frac{A_{0}}{A_0 +1} $$
Its purpose on the circuit is ***impedance matching***. It acts as a Unity-Gain-Buffer. Specifically, it keeps the output voltage relatively similar to the input voltage but makes the output impedance much lower than the input one. 
This is done so that the ***output current becomes very strong and the voltage stays the same***Additionally, with the first buffer connected, ***current cannot flow backwards*** and only goes in one direction, unable to distort the original source. 

---

The second op-amp is bit more complex, but its also a closed loop non inverting amplifier. Here is the reference photo:

![[main_amp.png|531]]

This photo contains several RC filters, like the combination R13-C8 and R14-C9. The operational amplifier here is for the main boosting of the signal. When Applying Kirchhoff's law in this circuit we can see that:
$$\frac{V_{out}}{V_{in}} = 1+ \frac{R_{feedback}}{R_{ground}}$$
where $R_{feedback}$ is the resistance between the (-) input and the output and $R_{ground}$ is the resistance between the (-) input and ground.  So:

- $R_{feedback}=V R 1$
- $R_{ground}= R13$

Notice that we do not include R11 because of the ***golden rules of operational amplifiers***. We also do not include the capacitors C7 and C8, because their affect is only visible in very high frequencies. 
We include them in the circuit because we want to ***eliminate the high frequency odd harmonics*** that the two clipping diodes (D4, D5) produce.

So, because the VR1 resistor is actually variable we have a ***minimum*** and ***maximum*** gain for the second op-amp, depending on the RV1s value:

**Minimum gain:**

**$1+ \frac{0}{4.7k} = 1$**


**Maximum gain:**

**$1+ \frac{100k}{4.7k} = 22.3$


