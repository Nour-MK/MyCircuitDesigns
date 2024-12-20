<p align="center">
  <img src="Photos/Banner.png"/>
</p>

<!-- Badge icons found at https://feathericons.com/-->
<p align="center">

<a href="https://custom-icon-badges.demolab.com/badge/Academic%20Year-Fall%202024-ffffff?style=for-the-badge&logo=calendar&logoSource=feather&logoColor=gray">
  <img src="https://custom-icon-badges.demolab.com/badge/Academic%20Year-Fall%202024-ffffff?style=for-the-badge&logo=calendar&logoSource=feather&logoColor=white" title="Academic Year" style="vertical-align:top; margin:4px"></a> <a href="https://custom-icon-badges.demolab.com/badge/Bachelor's%20Course-Linear%20Electronics%201-ffffff?style=for-the-badge&logo=book-open&logoSource=feather&logoColor=gray"><img src="https://custom-icon-badges.demolab.com/badge/Bachelor's%20Course-Linear%20Electronics%201-ffffff?style=for-the-badge&logo=book-open&logoSource=feather&logoColor=white" title="Bachelor's Course" style="vertical-align:top; margin:4px"></a> <a href="https://custom-icon-badges.demolab.com/badge/Project%20Status-Completed-ffffff?style=for-the-badge&logo=activity&logoSource=feather&logoColor=gray"><img src="https://custom-icon-badges.demolab.com/badge/Project%20Status-Completed-ffffff?style=for-the-badge&logo=activity&logoSource=feather&logoColor=white" title="Project Status" style="vertical-align:top; margin:4px"></a>

</p>

<p align="center">
  This report is Markdown-typed and submitted by student Nour Mostafa with ID 2021004938 in partial fulfillment of the requirements for the Bachelor of Science (B.Sc.) degree in Computer Engineering. This paper is best viewed in dark mode. To adjust your settings, go <a href="https://github.com/settings/appearance">here</a>.
</p>



# <p align="center">220V AC to 3V DC Power Supply Circuit</p>

Our task is to design a circuit that steps down and rectifies the 220V AC mains voltage of the UAE to 3V DC. The circuit must include a transformer to step down the voltage, a rectifier to convert the AC to DC, a filtering capacitor to smooth the rectified voltage, and a voltage regulator to maintain a steady 3V DC output. We need to calculate the transformer's turns ratio required for stepping down the input voltage, determine the specifications for the rectifier, capacitor, and voltage regulator, and calculate the ripple voltage to ensure it is within acceptable limits. Additionally, we will analyze the power efficiency of the circuit and calculate the maximum current the circuit can supply to the load while maintaining a steady output. Finally, we will simulate this circuit in Multisim to verify the output voltage, current, and ripple characteristics.


---

<p align="center">
  <img src="Photos/circuit-schema.png" title="Base Circuit Schema" />
</p>

## Introduction

A 220V AC to 3V DC power supply circuit is an electronic system designed to convert high-voltage alternating current (AC) from the mains supply into a low-voltage direct current (DC) output suitable for powering low-voltage electronic devices. The design process involves several stages, starting with a step-down transformer that reduces the 220V AC input to a lower AC voltage level, such as 6V AC, which is suitable for rectification. The rectification stage then converts this low-voltage AC into pulsating DC using a rectifier, which can be a half-wave, full-wave, or bridge configuration depending on the desired efficiency and performance. Following rectification, a filtering stage smoothens the pulsating DC voltage by using capacitors to remove AC ripples. To ensure a stable and accurate 3V DC output, a voltage regulation stage is implemented using a voltage regulator, such as a Zener diode. Throughout the design, several considerations are essential, including safety, isolation from high-voltage AC, proper transformer selection, and efficient power regulation to minimize heat loss. 

A __transformer__, the heart of the initial stage in many power supply circuits, is an essential electrical device that operates on the principle of electromagnetic induction to transfer electrical energy between two or more windings, typically at different voltage levels. It consists of primary and secondary windings wound around a magnetic core, which helps transfer energy efficiently through a changing magnetic field when an alternating current (AC) flows through the primary winding. Transformers are broadly classified into several types based on their function and design. Step-down transformers are used to reduce high input voltage to a lower output voltage, making them ideal for power supplies where a lower, safer voltage is required for devices. Conversely, step-up transformers increase the voltage level, often used in power transmission systems to minimize energy loss during long-distance transport. Isolation transformers are employed to electrically isolate the input and output circuits, ensuring safety and protecting sensitive components from electrical noise or faults. Autotransformers, which share a single winding for both input and output, are compact and more efficient but do not provide electrical isolation. Lastly, instrument transformers, including current and voltage transformers, are used for measurement and protection in high-voltage systems, ensuring safe monitoring of power without direct exposure to high voltages. Through these various types, transformers play a vital role in adapting voltage levels, ensuring energy efficiency, and enhancing the safety and performance of electrical systems across numerous applications.

__Rectifiers__ are essential components in power supply systems that serve the critical function of converting alternating current (AC) into direct current (DC), which is necessary for powering most electronic devices. Rectifiers are broadly classified into three main types: half-wave, full-wave, and bridge rectifiers, each with its own operating principles and efficiency levels. Half-wave rectifiers are the simplest form, utilizing a single diode to allow only one half of the AC waveform—either positive or negative—to pass through while blocking the other half. Although this approach is straightforward and cost-effective, it is inherently inefficient as it wastes half of the AC signal, resulting in lower power output and significant ripple. Full-wave rectifiers, on the other hand, make use of two diodes in conjunction with a center-tap transformer. This configuration allows both halves of the AC waveform to be rectified, significantly improving efficiency by utilizing the entire waveform. The center-tap transformer splits the AC voltage into two equal but opposite signals, and each diode conducts during one half-cycle, ensuring that the output voltage is smoother compared to a half-wave rectifier. However, the use of a center-tap transformer adds complexity and cost to the design. Lastly, bridge rectifiers are the most widely used and efficient type, consisting of four diodes arranged in a bridge configuration. Unlike full-wave rectifiers, bridge rectifiers do not require a center-tap transformer, making them more compact and cost-efficient. The four diodes work together to rectify both halves of the AC waveform, ensuring continuous conduction and producing a more stable DC output with minimal ripple. Bridge rectifiers are preferred for their superior performance, higher efficiency, and versatility in a wide range of applications. Collectively, rectifiers form the backbone of AC-to-DC conversion systems, ensuring that electrical devices receive the steady and reliable DC voltage required for their operation.

A __Zener diode__ acts as a voltage regulator by exploiting its ability to maintain a stable voltage across its terminals when reverse-biased beyond its breakdown voltage. Unlike regular diodes, which fail under reverse breakdown, the Zener diode is designed to operate reliably in this region. When the input voltage exceeds the Zener breakdown voltage, the diode conducts in reverse, allowing excess current to bypass the load while clamping the voltage to the Zener voltage. This property ensures that the output voltage remains constant regardless of fluctuations in the input voltage or variations in load current, as long as the current through the Zener diode stays within its safe operating limits. By placing the Zener diode parallel to the load, it stabilizes the voltage and protects sensitive components from overvoltage, making it an essential component in low-power voltage regulation circuits.

In today's modern world, electronic devices are deeply embedded in nearly every aspect of our daily lives, from smartphones and laptops to home appliances and wearable technology. These devices have become indispensable, with many of us relying on them for communication, entertainment, work, and even healthcare. As we continue to integrate technology into every part of our routines, the need for reliable and efficient power supply systems becomes increasingly important. Every device, whether it's charging a smartphone or powering a home appliance, requires a stable and consistent power source to function optimally. This project, focused on designing and understanding power supply circuits, is crucial because it addresses the fundamental need for energy in an electronic-dependent world. By ensuring that devices can be properly powered, we enable the seamless operation of modern technology, which ultimately supports the convenient and connected lifestyle we enjoy today.

## Apparatus

1. [AC Voltage Source](https://download.ni.com/support/manuals/374485a.pdf): provides the input electrical energy needed to power the circuit. This could come from a mains power supply, such as the 220V AC commonly found in residential buildings. The AC source alternates in polarity and voltage, providing the necessary energy for the transformer to step down and for the diodes to rectify it into DC. Without the AC voltage source, the circuit would not function, as there would be no input power to convert and regulate.

2. [Transformer](https://www2.seas.gwu.edu/~ece20/spring15/labs/tutorials/ECE_2115_Tutorial_2_Simulating_Transformers_in_Multisim.pdf): plays a key role in stepping down the input AC voltage from a higher value (such as 220V AC) to a lower, more manageable value that is suitable for the circuit and the devices being powered (such as 5V or 12V DC). The transformer works on the principle of electromagnetic induction, where the primary coil receives the input voltage and generates a magnetic field that induces a voltage in the secondary coil. By adjusting the turns ratio between the primary and secondary windings, the transformer can change the voltage to the required level.

3. [Diodes](https://www.vishay.com/docs/88503/1n4001.pdf): The diodes in this circuit are responsible for rectifying the AC voltage, converting it into a unidirectional (DC) flow. This process is crucial because most electronic devices, including smartphones, require DC power to operate. In this case, the diodes form a bridge rectifier configuration that allows the current to flow during both halves of the AC cycle, ensuring that the output is a full-wave rectified DC signal. The diodes also prevent reverse current from flowing, which could damage the power supply or other sensitive components.

4. [Capacitor](https://www.ultralibrarian.com/wp-content/uploads/2022/07/shutterstock_731355235-1024x683.jpg): serves the vital role of filtering the rectified DC voltage. After the AC voltage is converted into pulsating DC by the diodes, the capacitor smooths out these ripples, creating a more stable DC output. The capacitor charges during the peak of the AC waveform and discharges during the lower part of the waveform, filling in the gaps to reduce voltage fluctuations.

5. [Zener Diode](https://www.vishay.com/docs/85816/1n4728a.pdf): acts as a voltage regulator, ensuring that the output voltage remains constant despite variations in input voltage or load conditions. It does this by allowing current to flow normally in the forward direction but clamps the reverse voltage to a specific, predetermined value (its Zener voltage). Once the output voltage exceeds the Zener diode's rated voltage, it starts to conduct in reverse, preventing the voltage from rising above a safe level and protecting the components downstream, such as the load or the battery being charged.

6. [Resistors](https://static4.arrow.com/-/media/arrow/images/miscellaneous/1123-chart-how-to-read-resistor-color-codes-body-image.jpg): The resistors in this circuit serve various functions, including limiting the current to safe levels and helping to control the voltage drop across specific parts of the circuit. They can be used to adjust current flow through components, such as the Zener diode, or to provide feedback for stabilizing the voltage regulation. The resistors are also part of the load on this circuit. The load resistor in a power supply circuit plays a critical role in determining the current flow and the behavior of the circuit under operation. It represents the device or component that is being powered by the circuit. The design of the power supply must account for the expected load resistance to ensure stable operation and prevent overloading.

7. [Conductive Wires](https://makerbazar.in/cdn/shop/files/JUMPER-WIRE_8ed6d739-ee06-4590-bbff-c7a413ec8cfc.jpg?v=1705234278): Essential for making electrical connections between different components in the circuit. They provide a pathway for the flow of electric current, ensuring that signals and power can be effectively transmitted throughout the circuit. These wires connect various components such as resistors, capacitors, and power supplies, forming a complete and functional circuit. They also help in organizing the layout of the circuit on a breadboard, making it easier to troubleshoot and modify.

8. [Oscilloscope](https://bkpmedia.s3.us-west-1.amazonaws.com/photos/2194_front_lrg.jpg): is used for monitoring and analyzing the waveform of the voltage at different points in the circuit. It allows the user to visualize the AC input, the rectified DC output, and the effects of the filtering and regulation process. By observing the voltage waveform on the oscilloscope, engineers and technicians can ensure that the circuit is functioning correctly, that the voltage is stable, and that there are no excessive ripples or fluctuations. It helps to diagnose issues, such as improper rectification or regulation, and provides real-time feedback on the performance of the power supply.

9. [National Instruments Multisim](https://download.ni.com/support/manuals/374483a.pdf): A powerful circuit simulation software used for designing, prototyping, and testing electronic circuits. It offers a wide range of tools for simulating analog, digital, and mixed-signal circuits, helping to visualize and analyze circuit behavior in real-time. Multisim's extensive component library makes it ideal for both educational and professional use.

The detailed calculations regarding the values chosen for each of the circuit building components and any supporting assumptions will be thoroughly elaborated in the subsequent section, to provide a comprehensive understanding of the underlying processes.


## Design Procedure

You cannot represent a smartphone's load as a fixed 1k ohm resistor in your circuit because the resistance of a smartphone during charging is not constant and varies dynamically based on factors like the battery's state of charge, charging mode (standard vs. fast charging), and internal circuitry. Smartphones do not behave like passive resistors, as their current draw depends on the charging stage and the internal charging circuitry. For example, during fast charging, the phone actively negotiates higher voltages and currents (e.g., 9V, 2A), which translates to a much lower effective resistance, calculated by Ohm’s law as $$R = \frac{V}{I} = \frac{5V}{2A} = 2.5 \, \Omega$$. A 1k ohm resistor, on the other hand, would limit the current to $$I = \frac{V}{R} = \frac{5V}{1000 \, \Omega} = 5 \, \text{mA}$$, which is far too small for proper charging (most phones need at least 1A to 3A). The phone’s battery and its management system act as a complex, nonlinear load, with the battery's internal resistance changing depending on its charge level and temperature. For instance, during the early stages of charging, the resistance is lower to allow higher current flow, and as the battery fills up, the current decreases, and the effective resistance rises. Modern smartphones use buck converters or similar circuits to regulate the input power efficiently, adjusting the current and voltage dynamically. Thus, a smartphone’s resistance is much lower than 1k ohm and varies as it charges. To simulate a phone’s behavior accurately in a circuit, a dynamic load model or a current sink can be used, with typical charging scenarios having an effective resistance of $$R = 5 \, \Omega$$ for standard charging (5V, 1A), $$R = 4.5 \, \Omega$$ for fast charging (9V, 2A), and $$R = 4 \, \Omega$$ for higher power charging (12V, 3A). Despite this, however, we will design our circuit with the assumption that we have a fixed load. Later, we will calculate the range of load values that this circuit can effectively havdle without the DC output value being sabotaged.

In my Multisim simulation, through steps [1](Photos/howtocustomize.png) and [2](Photos/customizing-the-diode-in-multisim.png), I customized the 1N4728A Zener diode to have a breakdown voltage rating of 3.0V, instead of its original 3.3V rating, as I was unable to find a component in the library that met my specific requirements. Since the 1N4728A was the closest available option, I modified its parameters by adjusting the breakdown voltage setting within the component properties. This allowed me to simulate the desired behavior of the Zener diode for my circuit, despite the library limitation. Although this modification is only an approximation, it enables me to model the voltage regulation characteristics I need for the project. This was also a good exercise, as we had never before edited the parameters of the components in the Multisim database. Learning how to modify and adjust these parameters allowed us to customize the behavior of the components in the circuit to better suit our design requirements, providing deeper insights into the simulation process. This is why you will find a star next to the component's name in the simulation photos in the next section.

Our [plan](Photos/block-diagram.png) involves multiple steps of design. First, we know 4 things, The $V_{rms(in)} = 220 V$, the $V_{out} = 3 V$, and that the typical frequency of the AC mains in the UAE is 50 Hz. We also know that the 4 diodes in our full bridge rectifier have a 0.7 V across each of them, and since only 2 conduct every half cycle then we have a $2 \times 0.7 = 1.4 V$ voltage drop each half cycle. In our design, we are targeting a voltage ripple of 0.3 V, as this value strikes a practical balance between performance, cost, and complexity. While achieving a 0 V ripple might seem ideal, it would require significantly larger and more expensive components, such as high-capacity capacitors or more complex filtering stages, which could increase both the size and cost of the circuit. Additionally, reducing the ripple to zero often yields diminishing returns, as most electronic devices can tolerate a small amount of ripple without any significant impact on their functionality. A ripple of 0.3 V is generally within the tolerance limits of most components and is sufficient for the proper operation of the load, which may have their own internal regulation to further smooth out any fluctuations. We also have in mind a future plan of implementing this circuit in a laboratory where such expensive and capable capacitors may not exist. Therefore, designing for a 0.3 V ripple is a reasonable and efficient approach that meets the performance requirements while keeping the design both cost-effective and realizable in real life. 

### 1. **Input Voltage Calculation:**
The input AC voltage is first converted to DC using a full bridge rectifier. The peak voltage $V_p$ is calculated as follows:
$$V_p=\frac{220}{\sqrt{2}}=155.5\, \text{V}$$

### 2. **Transformer Turns Ratio:**
The transformer steps down the voltage. The turns ratio $n$ of the transformer is the ratio of the number of turns in the primary coil to the secondary coil. This can be calculated by the ratio of the primary voltage $V_p$ to the secondary voltage $V_s$:
$$n=\frac{\text{number of primary turns}}{\text{number of secondary turns}}=\frac{V_p}{V_s}=\frac{200}{10}=22$$

### 3. **Rectifier Input Voltage:**
The input to the full bridge rectifier is the peak voltage $V_p$, which is calculated from the RMS value $V_{rms}$ of the secondary voltage of the transformer:
$$V_p=\sqrt{2}\times V_{rms}=\sqrt{2}\times 10=14.1\, \text{V}$$

### 4. **Rectifier Output Voltage:**
After the full bridge rectifier, the output voltage $V_{\text{rectifier}}$ is calculated by subtracting the voltage drops across the two diodes (each diode has a voltage drop of 0.7V):
$$V_{\text{rectifier}}=V_p-2V_{\text{diodes}}=14.1-1.4=12.7\, \text{V}$$

### 5. **Filtering Capacitor Calculation:**
To achieve a small ripple voltage of 0.3V, the value of the filtering capacitor $C$ can be calculated using the following formula:
$$V_{\text{ripple}}=\frac{V_p}{2 f R_L C}$$

Substituting the given values:
$$0.3=\frac{12.7}{2\times 50\times 1000\times C}$$

Solving for \(C\):
$$C=\frac{12.7}{2\times 50\times 1000\times 0.3}=430\, \mu\text{F}$$

### 6. **Filtered Output Voltage:**
Now, using the capacitor value, we can calculate the final output voltage after filtering. The filtered output $V_r$ is calculated as:
$$V_r=V_{\text{rectifier}}-\frac{V_{\text{rectifier}}}{2 f R_L C}$$

Substituting the values:
$$V_r=12.7-\frac{12.7}{2\times 50\times 1000\times (470\times 10^{-6})} = 12.4V$$

This yields the filtered output voltage.

### 7. **Dynamic Resistance of the Zener:**
We picked a value of 5 mA in the acceptable range of currents for the Zener diode and proceeded to calculate the $R_z$ as peak voltage of the circuit after the transformer stage minus the Zener voltage all over the current of the Zener. Which yielded $$\frac{10\sqrt{2} - 3}{5 \times 10^{-3}} = 2.2 \, \text{k}\Omega$$.

### 8. **Zener Diode Voltage Regulation:**
The Zener diode is used to clamp the voltage to a target value of 3.0V. Although the Zener diode has a nominal breakdown voltage rating of 3.1V, the output voltage will reach the target of 3.0V due to the small voltage drop of 0.1V across the Zener diode and the series resistor. This small voltage drop ensures that the output voltage is maintained at the desired 3.0V.



## Implementation & Analysis 

<p align="center">
  <img src="Photos/actodc-circuit.png"/>
</p>

Shown above is the input signal and the resulting output voltage of the circuit, which is 3V. The circuit is functioning as expected through our manual calculations. We have placed various probes around the circuit to keep track of the voltage and current values throughout the circuit and that they are valued as intended. We can calculate the power as: $$P = I_z \times V_z = 3.07 \times 10^{-3} \times 3.0 = 9.21\, \text{mW}$$. This agrees with the result displayed on the wattmeter and is well within the Zener diode's power rating of 1W, as per its datasheet, so we are operating in safe conditions. Analyzing the power efficiency of the circuit involves comparing the output power delivered to the load with the input power from the AC source, considering component losses. 

Power efficiency refers to the ratio of useful output power to the total input power consumed by a system, expressed as a percentage. It indicates how effectively a power supply or device converts input energy into useful work, with minimal energy wasted as heat or other forms of loss. High power efficiency is important because it reduces energy waste, lowers operating costs, and minimizes the need for cooling or additional infrastructure to dissipate heat. In electronic circuits, especially those in portable devices, efficient power conversion ensures longer battery life, less heat generation, and more reliable performance. For instance, in power supplies, improving efficiency means less energy is lost during voltage regulation or conversion, leading to more sustainable operation, less power consumption, and potentially lower environmental impact. The typical power efficiency of a 3V power supply circuit can vary widely depending on the design and components used.  If the power supply uses a linear voltage regulator (such as the Zener diode), the efficiency is typically low because the regulator dissipates excess energy as heat. As for our circuit, that would be $$\frac{V_{\text{out}}}{V_{\text{in}}} = \frac{3V}{14.1V} \times 100 = 21\%$$. A switching regulator (buck converter, for example) is much more efficient than a linear regulator. Efficiencies can range from 80% to 95%, depending on the design and load conditions. Power loss in the circuit comes from both the regulator and other components, including resistive losses in the wiring, diodes, and capacitors.

To calculate the **maximum current** that our circuit can supply, we can use the voltage and resistance relationships in the circuit instead of the power dissipation method. Starting with the equation $$V_{\text{pin}} - I \cdot R - V_{\text{Z}} = 0$$, where $$V_{\text{pin}}$$ is the peak input voltage, $$R$$ is the series resistor value, and $$V_{\text{Z}}$$ is the Zener diode's voltage. Substituting the values into the equation $$10\sqrt{2} - I \cdot (2.2 \times 10^3) - 3 = 0$$. Solving for $$I_{\text{max}}$$, we get $$5 \, \text{mA}$$. This current is limited by the series resistor and the input voltage constraints. Additional factors, such as the transformer, rectifier, and filtering capacitor, may further influence the actual current supplied by the circuit.


Finally, we can calculate the range of loads by considering the voltage and current characteristics of the power supply. First, let's establish that the minimum load corresponds to the highest current the circuit can provide without excessive voltage drop. The current will be limited by the maximum current capability of the power supply and the Zener diode's voltage regulation. On the other hand, the maximum load corresponds to the lowest current, ideally where the circuit doesn't drop below the desired output voltage due to the internal resistance of the circuit or power losses. For example, if the load is too high, the current will be too small. 

<p align="center">
  <img src="Photos/600.png" style="width: 49%; height: 220px;"/> <img src="Photos/800.png" style="width: 49%; height: 220px;" /> 
  <img src="Photos/2k.png" style="width: 49%; height: 220px;"/>  <img src="Photos/100k.png" style="width: 49%; height: 220px;" />
  <img src="Photos/1M.png" style="width: 49%; height: 220px;"/> <img src="Photos/1G.png" style="width: 49%; height: 220px;" />
</p>

Through testing my circuit on Multisim, I observed that **there is no upper limit** to the maximum load resistance that the circuit can support while maintaining a regulated DC output voltage of 3V. I tested load resistances up to **1 GΩ**, and the circuit continued to function correctly. This behavior arises due to the nature of Zener diode regulation, where the diode maintains a constant output voltage regardless of how small the current becomes as the load resistance increases. However, at very high resistances, the **output power becomes negligible**, as the current drawn by the load decreases significantly. On the other hand, I determined that the **minimum load resistance** that maintains the 3V output is **600 Ω**. At this point, the current drawn is high enough to meet the load requirements without exceeding the Zener diode's limitations. This lower bound is dictated by the current-handling capability of the Zener diode and the power constraints of the circuit. The theoretical minimum load resistance can be calculated using the following formula $$R_{\text{min}}=\frac{V_{\text{out}}}{I_{\text{max}}}$$. Substituting the values we get $$R_{\text{min}}=\frac{3}{5\times10^{-3}}=600\,\Omega$$

To enable the power supply to support loads **less than 300 ohms**, the circuit's **dynamic resistance**—primarily influenced by the Zener diode—plays a crucial role. A higher dynamic resistance can limit the amount of current delivered to the load, especially as the load resistance decreases. The **2.2kΩ resistor** in the circuit is likely part of the **current-limiting network** for the Zener diode or the voltage regulation setup. Reducing the value of this resistor would allow more current to flow to the load, thereby supporting lower load resistances. However, it is critical to ensure that the Zener diode can handle the increased current. If the current exceeds the Zener diode's maximum rating, it could overheat or fail. The **dynamic resistance** (or differential resistance) of the Zener diode refers to the effective resistance presented when the diode operates in its **reverse breakdown region**, regulating the voltage. This resistance is not constant; it depends on the operating point—specifically the voltage and current across the diode. When recalculating the dynamic resistance, the **current at the Zener diode's operating point** within its active reverse breakdown region must be considered to ensure accurate analysis and reliable operation of the circuit.

To recalculate the **dynamic resistance** of the Zener diode, we use the **I-V characteristic graph** from the datasheet. The dynamic resistance $$R_{\text{dyn}}$$ is defined as the change in voltage divided by the corresponding change in current: $$R_{\text{dyn}} = \frac{dV}{dI} = \frac{0.7 - 0.55}{1 \times 10^{-3} - 0.01 \times 10^{-3}} \approx 151.51 \, \Omega$$. This dynamic resistance represents the **small-signal behavior** of the Zener diode in the breakdown region. It is an important parameter when analyzing the Zener diode's response to small variations in current or voltage. This much smaller value will expand the range of loads that our circuit can support from the $R_{min}$ side. Now, our **maximum current** would be $$0.07 \, \text{A}$$, and our calculated **minimum load resistance** $$R_{\text{min}}$$ would be $$42.85 \, \Omega$$. However, during testing, I was able to use a load as low as $$20 \, \Omega$$, and the circuit still maintained a DC voltage of **3 V**. At this point, some **ripple** started to appear in the output because we should have also adjusted the value of the capacitor accordingly, but we are keeping it fixed.


<p align="center">
  <img src="Photos/rdyn151.png" style="width: 49%; height: 220px;"/> <img src="Photos/rdyn5.png" style="width: 49%; height: 220px;" /> 
</p>

From these observations, we concluded that the **larger the dynamic Zener resistance**, the **smaller the range of loads** supportable by the circuit will be. Interestingly, when I attempted to set the **dynamic resistance** $$R_{\text{dyn}}$$ to a very small value of $$5 \, \Omega$$, the circuit still regulated the voltage with loads as small as $$5 \, \Omega$$ even despite this not following the formulas that guide our design. Nonetheless, there were minor misregulations in the decimal values, as the output voltage was approximately **3.2 V** rather than the exact **3.0 V**. Further, we must be aware that this comes with the risk of potential overheating or excessive current depending on the Zener diode's limits, so this modification should be considered in light of the component’s ratings especially in real-life.


## Future Improvements

1. Using a Zener diode-based linear regulator results in low efficiency (21%). A significant future improvement would be to replace the Zener diode with a switching regulator, such as a buck converter, which can improve efficiency to 80-90%. This would reduce heat dissipation and improve overall power delivery.
2. Since smartphones and other devices have variable loads, a future improvement could be to model the load more accurately. Instead of using a fixed resistor, we could create a more dynamic load using a programmable current sink that can adjust based on voltage, simulating real-world charging conditions more closely.
3. While a 0.3V ripple is acceptable for many applications, a more refined filtering stage could reduce ripple further, improving the quality of the DC output. This could involve increasing the capacitance or adding an additional stage of filtering.
4. Reducing the number of components while maintaining performance could be another focus area. For instance, using integrated bridge rectifiers or combining multiple stages into one component might save space and reduce cost.
5. If the power supply needs to support multiple devices or provide higher power outputs, we should consider expanding the design to handle multiple output channels with adjustable voltages. This would be especially useful if we want to create a more versatile power supply that can serve different types of devices.
6. Experiment with other Zener models. Zener diodes have specific characteristics that can affect the efficiency of your circuit. Some Zener diodes may have better voltage regulation, lower dynamic resistance, or higher power ratings, which could improve the overall performance of the regulator. While the Zener diode-based design may inherently suffer from lower efficiency, experimenting with other Zener diode models might provide slight improvements. 


## Conclusion

In summary, the circuit operates as intended, delivering a stable 3.0V DC output, which is effectively regulated by the zener diode. Our theoretical calculations align with the simulation results, confirming the accuracy of our design approach. The 430 µF capacitor successfully smooths the rectified voltage, resulting in minimal ripple. Overall, the design demonstrates proper rectification, filtering, and voltage regulation, fulfilling the intended functionality.

A 3V supply is commonly used for low-power electronic devices and systems that require minimal current. It is particularly popular in small battery-operated devices because 3V can be conveniently provided by two 1.5V batteries (such as AA or AAA cells) connected in series or through coin cell batteries like the CR2032, which are widely used due to their compact size and long shelf life. Devices that typically use a 3V supply include remote controls, wristwatches, calculators, small sensors, and other consumer electronics. Many microcontrollers, such as those used in embedded systems and IoT devices, also operate at 3V or 3.3V, as this voltage is sufficient to power their internal circuits while minimizing energy consumption. Memory devices like EEPROMs, low-power LEDs, and certain wireless communication modules (e.g., Bluetooth Low Energy) also rely on 3V or 3.3V power supplies for efficient and stable operation. Additionally, 3V is often seen in CMOS-based digital logic circuits and systems, as it meets their low-voltage requirements without compromising functionality. Overall, 3V power supplies are ideal for applications where energy efficiency, small size, and low power consumption are critical considerations.

The typical DC voltage needed to charge phones nowadays is 5 volts, which is the standard voltage used by most USB charging ports and adapters. This voltage is regulated and supplied through USB Type-A, Type-C, or other USB connectors, ensuring compatibility with a wide range of smartphones and devices. Modern phone chargers often incorporate advanced technologies like fast charging or quick charging, which can deliver higher power by increasing the current (measured in amperes) or temporarily boosting the voltage to levels such as 9V, 12V, or even higher, depending on the device and charger compatibility. For instance, technologies like USB Power Delivery (USB-PD) or Qualcomm's Quick Charge allow devices to negotiate with the charger for higher voltages and currents, enabling faster charging without damaging the phone's battery. Despite these advancements, the initial 5V standard remains the baseline for most phone chargers, ensuring universal compatibility and safe charging for a variety of devices, especially older models or when connected to standard USB ports.

The Ohm load of devices, such as phones, represents the equivalent resistance seen by the AC-to-DC circuit supplying power to the device. This resistance is not static but varies dynamically depending on the charging stage, the battery's internal resistance, and the current drawn during the charging process. For phones, the load can be approximated using Ohm’s Law (V = IR). At 5V, with a charging current of about 1A to 3A (common in standard and fast-charging scenarios), the equivalent resistance (R = V/I) ranges from approximately 1.67 ohms to 5 ohms. When fast charging with higher voltages like 9V or 12V, the effective resistance becomes lower as the current increases, allowing for faster energy delivery to the device. In other devices requiring power supplies, the ohm load similarly depends on their voltage and current needs. For example, LED strips often run at 12V DC, drawing currents from 0.5A to 2A, which corresponds to an equivalent resistance of 6 ohms to 24 ohms. Microcontroller-based systems or sensors, which typically operate at 3.3V or 5V, might draw smaller currents like 100mA to 500mA, yielding resistances of 6.6 ohms to 50 ohms. Larger systems, such as laptop chargers operating at 19V DC with currents around 3A to 6A, see a load of 3.2 ohms to 6.3 ohms. Industrial equipment or motors operating at higher DC voltages, like 24V or 48V, may draw significant current, resulting in correspondingly lower ohm loads.

In commercial practice, discussions about chargers and power supplies primarily focus on their power rating (measured in watts) and their DC voltage output. The power rating provides a straightforward measure of the supply’s ability to deliver energy, calculated as $P = V \times I$. For example, a phone charger may be advertised as a 10W (5V, 2A) or 18W (9V, 2A) fast charger. Higher-wattage ratings, such as 65W or 100W USB-C chargers, are often used for laptops or multi-device charging. Voltage ratings are also significant, especially when compatibility with specific devices is required, as seen with the 5V standard for USB ports or specialized voltages for industrial and computing systems. However, power (in watts) tends to headline discussions because it reflects the overall capability of the power supply to deliver energy, while voltage and current specifications are provided to ensure compatibility and safety with devices.




```mermaid
gantt
    title Work Division Gantt Chart
    tickInterval 1day
    todayMarker off
    axisFormat %a-%Y-%m-%d
    section Research         
        Nour Mostafa : 2024-11-29 00:00, 1d
        Dema Ammar : 2024-11-25 00:00, 2d
        Asma Aldhaibani : 2024-11-27 00:00, 2d
        Mariam Elhelaly : 2024-12-01 00:00, 3d
    section Multisim         
        Mariam Elhelaly : 2024-12-01 00:00, 2d
        Asma Aldhaibani : 2024-11-29 00:00, 2d
    section Analysis       
        Mariam Elhelaly : 2024-12-03 00:00, 2d
        Nour Mostafa :  2024-12-03 00:00, 1d
    section Report
        Nour Mostafa : 2024-12-4 00:00, 2d
```

We extend our sincere appreciation to Dr. Ali Al Ataby for his insightful feedback which has significantly contributed to the completion of this project.
This publication adheres to all regulatory laws and guidelines established by the American University of Ras Al Khaimah (AURAK) regarding the dissemination of academic materials.


## Resources
|1| AC/DC Power Supply Design in 7 Steps. (n.d.). <br> http://www.fsp-group.com/en/knowledge-tec-23.html  
|2| Brief-Biography (Director). (2017, October 8). Convert AC 220v to DC 12v Circuit Simulate in Proteus. <br> https://www.youtube.com/watch?v=9UaQQE9GXqg  
|3| brmarcum. (n.d.). AC to DC Conversion. Instructables. <br> https://www.instructables.com/AC-to-DC-Conversion/  
|4| DIY Circuits (Director). (2020, May 17). How to make 220v AC to 3v DC converter. <br> https://www.youtube.com/watch?v=7UsdRUU8Xq8  
|5| Power Supplies | Electronics Club. (n.d.). <br> https://electronicsclub.info/powersupplies.htm  
|6| RJ EDIT ALL (Director). (2024, January 7). Convert 220v ac to 3v 6v 9v 12v 24v 48v DC Out driver Circuit, multi converter. <br> https://www.youtube.com/watch?v=JuAzHa5LNWc  
|7| sncarter. (n.d.). The Simplest, Cheapest 3.3V Power Supply in the Universe. Instructables. <br> https://www.instructables.com/The-Simplest-Cheapest-33V-Supply-in-the-Universe/  
|8| The Engineer Solutions (Director). (2020, November 27). How to Make a Power Supply in Ni-Multisim | 5 volt power supply. <br> https://www.youtube.com/watch?v=FCmUJJs09o8  
|9| The Organic Chemistry Tutor (Director). (2020, February 5). 220V AC to 12V DC Converter Power Supply Using Diodes, Capacitors, Resistors, & Transformers. https://www.youtube.com/watch?v=lKhmNanDkPY  
