Download Link: https://assignmentchef.com/product/solved-ee746-assignment1-spiking-neuron-models
<br>
In this assignment, we will learn how to model the activity of spiking neurons starting with the simplest model. We will also implement the Hodgkin-Huxley neuron model and use it to determine an estimate of the energy cost associated with a spike.

Problem 1: Leaky Integrate and Fire Model

The dynamics of the membrane potential <em>V </em>(<em>t</em>), in the LIF neuron model is given by the equation

)                                                 (1)

<em>C </em>is the membrane capacitance, <em>g<sub>L </sub></em>is the leak conductance and <em>E<sub>L </sub></em>is the leak reversal potential. <em>I<sub>app </sub></em>is the externally applied current and is assumed to be positive for current flowing into the cell.

When <em>V </em>≥ <em>V<sub>T </sub></em>, a spike is issued and <em>V </em>is reset to <em>E<sub>L </sub></em>(We will write this as <em>V </em>(<em>t</em>) −→ <em>E<sub>L</sub></em>). (Assume that C= 300 pF, g<em><sub>L </sub></em>= 30 nS, <em>V<sub>T </sub></em>= 20 mV and E<em><sub>L </sub></em>= −70 mV).

<ul>

 <li>Assume that a constant current <em>I</em><sub>0 </sub>is applied to the neuron. Write an expression for the steady state value of the membrane potential. Hence, determine the minimum value of the steady state current, <em>I<sub>c </sub></em>necessary to initiate a spike. <strong>2 points</strong></li>

 <li>In order to simulate the behavior of a set of <em>N </em>neurons, it is useful to define a <em>N </em>× 1 column vector to the store the membrane potentials of the <em>N </em> Write a program to solve the equivalent difference equation numerically using Runge-Kutta second order method for a set of <em>N </em>neurons driven by external current input. (You should not use a FOR loop to calculate the potential of the <em>N </em>neurons, rather, the potential of all the neurons should be calculated in one step.)</li>

</ul>

Assume that the input to the program is a <em>N </em>×<em>M </em>column vector, representing the input current for the <em>N </em>neurons for <em>M </em>time-intervals where <em>M </em>= <em>T/</em>∆<em>t</em>. The output of your program should be a <em>N </em>× <em>M </em>matrix storing the values of the membrane potential for the <em>N </em>neurons, for the <em>M </em>time-intervals.

<ul>

 <li>We would like to now use this framework to study the dynamics of LIF neurons. Assumethat you have a population of 10 identical neurons, with each neuron receiving a constant current. Let the magnitude of the input current for the <em>k<sup>th </sup></em>neuron be given by the expression</li>

</ul>

<em>I<sub>app,k </sub></em>= (1 + <em>kα</em>)<em>I<sub>c                                                                                                                                   </sub></em>(2)

where <em>α </em>= 0<em>.</em>1. (In this example, the current does not vary with time, so, all the values across any row of the input current matrix is a constant). Plot the membrane potential for neurons 2<em>,</em>4<em>,</em>6 and 8 from <em>t </em>= 0 to 500 ms. (Assume ∆<em>t </em>= 0<em>.</em>1 ms and at <em>t </em>= 0, the neuron is in steady-state with

<table width="672">

 <tbody>

  <tr>

   <td width="609"><em>I<sub>app</sub></em>(<em>t</em>) = 0).</td>

   <td width="63"> </td>

  </tr>

  <tr>

   <td width="609">(d) Plot the average time interval between spikes from (c) as a function of <em>I<sub>app,k</sub></em>.</td>

   <td width="63"> </td>

  </tr>

 </tbody>

</table>

<h2>Problem 2: Izhikevich Model</h2>

The dynamics of the membrane potential <em>V </em>(<em>t</em>), in the Izhikevich neuron model is given by the equations

)                                (3)

)]                                                                (4)

When <em>V </em>(<em>t</em>) ≥ <em>v<sub>peak</sub></em>, <em>V </em>(<em>t</em>) −→ <em>c </em>and <em>U</em>(<em>t</em>) −→ <em>U</em>(<em>t</em>) + <em>d</em>.

By varying the parameters <em>C,E<sub>r</sub>,E<sub>t</sub>,k<sub>z</sub>,a,b,c </em>and <em>d</em>, a variety of neuronal behaviors can be modeled.

<table width="650">

 <tbody>

  <tr>

   <td width="38"> </td>

   <td width="68">C(pF)</td>

   <td colspan="2" width="136"><em>k<sub>z</sub></em>(<em>µ</em>S/V) <em>E<sub>r</sub></em>(mV)</td>

   <td width="68"><em>E<sub>t</sub></em>(mV)</td>

   <td colspan="2" width="136">a (KHz) b(nS)</td>

   <td width="68">c(mV)</td>

   <td width="68">d(pA)</td>

   <td colspan="2" width="68"><em>v<sub>peak</sub></em>(mV)</td>

  </tr>

  <tr>

   <td width="38">RS</td>

   <td width="68">100</td>

   <td width="68">0<em>.</em>7</td>

   <td width="68">−60</td>

   <td width="68">−40</td>

   <td width="68">0<em>.</em>03</td>

   <td width="68">−2</td>

   <td width="68">−50</td>

   <td width="68">100</td>

   <td colspan="2" width="68">35</td>

  </tr>

  <tr>

   <td width="38">IB</td>

   <td width="68">150</td>

   <td width="68">1<em>.</em>2</td>

   <td width="68">−75</td>

   <td width="68">−45</td>

   <td width="68">0<em>.</em>01</td>

   <td width="68">+5</td>

   <td width="68">−56</td>

   <td width="68">130</td>

   <td colspan="2" width="68">50</td>

  </tr>

  <tr>

   <td width="38">CH</td>

   <td width="68">50</td>

   <td width="68">1<em>.</em>5</td>

   <td width="68">−60</td>

   <td width="68">−40</td>

   <td width="68">0<em>.</em>03</td>

   <td width="68">+1</td>

   <td width="68">−40</td>

   <td width="68">150</td>

   <td colspan="2" width="68">25</td>

  </tr>

  <tr>

   <td colspan="9" width="582">(a) What are the steady state values of <em>V </em>and <em>U </em>for <em>I<sub>app </sub></em>= 0?</td>

   <td width="67"> </td>

   <td width="1"> </td>

  </tr>

  <tr>

   <td colspan="9" width="582">(b) Write the equivalent difference equations for (3) and (4).</td>

   <td width="67"> </td>

   <td width="1"> </td>

  </tr>

 </tbody>

</table>

(c) Write a program to solve the equivalent difference equation for a set of <em>N </em>Izhikevich model neurons using Runge-Kutta fourth order method. The neuron type should be a parameter in your function call, for each of the N neurons. You may use ∆<em>t </em>= 0<em>.</em>1 ms and plot the response of the three neurons above from <em>t </em>= 0 to 500 ms, for <em>I<sub>app </sub></em>= 400<em>,</em>500<em>,</em>600 pA.

Note: Try to re-run 2(c) with larger values of ∆<em>t</em>. You will notice that the overall dynamics can change drasticially, especially for neuron CH. This is because of the inaccuracy in determining the exact time when <em>V </em>(<em>t</em>) exceeds <em>v<sub>peak</sub></em>. For a good description of this issue and how to get around it, see: <em>Hybrid spiking models, Phil. Trans. R. Soc. A November 13, 2010 368 (1930) 5061-5070</em>.

We will ignore these issues here, and for the sake of displaying, you may chose to artificially set the value of membrane potential just before reset to <em>v<sub>peak </sub></em>in your code.

<h2>Problem 3: Adaptive Exponential Integrate-and-Fire Model</h2>

The dynamics of the membrane potential <em>V </em>(<em>t</em>), in the AEF neuron model is given by the equations

)                 (5)

)                                                                                   (6)

When <em>V </em>(<em>t</em>) ≥ 0, <em>V </em>(<em>t</em>) −→ <em>V<sub>r </sub></em>and <em>U</em>(<em>t</em>) −→ <em>U</em>(<em>t</em>) + <em>b</em>.

As before, by varying the parameters a variety of neuronal behaviors can be modeled.

<table width="650">

 <tbody>

  <tr>

   <td width="38"> </td>

   <td width="68">C(pF)</td>

   <td width="68"><em>g<sub>L</sub></em>(ns)</td>

   <td width="68"><em>E<sub>L</sub></em>(mV)</td>

   <td width="68"><em>V<sub>T </sub></em>(mV)</td>

   <td colspan="2" width="136">∆<em><sub>T </sub></em>(mV) a(nS)</td>

   <td width="68"><em>τ<sub>w</sub></em>(ms)</td>

   <td width="68">b(pA)</td>

   <td width="68"><em>V<sub>r</sub></em>(mV)</td>

  </tr>

  <tr>

   <td width="38">RS</td>

   <td width="68">200</td>

   <td width="68">10</td>

   <td width="68">−70</td>

   <td width="68">−50</td>

   <td width="68">2</td>

   <td width="68">2</td>

   <td width="68">30</td>

   <td width="68">0</td>

   <td width="68">−58</td>

  </tr>

  <tr>

   <td width="38">IB</td>

   <td width="68">130</td>

   <td width="68">18</td>

   <td width="68">−58</td>

   <td width="68">−50</td>

   <td width="68">2</td>

   <td width="68">4</td>

   <td width="68">150</td>

   <td width="68">120</td>

   <td width="68">−50</td>

  </tr>

  <tr>

   <td width="38">CH</td>

   <td width="68">200</td>

   <td width="68">10</td>

   <td width="68">−58</td>

   <td width="68">−50</td>

   <td width="68">2</td>

   <td width="68">2</td>

   <td width="68">120</td>

   <td width="68">100</td>

   <td width="68">−46</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>Write the equivalent difference equations for (5) and (6).</li>

 <li>What are the steady state values of <em>V </em>and <em>U </em>for <em>I<sub>app </sub></em>= 0? (Determine the answer numerically, such that the value of <em>V </em>is accurate within ±1<em>µ</em>V).</li>

 <li>Write a program to solve the equivalent difference equation for a set of <em>N </em>AEF model neurons using Euler method. The neuron type should be a parameter in your function call, for each of the N neurons. You may use ∆<em>t </em>= 0<em>.</em>1 ms and plot the response of the three neurons above from <em>t </em>= 0 to 500 ms, for <em>I<sub>app </sub></em>= 250<em>,</em>350<em>,</em>450 pA. <strong>Problem 4: Spike energy based on Hodgkin-Huxley neuron model</strong></li>

</ul>

The dynamics of the membrane potential <em>V </em>(<em>t</em>), in the Hodgkin-Huxley neuron model is given by the equations

)                                           (7)

<table width="672">

 <tbody>

  <tr>

   <td width="630">where</td>

   <td width="42"> </td>

  </tr>

  <tr>

   <td width="630">                                                                            <em>i<sub>Na</sub></em>(<em>t</em>)    =      <em>g<sub>Na</sub>m</em><sup>3</sup><em>h</em>(<em>V </em>(<em>t</em>) − <em>E<sub>Na</sub></em>)</td>

   <td width="42">(8)</td>

  </tr>

  <tr>

   <td width="630">                                                                              <em>i<sub>K</sub></em>(<em>t</em>)    =      <em>g<sub>K</sub>n</em><sup>4</sup>(<em>V </em>(<em>t</em>) − <em>E<sub>K</sub></em>)</td>

   <td width="42">(9)</td>

  </tr>

  <tr>

   <td width="630">                                                                                <em>i<sub>l</sub></em>(<em>t</em>)    =     <em>g<sub>l</sub></em>(<em>V </em>(<em>t</em>) − <em>E<sub>l</sub></em>)The variables <em>n,m </em>and <em>h </em>lie in the interval [0<em>,</em>1] and obey the equation</td>

   <td width="42">(10)</td>

  </tr>

 </tbody>

</table>

(11)

where

<em>β<sub>n</sub></em>(<em>t</em>) = 0<em>.</em>125exp(−(<em>V </em>(<em>t</em>) + 65)<em>/</em>80)         (12)

<em>β<sub>m</sub></em>(<em>t</em>) = 4exp(−0<em>.</em>0556(<em>V </em>(<em>t</em>) + 65))           (13)

(14)

<em>V </em>(<em>t</em>) is assumed to be measured in mV in the above expressions.

Assume that C=1<em>µ</em>F<em>/</em>cm<sup>2</sup>, <em>E<sub>Na </sub></em>= 50 mV, <em>E<sub>K </sub></em>= −77 mV and <em>E<sub>l </sub></em>= −55 mV and <em>g<sub>Na </sub></em>= 120 mS<em>/</em>cm<sup>2</sup>, <em>g<sub>K </sub></em>= 36 mS<em>/</em>cm<sup>2 </sup>and <em>g<sub>l </sub></em>= 0<em>.</em>3 mS<em>/</em>cm<sup>2</sup>.

<ul>

 <li>Solve the equivalent difference equations for (7) and (11) to determine the ion currents andthe membrane potential for a step current waveform described as follows:</li>

</ul>

<em>I<sub>ext</sub></em>(<em>t</em>) = <em>I</em><sub>0</sub>[<em>H</em>(<em>t</em>−2<em>T</em>)−<em>H</em>(<em>t</em>−3<em>T</em>)] where <em>H</em>(<em>x</em>) is the Heaviside step function defined as <em>H</em>(<em>x</em>) = 1 if <em>x </em>≥ 0 and <em>H</em>(<em>x</em>) = 0 otherwise. You should set your initial conditions such that there are no spikes when there is no external input current to the neuron. Assume <em>I</em><sub>0 </sub>= 15<em>µ</em>A<em>/</em>cm<sup>2</sup>, ∆<em>t </em>= 0<em>.</em>01 ms, <em>T </em>= 30ms.

<ul>

 <li>The instantaneous power dissipated (per unit area) in the various ion channels can beapproximated by the expression</li>

</ul>

<em>P<sub>x</sub></em>(<em>t</em>) = <em>i<sub>x</sub></em>(<em>t</em>)(<em>V </em>(<em>t</em>) − <em>E<sub>x</sub></em>)                                                          (15)

Similarly, the power spent in charging/discharging the membrane capacitance (per unit area) can be approximated as

)                                (16)

Plot the relative magnitudes of the instantaneous power dissipated in the three ion channels and in the membrane capacitor as a function of time for one cycle of the action potential.

Numerically integrate the power in (b) to determine the total energy dissipated in one cycleof the action potential for a patch of the cell membrane with area of 1 <em>µm</em><sup>2 </sup>