Download Link: https://assignmentchef.com/product/solved-uwee572-lab2-analysis-of-coupled-noises-on-pcb
<br>
If TDS8200 has only two channels (Ch1 and Ch2), Ch1 will be used as the source channel (TDR ON) and Ch2 will be used as a receive channel (TDR OFF).   The RF switch box is connected to Ch2 so that two signals (Ch A and Ch B) can be monitored by selecting the lines.

If DUT has 3 or 4 ports, the unused ports must be terminated with a matched impedance (or the load condition specified in this lab).

I. Objectives

This lab is to introduce the characteristics of backward and forward coupled noises on coupled transmission lines.  You will also study how to obtain the coupling coefficients and lumped element models from the measured data.  Data must be saved on a PC so that you can process and analyze it. It is assumed that you are already familiar with TDR.

The coupled lines are fabricated on a FR4 PCB and the TL structure is microstrip TL.  As we studied in the coupled line section, the backward coupled noise is related to (K<sub>C</sub>+K<sub>L</sub>) while the forward coupled noise is related to (K<sub>C</sub>-K<sub>L</sub>). The coupled lines using the microstrip TL show the forward coupled noise because K<sub>C</sub> is not equal to K<sub>L</sub>. Whereas the stripline TL in which we have K<sub>C</sub>=K<sub>L, </sub>does not create the forward coupled noise. One of the objects of this lab is to estimate K<sub>C</sub> and K<sub>L</sub> from the time-domain response. Because K<sub>C</sub> and K<sub>L</sub> are given by equivalent capacitors and inductors of the coupled lines, we should also be able to estimate the values of these lumped elements using additional relationships.

<strong>Reference:</strong>

EE480 lecture note on coupled lines

TDS8200 users note

<h1>II. Experimental setup</h1>

Lab Equipment:

TDS8200 and Switch box

TDS8200 TDR with 80E04 (TDR head)

Figure 1: A TDS8200 Digital Sampling Oscilloscope. A Sampling Module

Figure 2: Setup

Test boards

TL PCB with different coupling characteristics Use A, B and C samples on PCB.

<u> Coupled Lines              |             A          |             B          |             C          |</u>

<u> Coupled length     <em>d</em>       |            10cm     |            10cm     |            5cm       |</u>

<u> Line separation     <em>s</em>       |            0.5mm  |            1mm     |            0.5mm  |</u>

Test cables:

Cable 1: Blue

Cable 2: Blue

Cable 3: Blue

Cable 4: Short black cable for an extra delay line

Load and devices

SHORT

OPEN (No connection.   Strictly speaking this is not OPEN.) THRU

<h1>III. Experimental procedure</h1>

<strong>(1) Turn ON TDS8200 and SW box.</strong>

Make sure the Tx output of SW-box is connected to the microwave switch (gray cable). The center SMA connector of the microwave switch must be connected to Ch2 of TDS8200. SW box has two switches.  Only the left side switch (show Ch A and Ch B) is used in this lab.

<h2>(2) Connect cables and obtain the characteristics of the input waveforms and calibration of Ch A (cable 2) and Ch B (cable 3)</h2>

The gain responses of Ch A and Ch B may not be the same and we need to check them.

Using the THRU measurement, obtain the peak voltage and rise time of the input signal.

Connect the TDR cable (Ch1) and Ch A directly as shown below. Select Ch A using the SW box.  Save Ch A data and use MATLAB or other software to get the peak voltage and rise-time.

Similarly, connect the TDR cable (Ch1) and Ch B directly as shown below. Select Ch A using the SW box.  Save Ch B data and use MATLAB or other software to get the peak voltage and rise-time.

Note: The responses (rise-time, voltage level) of Ch A and Ch B may not be the same due to the microwave switch and different cables.

<h2> (3) Reflected, Backward and forward coupled noise measurements</h2>

Connect the TDR input (Ch1) to the main line (start with the coupled line A), Ch A to the backward coupled path, and Ch B to the forward coupled path as shown below.  Also connect Cable 4 (short black cable) to the transmitted output as shown below.  Terminate the end of Cable 4 by <strong>SHORT </strong>termination.

Save Ch 1, Ch A and Ch B responses.  Ch 1 data (reflection) is also used for the analysis. This can be used for estimating the characteristics impedance of the coupled lines.

<ul>

 <li>Get data with SHORT connected at the end of Cable 4.</li>

 <li>Get data without SHORT (OPEN circuit) connected at the end of Cable 4.</li>

</ul>

<strong>(4) Repeat the same measurements for coupled lines B and C.  Make sure to connect four cables the same way.</strong>

<h1>IV. Analysis and estimation of K<sub>C</sub> and K<sub>L</sub></h1>

We will use <em>V</em><sub>f</sub> and <em>V</em><sub>b</sub> to estimate K<sub>C</sub> and K<sub>L</sub> for different coupled lines.

<strong>Note:  Use the 1st responses of <em>V</em></strong><strong><sub>f</sub> and <em>V</em></strong><strong><sub>b</sub>. The responses due to the reflected signal from OPEN and SHORT are not good (attenuated and distorted). </strong>Using the simple analysis, we have the following relationships.

<sub> </sub>

Applicable if the slope of <em>V</em><sub>in</sub> has a linear slope.         <em>V</em><sub>peak</sub>: Peak value of <em>V</em><sub>in</sub>. Also v<sub>o</sub> is the signal speed.




<ul>

 <li>Obtain the signal speed v<sub>o</sub> on the TL using <em>V</em><sub>b</sub> Assume it is a square wave</li>

</ul>

and the signal duration is given by .  Since <em>d </em>is known, v<sub>o</sub> can be obtained from this.

<ul>

 <li>Using the peak values of <em>V</em><sub>b</sub> (voltage on a flat section) and <em>V</em><sub>f</sub> (peak), estimate K<sub>C</sub> and</li>

</ul>

<ol>

 <li>K<sub>L</sub>. This can be done by solving two equations for K<sub>C</sub> and K<sub>L</sub>.  simply becomes <em>V</em><sub>peak</sub>.</li>

</ol>

<ul>

 <li>Integrate <em>V</em><sub>f</sub> and <em>V</em><sub>b </sub>over time.  Using the integration method, estimate the values of K<sub>C</sub> and K<sub>L</sub>. We get the following two equations.</li>

</ul>

The left-hand side will be the integration of the measured data.  The right-hand side contains K<sub>C</sub> and K<sub>L</sub>.  Since we know <em>V</em><em><sub>p</sub></em><sub>eak</sub>, <em>v</em><sub>o</sub> and <em>d</em>, we should be able to find K<sub>C</sub> and K<sub>L</sub>.

<h1>V. Estimation of C<sub>1G</sub>, C<sub>2G</sub>, C<sub>12</sub>, L<sub>11</sub>, L<sub>22</sub>, and L<sub>12</sub></h1>

The coupled lines can be expressed using the self-capacitance (C<sub>1G</sub>=C<sub>2G</sub>), mutual capacitance (C<sub>12</sub>), self-inductance (L<sub>11</sub>=L<sub>22</sub>), and mutual inductance (L<sub>12</sub>).  Using K<sub>C</sub>, K<sub>L</sub>, velocity, and one other value that we can measure, we should be able to find the values of

6 lumped elements.  Estimate the values of C<sub>1G</sub>, C<sub>2G</sub>, C<sub>12</sub>, L<sub>11</sub>, L<sub>22</sub>, and L<sub>12 </sub>for 3 different coupled lines using the experimental data.

<h1>VI. Questions</h1>

<ol>

 <li>What are the effects of SHORT and OPEN at the end of Cable 4? What happens to the polarities (negative or positive signs) of backward and forward coupled noises correct as you change the load?  Explain the phenomena based on the rise or fall of the incident signal which is creating coupled noises.</li>

 <li>K<sub>c</sub> and K<sub>L</sub> depend on the separation <strong><em>s</em></strong> but they should be independent of the length <strong><em>d</em></strong>. Show if this is correct or not, using the measured data.</li>

 <li>The incident signal is a unit step function and an unknown load is attached to the thru section. The waveforms of forward and backward coupled noises are shown below.</li>

</ol>

Top: forward coupled noise, Bottom: backward coupled noise Time-scale of top and bottom may not be the same.

<ul>

 <li>What type of load is attached at Port 2 (thru port)?</li>

 <li>Waveforms A and B are two forward coupled noises. However, the waveforms of A and B are not the same.  Assume the coupled TL is lossy (consider dispersion due to loss). Explain the possible reasons.</li>

 <li>Similarly the waveforms of the two backward coupled noises C and D are not the same. Explain the reason.</li>

</ul>