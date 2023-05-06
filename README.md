Download Link: https://assignmentchef.com/product/solved-economics7103-hw4
<br>
You have imaginary data on the monthly yields for Pacific fish trawling companies (<em>fishbycatch.csv</em>). An environmental nonprofit targeted these firms and implemented a program designed to reduce bycatch. As part of the program, the nonprofit contacted firm managers and provided information about best practices to reduce bycatch. The program was implemented in two phases. In January 2018, the nonprofit contacted half of the firms. The next year in January 2019, the nonprofit contacted the remaining firms.

You are interested in whether the program worked or not and decide to use this panel data to empirically estimate the effect of the program. You realize that you have a treatment and control group in pre- and post-treatment periods due to the program’s rollout, so you think a difference-in-differences design is a good approach. You have the following data:

<table width="422">

 <tbody>

  <tr>

   <td width="67">Variable</td>

   <td width="355">Description</td>

  </tr>

  <tr>

   <td width="67"><em>firm</em></td>

   <td width="355">Firm identification number</td>

  </tr>

  <tr>

   <td width="67"><em>shrimp*</em></td>

   <td width="355">Pounds of shrimp in month *</td>

  </tr>

  <tr>

   <td width="67"><em>salmon*</em></td>

   <td width="355">Pounds of salmon in month *</td>

  </tr>

  <tr>

   <td width="67"><em>bycatch*</em></td>

   <td width="355">Pounds of bycatch in month *</td>

  </tr>

  <tr>

   <td width="67"><em>firmsize</em></td>

   <td width="355">Size of fishing fleet</td>

  </tr>

  <tr>

   <td width="67"><em>treated</em></td>

   <td width="355">=1 if firm received information treatment in January 2018</td>

  </tr>

 </tbody>

</table>

Table 1: Variable descriptions for homework 3.

Note that to convert these panel data from wide form to long form, you can use the Pandas wide_to_long() function.

<ol>

 <li>Visually inspect the bycatch by month before and after treatment for treated and control groups bycreating a line plot for months in 2017 and 2018. Does it appear that there are parallel trends before treatment? (Hint: I found the Pandas function groupby() )</li>

 <li>Estimate the treatment effect of the program on bycatch using the sample analog of the populationdifference-in-differences for treatment and control groups in December 2017 and January 2018. The population difference-in-differences is:</li>

</ol>

<em>DID </em>={<em>E</em>[<em>Y<sub>igt</sub></em>|<em>g</em>(<em>i</em>) = <em>treat,t </em>= <em>Post</em>] − <em>E</em>[<em>Y<sub>igt</sub></em>|<em>g</em>(<em>i</em>) = <em>treat,t </em>= <em>Pre</em>]}                                              (1)

− {<em>E</em>[<em>Y<sub>igt</sub></em>|<em>g</em>(<em>i</em>) = <em>control,t </em>= <em>Post</em>] − <em>E</em>[<em>Y<sub>igt</sub></em>|<em>g</em>(<em>i</em>) = <em>control,t </em>= <em>Pre</em>]}<em>.                              </em>(2)

Simply report the estimate without a standard error. What is the intuition of the estimator?

<ol start="3">

 <li>Estimate the treatment effect of the program on bycatch using a regression-based two-period differencein-differences estimator with estimating equation:</li>

</ol>

<em>bycatch<sub>i,t </sub></em>= <em>α </em>+ <em>λ<sub>t</sub></em><sub>=2017 </sub>+ <em>γg</em>(<em>i</em>) + <em>δtreat<sub>i,t </sub></em>+ <em>ε<sub>i,t</sub>,                                                       </em>(3)

where <em>λ<sub>t</sub></em><sub>=2017 </sub>is a separate intercept for the pre-period (December 2017), <em>g</em>(<em>i</em>) is an indicator that firm <em>i </em>is in the treatment group, and <em>treat<sub>i,t </sub></em>is an indicator variable equal to one when a firm is treated. Your estimating sample should include the observations in December 2017 and January 2018 only. Report the results in a table with standard errors or confidence intervals calculated using clustered standard errors at the firm level. How does this result compare to your previous calculation?

1