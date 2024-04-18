# Sample_Selection
Abbreviations used:
q1 = quartile1
q2 = quartile2
q3 = quartile3

Sample 1: 
1. Astrometric_Selection
A sample of 1897754 quasar candidates.They are indicated by the astrometric_selection_flag in the qso_candidates table.
The sample is split in the following way:
2. Sources with 5 parameter solutions
3. Sources with 6 parameter solutions
4. Host galaxy detected -  Flag indicating the presence of a detectable host galaxy.
5. No host galaxy detected
6. Sources identified as galaxy candidates - This flag indicates that this source has been identified and/or processed as a galaxy candidate by some of the DPAC processing chains.
7. Sources not identified as galaxy candidates
8. Sources outside the galactic plane - |sin(b)>0.1|
# Source quality indicators
a. sqrt_chi2_al_dof ----> sqrt(astrometric_chi2_al/astrometric_n_good_obs_al − N)
(astrometric_chi2_al - goodness-of-fit (χ2) in the AL direction.
χ2 values were computed for the ‘good’ AL observations of the source, without taking into account the astrometric_excess_noise (if any) of the source. They do however take into account the attitude excess noise (if any) of each observation. 
astrometric_n_good_obs_al - Number of good observations in the along-scan (AL) direction (short),
astrometric_n_good_obs_al − N - The number of degrees of freedom for a source update,
N is the number of parameters solved, N=5 for 2-parameter and 5-parameter solutions and 6 for 6-parameter solutions.)
9. < 1.2 - ruwe split for reasonably good solutions
10. > 1.2 
11. < 1.4 - ruwe split for reasonably good solutions
12. > 1.4
13. < median (splits based on median)
14. > median
15. sqrt_chi2_al_dof <q1 (splits based on quartiles)
16. q1< sqrt_chi2_al_dof <q2
17. q2< sqrt_chi2_al_dof <q3
18. sqrt_chi2_al_dof >q3
b. astrometric_excess_noise : Excess noise of the source 
This is the excess noise ϵi of the source. It measures the disagreement, expressed as an angle, between the observations of a source and the best-fitting standard astrometric model (using five astrometric parameters). The assumed observational noise in each observation is quadratically increased by ϵi in order to statistically match the residuals in the astrometric solution. A value of 0 signifies that the source is astrometrically well-behaved, i.e. that the residuals of the fit statistically agree with the assumed observational noise. A positive value signifies that the residuals are statistically larger than expected.
The significance of ϵi is given by astrometric_excess_noise_sig (D). If D≤2 then ϵi is probably not significant, and the source may be astrometrically well-behaved even if ϵi is large.
i. Selections in astrometric excess noise for sources whose astrometric excess noise significance is greater than 2
All samples from 19-24 are selected with the condition astrometric_excess_noise_sig > 2 
19. < median
20. > median
21. astrometric_excess_noise <q1 (splits based on quartiles)
22. q1< astrometric_excess_noise <q2
23. q2< astrometric_excess_noise <q3
24. astrometric_excess_noise >q3
25. astrometric_excess_noise_sig < 2 (If D≤2 then ϵi is probably not significant)
c. astrometric_excess_noise_sig
Significance of excess noise
A dimensionless measure (D) of the significance of the calculated astrometric_excess_noise (ϵi). 
A value D>2 indicates that the given ϵi is probably significant.
ii. Selections in astrometric excess noise significance for sources whose astrometric excess noise significance is greater than 2
26. < median
27. > median
28. astrometric_excess_noise_sig <q1
29. q1< astrometric_excess_noise_sig <q2
30. q2< astrometric_excess_noise_sig <q3
31. astrometric_excess_noise_sig >q3
d. ruwe
The Renormalised Unit Weight Error
32. ruwe < 1.2 gives reasonably good solutions
33. ruwe > 1.2
34. ruwe < 1.4 gives reasonably good solutions
35. ruwe > 1.4
36. < median
37. > median
38. ruwe <q1
39. q1< ruwe <q2
40. q2< ruwe <q3
41. ruwe >q3
e. astrometric_gof_al
Goodness-of-fit statistic of the astrometric solution for the source in the along-scan direction. This is the ‘gaussianized chi-square’, which for good fits should approximately follow a normal distribution with zero mean value and unit standard deviation. Values exceeding, say, +3 thus indicate a bad fit to the data.
42. astrometric_gof_al <3 - good fit
43. astrometric_gof_al >3 - bad fit
44. < median
45. > median
46. astrometric_gof_al <q1
47. q1< astrometric_gof_al <q2
48. q2< astrometric_gof_al <q3
49. astrometric_gof_al >q3
f. astrometric_sigma5d_max
The longest semi-major axis of the 5-d error ellipsoid.
This is a 5-dimensional equivalent to the semi-major axis of the position error ellipse and is therefore useful for filtering out cases where one of the five parameters, or some linear combination of several parameters, is particularly ill-determined.
astrometric_sigma5d_max is given for all the solutions, as its size is one of the criteria for accepting or rejecting the 5 or 6-parameter solution.
50. < median
51. > median
52. astrometric_sigma5d_max <q1
53. q1< astrometric_sigma5d_max <q2
54. q2< astrometric_sigma5d_max <q3
55. astrometric_sigma5d_max >q3
g. ipd_gof_harmonic_amplitude
This statistic measures the amplitude of the variation of the Image Parameter Determination (IPD) goodness–of–fit (GoF; reduced chi-square) as function of the position angle of the scan direction. A large amplitude indicates that the source has some non-isotropic spatial structure, for example a binary or galaxy, that is at least partially resolved by Gaia.
56. < median
57. > median
58. ipd_gof_harmonic_amplitude <q1
59. q1< ipd_gof_harmonic_amplitude <q2
60. q2< ipd_gof_harmonic_amplitude <q3
61. ipd_gof_harmonic_amplitude >q3
h. ipd_frac_multi_peak
This field provides information on the raw windows used for the astrometric processing of this source coming from the Image Parameters Determination (IPD) module in the core processing. It provides the fraction of windows (having a successful IPD result), as percentage (from 0 to 100), for which the IPD algorithm has identified a double peak, meaning that the detection may be a visually resolved double star (either just visual double or real binary). The quantity was computed using all transits where the IPD was successful.
62. > median
63. ipd_frac_multi_peak < 10 (splits based on bins - begin)
64-68. splits based on bins (bin width = 10)
69. ipd_frac_multi_peak >60 (splits based on bins - end)
i. phot_bp_rp_excess_factor
BP/RP excess factor estimated from the comparison of the sum of integrated BP and RP fluxes with respect to the flux in the G band. This measures the excess of flux in the BP and RP integrated photometry with respect to the G band. A deviation from the norm means that there is a consistency issue between the fluxes. This could generally imply a problem with the G, BP or RP measurements. 

 

 





