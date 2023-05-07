Download Link: https://assignmentchef.com/product/solved-eel3135-lab-6
<br>
<h2>Calculating DTFT in MATLAB</h2>

It is not hard to see that you may use the function freq resp you wrote in Lab 5 to calculate the DTFT of any finite-length signal (why?). Hereafter in this lab, rename the function as below:

X = dtft(x,w)

where x is the input signal vector, w is a (normalized radian) frequency vector, and X is the DTFT vector of x calculated at the frequencies specified in w. For an infinite-length signal, we have to truncate it in order to use the function dtft to approximately calculate the DTFT of the signal.

Note that the method used in dtft is a computationally inefficient way to calculate the DTFT of a signal, as you will see in the latter parts of the lab. We will talk about how to do DTFT calculations in a much more computationally efficient way later in the semester.

<h2>Table of Discrete-Time Fourier Transform Pairs</h2>

∞

Discrete-Time Fourier Transform     :           <em>X</em>(<em>e<sup>jω</sup></em><sub>b</sub>) = <sup>X </sup><em>x</em>[<em>n</em>]<em>e</em><sup>−<em>jωn</em></sup><sub>b</sub>

Inverse Discrete-Time Fourier Transform       :

Dirac delta function that repeat every 2<em>π      </em>:       <em>δ</em><sub>2<em>π</em></sub>(<em>ω</em><sub>b</sub>) = <sup>X </sup><em>δ</em>(<em>ω</em><sub>b </sub>− 2<em>πk</em>)

<em>k</em>=−∞

<table width="505">

 <tbody>

  <tr>

   <td width="195"><em>x</em>[<em>n</em>]</td>

   <td width="244"><em>X</em>(<em>e</em><em>jω</em>b)</td>

   <td width="67">condition</td>

  </tr>

  <tr>

   <td width="195"><em>δ</em>[<em>n</em>]</td>

   <td width="244">1</td>

   <td width="67"> </td>

  </tr>

  <tr>

   <td width="195"><em>δ</em>[<em>n </em>− <em>n</em><sub>0</sub>] <em>x</em>[<em>n</em>] = 1</td>

   <td width="244">2</td>

   <td width="67"> </td>

  </tr>

  <tr>

   <td width="195"><em>u</em>[<em>n</em>]<em>e</em><em>jω</em>b0<em>n</em>cos(<em>ω</em><sub>0</sub><em>n</em>) b</td>

   <td width="244">) is periodic with period 2<em>π</em></td>

   <td width="67"> </td>

  </tr>

 </tbody>

</table>

<h2>Table of Discrete-Time Fourier Transform Properties</h2>

For each property, assume

)       and

<table width="627">

 <tbody>

  <tr>

   <td width="283">Property</td>

   <td width="109">Time domain</td>

   <td width="234">DTFT domain</td>

  </tr>

  <tr>

   <td width="283">Linearity</td>

   <td width="109"><em>Ax</em>[<em>n</em>] + <em>By</em>[<em>n</em>]</td>

   <td width="234"><em>AX</em>(<em>e</em><em>jω</em>b) + <em>BY </em>(<em>e</em><em>jω</em>b)</td>

  </tr>

  <tr>

   <td width="283">Time Shifting</td>

   <td width="109"><em>x</em>[<em>n </em>− <em>n</em><sub>0</sub>]</td>

   <td width="234"></td>

  </tr>

  <tr>

   <td width="283">Frequency Shifting</td>

   <td width="109"></td>

   <td width="234"><em>X</em>(<em>ω </em>− <em>ω</em><sub>0</sub>) b b</td>

  </tr>

  <tr>

   <td width="283">Conjugation</td>

   <td width="109"><em>x</em><sup>∗</sup>[<em>n</em>]</td>

   <td width="234"><em>X</em>∗(<em>e</em>−<em>jω</em>b)</td>

  </tr>

  <tr>

   <td width="283">Time Reversal</td>

   <td width="109"><em>x</em>[−<em>n</em>]</td>

   <td width="234"><em>X</em>(<em>e</em>−<em>jω</em>b)</td>

  </tr>

  <tr>

   <td width="283">ConvolutionMultiplicationDifferencing in TimeAccumulationFrequency DifferentiationParseval’s Relation for Aperiodic Signals</td>

   <td width="109"><em>nx</em>[<em>n</em>]</td>

   <td width="234"></td>

  </tr>

 </tbody>

</table>

<h1>Lab 6 Exercises</h1>

<ul>

 <li>Unless stated otherwise, you must submit your solutions to all the lab exercises in this section.</li>

 <li>Your laboratory solutions should be submitted on Canvas as a single PDF. The simplest way is to put your codes and answers for all the lab exercises in a single MATLAB Publisher script and use %% to separate the codes and answers for different exercises into different sections as described in the information section of Lab 1.</li>

 <li><strong>Plot all magnitude spectrums in this lab in dB scale.</strong></li>

</ul>

<strong>Exercise 6.1:</strong>

This exercise shows you how to carefully interprete the results obtained from your MATLAB function dtft, particularly for the cases of infinite-length signals.

Use the tables in the information section, or otherwise, to analytically determine the expressions of the DTFTs for the signals below. Use your MATLAB function dtft to calculate and plot (magnitude and angle) the DTFTs. For each signal, truncate its length to 10, if needed, when using your function dtft to calculate the DTFT. Compare your plot with the DTFT expression you obtain analytically. Do they match? Repeat the same MATLAB calculation of the DTFT and comparison with the analytic expression by truncating each signal to length 100 instead. Explain the effects of increasing the truncation length.

<ul>

 <li><em>x</em>[<em>n</em>] = <em>δ</em>[<em>n </em>− 3]</li>

 <li><em>x</em>[<em>n</em>] = (8<em>/</em>9)<em><sup>n</sup>u</em>[<em>n</em>]</li>

 <li><em>x</em>[<em>n</em>] = (−8<em>/</em>9)<em><sup>n</sup>u</em>[<em>n</em>]</li>

 <li><em>x</em>[<em>n</em>] = <em>u</em>[<em>n</em>] − <em>u</em>[<em>n </em>− 5]</li>

 <li><em>x</em>[<em>n</em>] = cos((<em>π/</em>4)<em>n</em>)</li>

</ul>

<h2>Exercise 6.2: <em>(Nulling Filter)</em></h2>

This exercise shows you how to employ DTFT to analyze an audio signal corrupted by a sinusoidal interfering signal. Specifically, you will examine the DTFT to determine the frequency of the sinusoidal interference and then use a nulling filter to remove the interference. The corrupted audio signal is provided in the WAV file corrupted wannabe.wav.

<ul>

 <li>Load corrupted wannabe.wav into MATLAB. Use your function dtft to calculate the DTFT of the audio signal. Plot the magnitude of the DTFT. <u>Hint: </u>You should use a frequency vector that has at least 2000 points to calculate the DTFT so as to properly identify the interference frequency in part (b) below. It may take a minute or so to compute the DTFT.</li>

 <li>Identify the frequency of the sinusoidal interference. Give this frequency in normalized radian frequency as well as continuous-time cyclic frequency. <u>Hint: </u>You may use “Tools→Data Tips” to identify the value of interference frequency from the DTFT magnitude plot. You may also use the MATLAB function find (see Lab 5) to more accurate determine the frequency of interest.</li>

 <li>Consider the following nulling FIR filter:</li>

</ul>

<em>y</em>[<em>n</em>] = <em>x</em>[<em>n</em>] − 2cos(<em>w</em>b<sub>0</sub>)<em>x</em>[<em>n </em>− 1] + <em>x</em>[<em>n </em>− 2]<em>,                                                     </em>(1)

This filter can remove a sinusoid at the normalized radian frequency specified by <em>w</em>b<sub>0</sub>. Design this filter to remove the interference that you identified in (b), i.e. specify the impulse response of the resulting filter in the vector h. Use your function dtft to calculate and plot the magnitude response and phase response of the filter.

<ul>

 <li>Apply the nulling filter to the corrupted audio signal. Listen to the filtered audio and save it to the WAV file filtered wannabe.wav. Submit the WAV file. Use your dtft function to calculate and plot the magnitude of the DTFT of the filtered audio signal. Describe the differences between the DTFTs of the original audio and the output of the nulling filter, particularly with respect to the interference signal.</li>

</ul>

<strong>Exercise 6.3 (Extra credits: +20 points):</strong>

This exercise is similar to Exercise 6.2. An audio signal (not the same as the one in Exercise 6.2) is corrupted by a very strong artificial noise (not a simple sinusoidal interference). You again need to use your dtft function to study the frequency contents of the corrupted audio signal, identify the frequency range of the noise components, and design a filter to remove the noise. The theory behind how to design a filter that can remove the noise here is a bit too advance for us. Instead of going through the theory, this exercise shows you how to use a MATLAB filter design GUI to work out the required filter.

Load in the noisy audio signal from the WAV file what did he say.wav. Use your dtft function to calculate and plot the magnitude of the signal’s DTFT. Identify the frequency range of the noise. Express your answer in both normalized radian frequency and continuous-time cyclic frequency. To remove the noise in this case, you will need to employ a filter different than the nulling filter in Exercise 6.2. State what kind of filter (lowpass, highpass, bandpass) is needed to remove the noise. Determine the start and end frequencies of the passband and stopband of the filter.

MATLAB has a GUI filterDesigner that helps you design a filter. Type filterDesigner in the command window to invoke the GUI. You may select the type of the filter that you want to design. Based on your answer above, choose whether you want to design a lowpass, highpass, or bandpass filter. Choose <strong>FIR Equiripple</strong>. Choose the <strong>Filter Order </strong>to be <strong>Minimum order</strong>. Specify the sampling frequency, start and end frequencies of the passband and stopband. You will also need to specify the ripple tolerance in the passband (<strong>Apass</strong>) and the magnitude attenuation from the passband to stopband (<strong>Astop</strong>). It suffices to choose <strong>Apass </strong>= 1 dB. You will need to choose a suitable value for <strong>Astop</strong>. For example, <strong>Astop </strong>= 60 dB means that the value of the magnitude response in the stopband is 60 dB below that in the passband. After specifying all the parameters, click the <strong>Design Filter </strong>button to generate the filter impulse response. You can save the generated impulse response to your workspace by choosing “File→Export”, and then specifying <strong>Export to Workspace</strong>, <strong>Export as Coefficients</strong>, and setting Numerator to your choice of a variable name to hold the impulse response. Click the <strong>Export </strong>button to export the impulse response to your workspace.

Use the GUI to design a filter that can remove the noise. <strong>Report all the parameters that you specify in the GUI. </strong>Export the impulse response of the filter to your MATLAB workspace. Apply this filter to the noisy audio signal. Listen to the filtered signal and save the filtered audio to the WAV file filtered what.wav. Submit the WAV file. <strong>Write down the sentence dictated in the audio file. </strong>Use your dtft function to calculate and plot the magnitude of the DTFT of the filtered audio signal. Describe the differences between the DTFTs of the original audio and the output of the noise removal filter, highlighting what and how much noise components are removed by the filter.

Note that you may need to iterate the above filter design process a few times to generate a relatively clean and audible audio signal.