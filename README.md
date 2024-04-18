# Sample_Selection
*Abbreviations used:
q1 = quartile1,
q2 = quartile2,
q3 = quartile3
The medians and the quartiles were claculated each of the sample.

Sample 1: 
1. Astrometric_Selection:
A sample of 1897754 quasar candidates.They are indicated by the astrometric_selection_flag in the qso_candidates table.
The sample is split in the following way:
2. Sources with 5 parameter solutions
3. Sources with 6 parameter solutions
4. Host galaxy detected -  Flag indicating the presence of a detectable host galaxy.
5. No host galaxy detected
6. Sources identified as galaxy candidates - This flag indicates that this source has been identified and/or processed as a galaxy candidate by some of the DPAC processing chains.
7. Sources not identified as galaxy candidates
8. Sources outside the galactic plane - |sin(b)>0.1|
i. Source quality indicators:
a. sqrt_chi2_al_dof:
sqrt(astrometric_chi2_al/astrometric_n_good_obs_al − N)
(astrometric_chi2_al - goodness-of-fit (χ2) in the AL direction.
χ2 values were computed for the ‘good’ AL observations of the source, without taking into account the astrometric_excess_noise (if any) of the source. They do however take into account the attitude excess noise (if any) of each observation. 
astrometric_n_good_obs_al - Number of good observations in the along-scan (AL) direction (short),
astrometric_n_good_obs_al − N - The number of degrees of freedom for a source update,
N is the number of parameters solved, N=5 for 2-parameter and 5-parameter solutions and 6 for 6-parameter solutions.)
9. sqrt_chi2_al_dof < 1.2 - ruwe split for reasonably good solutions
10. sqrt_chi2_al_dof > 1.2 
11. sqrt_chi2_al_dof < 1.4 - ruwe split for reasonably good solutions
12. sqrt_chi2_al_dof > 1.4
13. sqrt_chi2_al_dof < median (splits based on median)
14. sqrt_chi2_al_dof > median
15. sqrt_chi2_al_dof <q1 (splits based on quartiles)
16. q1< sqrt_chi2_al_dof <q2
17. q2< sqrt_chi2_al_dof <q3
18. sqrt_chi2_al_dof >q3
b. astrometric_excess_noise:
Excess noise of the source 
This is the excess noise ϵi of the source. It measures the disagreement, expressed as an angle, between the observations of a source and the best-fitting standard astrometric model (using five astrometric parameters). The assumed observational noise in each observation is quadratically increased by ϵi in order to statistically match the residuals in the astrometric solution. A value of 0 signifies that the source is astrometrically well-behaved, i.e. that the residuals of the fit statistically agree with the assumed observational noise. A positive value signifies that the residuals are statistically larger than expected.
The significance of ϵi is given by astrometric_excess_noise_sig (D). If D≤2 then ϵi is probably not significant, and the source may be astrometrically well-behaved even if ϵi is large.
*Selections in astrometric excess noise for sources whose astrometric excess noise significance is greater than 2
All samples from 19-24 are selected with the condition astrometric_excess_noise_sig > 2 
19. astrometric_excess_noise < median
20. astrometric_excess_noise > median
21. astrometric_excess_noise <q1 (splits based on quartiles)
22. q1< astrometric_excess_noise <q2
23. q2< astrometric_excess_noise <q3
24. astrometric_excess_noise >q3
25. astrometric_excess_noise_sig < 2 (If D≤2 then ϵi is probably not significant)
c. astrometric_excess_noise_sig:
Significance of excess noise
A dimensionless measure (D) of the significance of the calculated astrometric_excess_noise (ϵi). 
A value D>2 indicates that the given ϵi is probably significant.
*Selections in astrometric excess noise significance for sources whose astrometric excess noise significance is greater than 2
26. astrometric_excess_noise_sig < median
27. astrometric_excess_noise_sig > median
28. astrometric_excess_noise_sig <q1
29. q1< astrometric_excess_noise_sig <q2
30. q2< astrometric_excess_noise_sig <q3
31. astrometric_excess_noise_sig >q3
d. ruwe:
The Renormalised Unit Weight Error
32. ruwe < 1.2 gives reasonably good solutions
33. ruwe > 1.2
34. ruwe < 1.4 gives reasonably good solutions
35. ruwe > 1.4
36. ruwe < median
37. ruwe > median
38. ruwe <q1
39. q1< ruwe <q2
40. q2< ruwe <q3
41. ruwe >q3
e. astrometric_gof_al:
Goodness-of-fit statistic of the astrometric solution for the source in the along-scan direction. This is the ‘gaussianized chi-square’, which for good fits should approximately follow a normal distribution with zero mean value and unit standard deviation. Values exceeding, say, +3 thus indicate a bad fit to the data.
42. astrometric_gof_al <3 - good fit
43. astrometric_gof_al >3 - bad fit
44. astrometric_gof_al < median
45. astrometric_gof_al > median
46. astrometric_gof_al <q1
47. q1< astrometric_gof_al <q2
48. q2< astrometric_gof_al <q3
49. astrometric_gof_al >q3
f. astrometric_sigma5d_max:
The longest semi-major axis of the 5-d error ellipsoid.
This is a 5-dimensional equivalent to the semi-major axis of the position error ellipse and is therefore useful for filtering out cases where one of the five parameters, or some linear combination of several parameters, is particularly ill-determined.
astrometric_sigma5d_max is given for all the solutions, as its size is one of the criteria for accepting or rejecting the 5 or 6-parameter solution.
50. astrometric_sigma5d_max < median
51. astrometric_sigma5d_max > median
52. astrometric_sigma5d_max <q1
53. q1< astrometric_sigma5d_max <q2
54. q2< astrometric_sigma5d_max <q3
55. astrometric_sigma5d_max >q3
g. ipd_gof_harmonic_amplitude:
This statistic measures the amplitude of the variation of the Image Parameter Determination (IPD) goodness–of–fit (GoF; reduced chi-square) as function of the position angle of the scan direction. A large amplitude indicates that the source has some non-isotropic spatial structure, for example a binary or galaxy, that is at least partially resolved by Gaia.
56. ipd_gof_harmonic_amplitude < median
57. ipd_gof_harmonic_amplitude > median
58. ipd_gof_harmonic_amplitude <q1
59. q1< ipd_gof_harmonic_amplitude <q2
60. q2< ipd_gof_harmonic_amplitude <q3
61. ipd_gof_harmonic_amplitude >q3
h. ipd_frac_multi_peak:
This field provides information on the raw windows used for the astrometric processing of this source coming from the Image Parameters Determination (IPD) module in the core processing. It provides the fraction of windows (having a successful IPD result), as percentage (from 0 to 100), for which the IPD algorithm has identified a double peak, meaning that the detection may be a visually resolved double star (either just visual double or real binary). The quantity was computed using all transits where the IPD was successful.
62. ipd_frac_multi_peak > median
63. ipd_frac_multi_peak < 10 (splits based on bins - begin)
64-68. splits based on bins (bin width = 10)
69. ipd_frac_multi_peak >60 (splits based on bins - end)
i. phot_bp_rp_excess_factor:
BP/RP excess factor estimated from the comparison of the sum of integrated BP and RP fluxes with respect to the flux in the G band. This measures the excess of flux in the BP and RP integrated photometry with respect to the G band. A deviation from the norm means that there is a consistency issue between the fluxes. This could generally imply a problem with the G, BP or RP measurements.
70. phot_bp_rp_excess_factor < median
71. phot_bp_rp_excess_factor > median
72. phot_bp_rp_excess_factor <q1
73. q1< phot_bp_rp_excess_factor <q2
74. q2< phot_bp_rp_excess_factor <q3
75. phot_bp_rp_excess_factor >q3
* Other source parameters
j. phot_g_mean_mag:
Mean magnitude in the G band. This is computed from the G-band mean flux (phot_g_mean_flux ) applying the magnitude zero-point in the Vega scale. No error is provided for this quantity as the error distribution is only symmetric in flux space.
This converts to an asymmetric error distribution in magnitude space which cannot be represented by a single error value. 
76. phot_g_mean_mag < median
77. phot_g_mean_mag > median
78. phot_g_mean_mag <q1
79. q1< phot_g_mean_mag <q2
80. q2< phot_g_mean_mag <q3
81. phot_g_mean_mag >q3
* splits based on bins
82. phot_g_mean_mag < 15
83-88. splits based on bins (bin width = 1)
89. phot_g_mean_mag > 21
k. bp_rp:
BP−RP colour (phot_bp_mean_mag – phot_rp_mean_mag) 
90. bp_rp < median
91. bp_rp > median
92. bp_rp <q1
93. q1< bp_rp <q2
94. q2< bp_rp <q3
95. bp_rp >q3
* splits based on bins
96. bp_rp <-1
97-100. splits based on bins (bin width = 1)
101. bp_rp >3
102. bp_rp <1 (random split based on the histogram)
103. bp_rp >1
l. b:
Galactic Latitude of the object at reference epoch ref_epoch.
104. b < median
105. b > median
106. b <q1
107. q1< b <q2
108. q2< b <q3
109. b >q3
* splits based on bins
110. b <-70
111-124. splits based on bins (bin width = 10)
125. b >70
126. b <0 (random split based on histogram)
127. b >0
m. l:
Galactic Longitude of the object at reference epoch ref_epoch.
128. l < median
129. l > median
130. l <q1
131. q1< l <q2
132. q2< l <q3
133. l >q3
* splits based on bins 
134-144. bin width = 30
145. l >330
n. ecl_lat:
Ecliptic Latitude of the object at reference epoch ref_epoch.
146. ecl_lat < median
147. ecl_lat > median
148. ecl_lat <q1
149. q1< ecl_lat <q2
150. q2< ecl_lat <q3
151. ecl_lat >q3
* splits based on bins
152. ecl_lat <-70
153-166. bin width = 10
167. ecl_lat >70
168. ecl_lat <0 (random split based on the histogram)
169. ecl_lat >0
o. ecl_lon:
Ecliptic Longitude of the object at reference epoch ref_epoch.
170. ecl_lon < median
171. ecl_lon > median
172. ecl_lon <q1
173. q1< ecl_lon <q2
174. q2< ecl_lon <q3
175. ecl_lon >q3
* splits based on bins
176-186. bin width = 30
187. ecl_lon >330
p. ipd_frac_odd_win:
Percent of transits with truncated windows or multiple gate. This field is calculated during AGIS and provides information on the raw windows used for the astrometric processing of this source. It provides the fraction (as a percentage, from 0 to 100) of transits having either truncation or multiple gates flagged in one or more windows. Such a situation invariably means that the on-board video processing unit (VPU) detected some nearby source (which may be just a spurious detection, but typically could be some real nearby source — having another distinct transit and most probably assigned to a different source). So in general a non–zero fraction indicates that this source may be contaminated by another nearby source. The quantity was computed using all transits where the IPD was successful. 
188. ipd_frac_odd_win >median
* splits based on bins
189-197. bin width = 10
198. ipd_frac_odd_win >90
q. visibility_periods_used:
Number of visibility periods used in the astrometric solution.
A visibility period is a group of observations separated from other groups by a gap of at least 4 days. A source may have from one to tens of field–of–view transits in a visibility period, but with a small spread in time, direction of scanning, and parallax factor. From one visibility period to the next these variables have usually changed significantly. A high number of visibility periods is therefore a better indicator of an astrometrically well–observed source than a large number of field–of–view transits (matched_transits or astrometric_matched_transits) or CCD observations (astrometric_n_obs_al). A small value (e.g. less than 10) indicates that the calculated parallax could be more vulnerable to errors, e.g. from the calibration model, not reflected in the formal uncertainties.
199. visibility_periods_used <median
200. visibility_periods_used >median
201. visibility_periods_used <q1
202. q1< visibility_periods_used <q2
203. q2< visibility_periods_used <q3
204. visibility_periods_used >q3
205. visibility_periods_used <20 (random split)
206. visibility_periods_used >20
r. nu_eff_used_in_astrometry:
Effective wavenumber of the source used in the astrometric solution. This νeff is the value used in the image parameter determination and in the astrometric calibration if reliable mean BP and RP photometry were available. It is the photon-flux weighted inverse wavelength, as estimated from the BP and RP bands. The field is provided for astrometric solutions with five parameters but is empty for those with two or six parameters.
Due to cyclic processing of the astrometry and the photometry, this effective wavenumber might be different from the one computed using the latest available photometry. Moreover, if no reliable photometry was available at the time of the astrometric processing, this field is empty and an astrometrically estimated value of the effective wavenumber may instead be given in the pseudocolour field. 207. nu_eff_used_in_astrometry < median
208. nu_eff_used_in_astrometry > median
209. nu_eff_used_in_astrometry <q1
210. q1< nu_eff_used_in_astrometry <q2
211. q2< nu_eff_used_in_astrometry <q3
212. nu_eff_used_in_astrometry >q3
s. pseudocolour:
Astrometrically estimated pseudocolour of the source. 
Effective wavenumber of the source estimated in the final astrometric processing. The pseudocolour is the astrometrically estimated effective wavenumber of the photon flux distribution in the astrometric (G) band, measured in μm−1. The value in this field was estimated from the chromatic displacements of image centroids, calibrated by means of the photometrically determined effective wavenumbers (νeff) of primary sources.The field is empty when chromaticity was instead taken into account using the photometrically determined νeff given in the field nu_eff_used_in_astrometry.   
213. pseudocolour < median
214. pseudocolour > median
215. pseudocolour <q1
216. q1< pseudocolour <q2
217. q2< pseudocolour <q3
218. pseudocolour >q3
  
     
  
   
  
 
 
 



 

 

 

 





