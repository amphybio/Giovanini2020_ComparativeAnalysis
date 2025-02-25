
**ComparativeAnalysis_ProbabilitesAndMoments**
<html>
<head>
<meta http-equiv="content-type" content="text/html; charset=utf-8">
<!-- Created by Maple 18.00, Linux -->
</head>
<body bgcolor="FFFFFF">
<p align="left"><font color="#000000" size="3" face="Times New Roman">This document contains the codes used to obtain the results of our study. It is divided in two sections: "procedures" and "results". Both sections is organized in two subsections, respectively, an Externally Regulating Gene (ERG) and a Self-Repressing Gene (SRG) models. In "procedures" we find the codes that compute the points for the graphs, and in "results" is shown, properly, the graphs of our work. </font>&nbsp;</p>
<dl style="margin-left:40px"><a name="MapleAutoBookmark2" />
<p align="left"><font color="#000000" size="5" face="Serif"><strong>Procedures</strong></font>&nbsp;</p>
<dl style="margin-left:40px"><a name="MapleAutoBookmark3" />
<p align="left"><font color="#000000" size="4" face="Serif"><strong>ERG</strong></font>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">The KummerM function parameters are written as functions of the kinetic parameters of the stochastic model for an ERG:</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_1.gif" width="193" height="30" alt="a = `/`(`*`(f), `*`(rho)), b = `/`(`*`(`+`(f, h2)), `*`(rho)), N = `/`(`*`(k), `*`(rho)); 1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_2.gif" width="161" height="32" alt="a = `/`(`*`(f), `*`(rho)), b = `/`(`*`(`+`(f, h2)), `*`(rho)), N = `/`(`*`(k), `*`(rho))" align="center" border="0"></td>
<td width='5%' align='center'>(1.1.1)</td>
</tr>
</table></font>&nbsp;</p>
<dl style="margin-left:40px"><a name="MapleAutoBookmark4" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Probabilities</em></strong></font>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">Here we define the formulas for computing the probabilities phi_n, alpha_n, beta_n as function of the KummerM function parameters: a, b, N.</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_3.gif" width="419" height="30" alt="PhinE := `/`(`*`(pochhammer(a, n), `*`(`^`(N, n), `*`(KummerM(`+`(a, n), `+`(b, n), `+`(`-`(N)))))), `*`(pochhammer(b, n), `*`(factorial(n)))); -1; AlphanE := `/`(`*`(a, `*`(pochhammer(`+`(a, 1), n), ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_4.gif" width="521" height="30" alt="PhinE := `/`(`*`(pochhammer(a, n), `*`(`^`(N, n), `*`(KummerM(`+`(a, n), `+`(b, n), `+`(`-`(N)))))), `*`(pochhammer(b, n), `*`(factorial(n)))); -1; AlphanE := `/`(`*`(a, `*`(pochhammer(`+`(a, 1), n), ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_5.gif" width="12" height="14" alt="PhinE := `/`(`*`(pochhammer(a, n), `*`(`^`(N, n), `*`(KummerM(`+`(a, n), `+`(b, n), `+`(`-`(N)))))), `*`(pochhammer(b, n), `*`(factorial(n)))); -1; AlphanE := `/`(`*`(a, `*`(pochhammer(`+`(a, 1), n), ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_6.gif" width="529" height="30" alt="PhinE := `/`(`*`(pochhammer(a, n), `*`(`^`(N, n), `*`(KummerM(`+`(a, n), `+`(b, n), `+`(`-`(N)))))), `*`(pochhammer(b, n), `*`(factorial(n)))); -1; AlphanE := `/`(`*`(a, `*`(pochhammer(`+`(a, 1), n), ..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">We compute the probabilities phi_n, alpha_n, beta_n for given values of the KummerM function parameters.
<br>The parameter K gives the maximal value for n and is choosen to ensure that phi0+phi1+...+phiK~1</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_7.gif" width="221" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_8.gif" width="286" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_9.gif" width="8" height="13" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_10.gif" width="648" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_11.gif" width="648" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_12.gif" width="12" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_13.gif" width="92" height="30" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_14.gif" width="12" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_15.gif" width="138" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_16.gif" width="188" height="30" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_17.gif" width="216" height="32" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_18.gif" width="86" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_19.gif" width="77" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_20.gif" width="105" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_21.gif" width="12" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_22.gif" width="12" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_23.gif" width="388" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_24.gif" width="134" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_25.gif" width="532" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_26.gif" width="608" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_27.gif" width="387" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_28.gif" width="399" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_29.gif" width="545" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_30.gif" width="589" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_31.gif" width="84" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_32.gif" width="533" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_33.gif" width="321" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_34.gif" width="84" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_35.gif" width="50" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_36.gif" width="8" height="13" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_37.gif" width="82" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_38.gif" width="68" height="14" alt="PrE := proc (N1, A, B, rho, K, report) local j, pnts, palpha, nmean, fano, cov, k, f, h2; pnts := [seq([j, evalf(subs(n = j, subs(a = A, b = B, N = N1, AlphanE))), evalf(subs(n = j, subs(a = A, b = B,..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">Following, we have an example for test the probabilities procedure:</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_39.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_40.gif" width="571" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 150; -1; Report := false; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_41.gif" width="101" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 150; -1; Report := false; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_42.gif" width="124" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 150; -1; Report := false; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_43.gif" width="448" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 150; -1; Report := false; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_44.gif" width="29" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 150; -1; Report := false; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_45.gif" width="135" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 150; -1; Report := false; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_46.gif" width="330" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 150; -1; Report := false; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_47.gif" width="29" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 150; -1; Report := false; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], ..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_48.gif" width="315" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. 0.6e-1]); 1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_49.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark5" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Pearson correlation</em></strong></font>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">In a ERG, the Pearson correlation between number of proteins n and auxiliar random variable of state gene promoter for given values of the KummerM function parameters is computed by:</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_50.gif" width="268" height="30" alt="R := `/`(`*`(sqrt(`/`(`*`(N, `*`(`+`(1, `-`(p)))), `*`(`+`(1, b, `*`(N, `*`(`+`(1, `-`(p))))))))), `*`(sqrt(`+`(b, 1)))); -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_51.gif" width="173" height="14" alt="CorrE := proc (N1, B, npnts) local step, palpha, pnts; step := evalf(`/`(1, `*`(npnts))); palpha := [seq(`*`(step, `*`(i)), i = 1 .. npnts)]; pnts := [seq([palpha[i], evalf(subs(N = 50, b = B, p = pal..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_52.gif" width="152" height="14" alt="CorrE := proc (N1, B, npnts) local step, palpha, pnts; step := evalf(`/`(1, `*`(npnts))); palpha := [seq(`*`(step, `*`(i)), i = 1 .. npnts)]; pnts := [seq([palpha[i], evalf(subs(N = 50, b = B, p = pal..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_53.gif" width="143" height="30" alt="CorrE := proc (N1, B, npnts) local step, palpha, pnts; step := evalf(`/`(1, `*`(npnts))); palpha := [seq(`*`(step, `*`(i)), i = 1 .. npnts)]; pnts := [seq([palpha[i], evalf(subs(N = 50, b = B, p = pal..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_54.gif" width="221" height="14" alt="CorrE := proc (N1, B, npnts) local step, palpha, pnts; step := evalf(`/`(1, `*`(npnts))); palpha := [seq(`*`(step, `*`(i)), i = 1 .. npnts)]; pnts := [seq([palpha[i], evalf(subs(N = 50, b = B, p = pal..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_55.gif" width="558" height="14" alt="CorrE := proc (N1, B, npnts) local step, palpha, pnts; step := evalf(`/`(1, `*`(npnts))); palpha := [seq(`*`(step, `*`(i)), i = 1 .. npnts)]; pnts := [seq([palpha[i], evalf(subs(N = 50, b = B, p = pal..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_56.gif" width="85" height="14" alt="CorrE := proc (N1, B, npnts) local step, palpha, pnts; step := evalf(`/`(1, `*`(npnts))); palpha := [seq(`*`(step, `*`(i)), i = 1 .. npnts)]; pnts := [seq([palpha[i], evalf(subs(N = 50, b = B, p = pal..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_57.gif" width="68" height="14" alt="CorrE := proc (N1, B, npnts) local step, palpha, pnts; step := evalf(`/`(1, `*`(npnts))); palpha := [seq(`*`(step, `*`(i)), i = 1 .. npnts)]; pnts := [seq([palpha[i], evalf(subs(N = 50, b = B, p = pal..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">In this example below, we can test the correlation procedure:</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_58.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_59.gif" width="264" height="14" alt="Nf2a := 50; -1; Bf2a := .1; -1; npntsf2a := 1000; -1; corrf2a := []; -1; corrf2a := [op(corrf2a), CorrE(Nf2a, Bf2a, npntsf2a)]; -1" align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_60.gif" width="97" height="14" alt="Nf2a := 50; -1; Bf2a := .1; -1; npntsf2a := 1000; -1; corrf2a := []; -1; corrf2a := [op(corrf2a), CorrE(Nf2a, Bf2a, npntsf2a)]; -1" align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_61.gif" width="336" height="14" alt="Nf2a := 50; -1; Bf2a := .1; -1; npntsf2a := 1000; -1; corrf2a := []; -1; corrf2a := [op(corrf2a), CorrE(Nf2a, Bf2a, npntsf2a)]; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_62.gif" width="203" height="14" alt="plot(corrf2a, view = [0 .. 1, 0 .. 1]); 1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_63.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark6" />
<p align="left"><font color="#000000" size="4" face="Serif"><strong>SRG</strong></font>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">For an SRG, the KummerM function parameters are written as functions of the kinetic parameters of the stochastic model as follows:</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_64.gif" width="393" height="32" alt="a = `/`(`*`(f), `*`(rho)), b = `+`(`/`(`*`(f), `*`(`+`(rho, h1))), `/`(`*`(N, `*`(rho, `*`(h1))), `*`(`^`(`+`(rho, h1), 2)))), N = `/`(`*`(k), `*`(rho)), z0 = `/`(`*`(rho), `*`(`+`(rho, h1))); 1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_65.gif" width="322" height="36" alt="a = `/`(`*`(f), `*`(rho)), b = `+`(`/`(`*`(f), `*`(`+`(rho, h1))), `/`(`*`(N, `*`(rho, `*`(h1))), `*`(`^`(`+`(rho, h1), 2)))), N = `/`(`*`(k), `*`(rho)), z0 = `/`(`*`(rho), `*`(`+`(rho, h1)))" align="center" border="0"></td>
<td width='5%' align='center'>(1.2.1)</td>
</tr>
</table></font>&nbsp;</p>
<dl style="margin-left:40px"><a name="MapleAutoBookmark7" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Probabilities</em></strong></font>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">Here we define the formulas for computing the probabilities phi_n, alpha_n, beta_n as function of the KummerM function parameters: a, b, N, z0:</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_66.gif" width="465" height="32" alt="PhinS := `/`(`*`(pochhammer(a, n), `*`(`^`(`*`(N, `*`(z0)), n), `*`(KummerM(`+`(a, n), `+`(b, n), `+`(`-`(`*`(N, `*`(`^`(z0, 2))))))))), `*`(pochhammer(b, n), `*`(factorial(n), `*`(KummerM(a, b, `*`(N..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_67.gif" width="589" height="32" alt="PhinS := `/`(`*`(pochhammer(a, n), `*`(`^`(`*`(N, `*`(z0)), n), `*`(KummerM(`+`(a, n), `+`(b, n), `+`(`-`(`*`(N, `*`(`^`(z0, 2))))))))), `*`(pochhammer(b, n), `*`(factorial(n), `*`(KummerM(a, b, `*`(N..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_68.gif" width="12" height="14" alt="PhinS := `/`(`*`(pochhammer(a, n), `*`(`^`(`*`(N, `*`(z0)), n), `*`(KummerM(`+`(a, n), `+`(b, n), `+`(`-`(`*`(N, `*`(`^`(z0, 2))))))))), `*`(pochhammer(b, n), `*`(factorial(n), `*`(KummerM(a, b, `*`(N..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_69.gif" width="176" height="14" alt="PhinS := `/`(`*`(pochhammer(a, n), `*`(`^`(`*`(N, `*`(z0)), n), `*`(KummerM(`+`(a, n), `+`(b, n), `+`(`-`(`*`(N, `*`(`^`(z0, 2))))))))), `*`(pochhammer(b, n), `*`(factorial(n), `*`(KummerM(a, b, `*`(N..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">We compute the probabilities phi_n, alpha_n, beta_n for given values of the KummerM function parameters.
<br>The parameter K gives the maximal value for n and is choosen to ensure that phi0+phi1+...+phiK~1</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_70.gif" width="220" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_71.gif" width="350" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_72.gif" width="129" height="30" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_73.gif" width="361" height="30" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_74.gif" width="12" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_75.gif" width="138" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_76.gif" width="271" height="30" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_77.gif" width="241" height="30" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_78.gif" width="12" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_79.gif" width="86" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_80.gif" width="77" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_81.gif" width="133" height="30" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_82.gif" width="132" height="30" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_83.gif" width="12" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_84.gif" width="648" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_85.gif" width="648" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_86.gif" width="12" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_87.gif" width="8" height="13" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_88.gif" width="12" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_89.gif" width="392" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_90.gif" width="134" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_91.gif" width="532" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_92.gif" width="608" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_93.gif" width="387" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_94.gif" width="494" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_95.gif" width="545" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_96.gif" width="589" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_97.gif" width="84" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_98.gif" width="540" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_99.gif" width="447" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_100.gif" width="84" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_101.gif" width="51" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_102.gif" width="8" height="13" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_103.gif" width="129" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_104.gif" width="68" height="14" alt="PrS := proc (A, B, Z0, rho, K, report) local j, N1, pnts, palpha, nmean, fano, cov, k, f, h1, h1_eff; N1 := `/`(`*`(`+`(B, `-`(`*`(A, `*`(Z0))))), `*`(Z0, `*`(`+`(1, `-`(Z0))))); palpha := `/`(`*`(A, ..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">Here, we have an example to test the SRG probabilities procedure:</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_105.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_106.gif" width="648" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_107.gif" width="104" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_108.gif" width="124" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_109.gif" width="648" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_110.gif" width="648" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_111.gif" width="29" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_112.gif" width="135" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_113.gif" width="340" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_114.gif" width="29" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_115.gif" width="322" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.5e-1]); 1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_116.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_117.gif" width="478" height="14" alt="for k1 to 5 do PrS(Af4b[k1], Bf4b[k1], Zf4b[k1], 0.1e-1, Kf4b, false)[2] end do; 1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_118.gif" width="151" height="14" alt="14.883141277015899014" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="center"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_119.gif" width="151" height="14" alt="34.432222430725472793" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="center"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_120.gif" width="151" height="14" alt="60.191394746073296799" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="center"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_121.gif" width="151" height="14" alt="83.160974991360776179" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="center"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_122.gif" width="151" height="14" alt="14.178734358249156220" align="center" border="0"></td>
<td width='5%' align='center'>(1.2.1.1)</td>
</tr>
</table></font>&nbsp;</p>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark8" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Pearson correlation</em></strong></font>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">In a SRG, we compute the Pearson correlation between number of proteins n and auxiliar random variable of state gene promoter for given values of the KummerM function parameters by the following procedure:</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_123.gif" width="172" height="14" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_124.gif" width="311" height="14" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_125.gif" width="143" height="46" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_126.gif" width="217" height="14" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_127.gif" width="276" height="30" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_128.gif" width="540" height="30" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_129.gif" width="328" height="14" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_130.gif" width="457" height="30" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_131.gif" width="627" height="32" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_132.gif" width="410" height="14" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_133.gif" width="85" height="14" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_134.gif" width="68" height="14" alt="CorrS := proc (Z0, B, npnts) local step, A, N1, palpha, nmean, covS, corrS, pnts; step := evalf(`/`(`*`(B), `*`(Z0, `*`(npnts)))); A := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [se..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">We can to test the SRG correlation procedure in this example below:</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_135.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_136.gif" width="254" height="14" alt="zf2 := .45; -1; Bf2 := 100; -1; npntsf2 := 1000; -1; corrf2b := []; -1; corrf2c := []; -1; corr_aux := CorrS(zf2, Bf2, npntsf2); -1; corrf2b := [op(corrf2b), [seq([corr_aux[i][1], corr_aux[i][3]], i =..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_137.gif" width="182" height="14" alt="zf2 := .45; -1; Bf2 := 100; -1; npntsf2 := 1000; -1; corrf2b := []; -1; corrf2c := []; -1; corr_aux := CorrS(zf2, Bf2, npntsf2); -1; corrf2b := [op(corrf2b), [seq([corr_aux[i][1], corr_aux[i][3]], i =..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_138.gif" width="232" height="14" alt="zf2 := .45; -1; Bf2 := 100; -1; npntsf2 := 1000; -1; corrf2b := []; -1; corrf2c := []; -1; corr_aux := CorrS(zf2, Bf2, npntsf2); -1; corrf2b := [op(corrf2b), [seq([corr_aux[i][1], corr_aux[i][3]], i =..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_139.gif" width="534" height="14" alt="zf2 := .45; -1; Bf2 := 100; -1; npntsf2 := 1000; -1; corrf2b := []; -1; corrf2c := []; -1; corr_aux := CorrS(zf2, Bf2, npntsf2); -1; corrf2b := [op(corrf2b), [seq([corr_aux[i][1], corr_aux[i][3]], i =..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_140.gif" width="531" height="14" alt="zf2 := .45; -1; Bf2 := 100; -1; npntsf2 := 1000; -1; corrf2b := []; -1; corrf2c := []; -1; corr_aux := CorrS(zf2, Bf2, npntsf2); -1; corrf2b := [op(corrf2b), [seq([corr_aux[i][1], corr_aux[i][3]], i =..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_141.gif" width="214" height="14" alt="zf2 := .45; -1; Bf2 := 100; -1; npntsf2 := 1000; -1; corrf2b := []; -1; corrf2c := []; -1; corr_aux := CorrS(zf2, Bf2, npntsf2); -1; corrf2b := [op(corrf2b), [seq([corr_aux[i][1], corr_aux[i][3]], i =..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_142.gif" width="8" height="14" alt="zf2 := .45; -1; Bf2 := 100; -1; npntsf2 := 1000; -1; corrf2b := []; -1; corrf2c := []; -1; corr_aux := CorrS(zf2, Bf2, npntsf2); -1; corrf2b := [op(corrf2b), [seq([corr_aux[i][1], corr_aux[i][3]], i =..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_143.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="center"><tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_144.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark9" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Fano Factor</em></strong></font>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">Here we compute the points for Fano Factor in function of: the probability of gene promotor ON state or the protein mean number: </font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_145.gif" width="167" height="14" alt="FanoS := proc (A, B, npnts) local step, Z0, N1, palpha, nmean, Fano, pnts; step := evalf(`/`(`*`(B), `*`(A, `*`(npnts)))); Z0 := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [seq(`/`(`..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_146.gif" width="280" height="14" alt="FanoS := proc (A, B, npnts) local step, Z0, N1, palpha, nmean, Fano, pnts; step := evalf(`/`(`*`(B), `*`(A, `*`(npnts)))); Z0 := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [seq(`/`(`..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_147.gif" width="143" height="46" alt="FanoS := proc (A, B, npnts) local step, Z0, N1, palpha, nmean, Fano, pnts; step := evalf(`/`(`*`(B), `*`(A, `*`(npnts)))); Z0 := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [seq(`/`(`..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_148.gif" width="223" height="14" alt="FanoS := proc (A, B, npnts) local step, Z0, N1, palpha, nmean, Fano, pnts; step := evalf(`/`(`*`(B), `*`(A, `*`(npnts)))); Z0 := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [seq(`/`(`..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_149.gif" width="300" height="30" alt="FanoS := proc (A, B, npnts) local step, Z0, N1, palpha, nmean, Fano, pnts; step := evalf(`/`(`*`(B), `*`(A, `*`(npnts)))); Z0 := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [seq(`/`(`..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_150.gif" width="563" height="30" alt="FanoS := proc (A, B, npnts) local step, Z0, N1, palpha, nmean, Fano, pnts; step := evalf(`/`(`*`(B), `*`(A, `*`(npnts)))); Z0 := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [seq(`/`(`..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_151.gif" width="328" height="14" alt="FanoS := proc (A, B, npnts) local step, Z0, N1, palpha, nmean, Fano, pnts; step := evalf(`/`(`*`(B), `*`(A, `*`(npnts)))); Z0 := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [seq(`/`(`..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_152.gif" width="492" height="30" alt="FanoS := proc (A, B, npnts) local step, Z0, N1, palpha, nmean, Fano, pnts; step := evalf(`/`(`*`(B), `*`(A, `*`(npnts)))); Z0 := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [seq(`/`(`..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_153.gif" width="407" height="14" alt="FanoS := proc (A, B, npnts) local step, Z0, N1, palpha, nmean, Fano, pnts; step := evalf(`/`(`*`(B), `*`(A, `*`(npnts)))); Z0 := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [seq(`/`(`..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_154.gif" width="85" height="14" alt="FanoS := proc (A, B, npnts) local step, Z0, N1, palpha, nmean, Fano, pnts; step := evalf(`/`(`*`(B), `*`(A, `*`(npnts)))); Z0 := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [seq(`/`(`..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_155.gif" width="68" height="14" alt="FanoS := proc (A, B, npnts) local step, Z0, N1, palpha, nmean, Fano, pnts; step := evalf(`/`(`*`(B), `*`(A, `*`(npnts)))); Z0 := [seq(`*`(step, `*`(i)), i = 1 .. `+`(npnts, `-`(1)))]; N1 := [seq(`/`(`..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">We can to test the SRG Fano factor procedure in this example below:</font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_156.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_157.gif" width="257" height="14" alt="Af5 := 500; -1; Bf5 := 0.1e-1; -1; npntsf5 := 1000; -1; fanof5b := []; -1; fanof5c := []; -1; fano_aux := FanoS(Af5, Bf5, npntsf5); -1; fanof5b := [op(fanof5b), [seq([fano_aux[i][1], fano_aux[i][3]], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_158.gif" width="186" height="14" alt="Af5 := 500; -1; Bf5 := 0.1e-1; -1; npntsf5 := 1000; -1; fanof5b := []; -1; fanof5c := []; -1; fano_aux := FanoS(Af5, Bf5, npntsf5); -1; fanof5b := [op(fanof5b), [seq([fano_aux[i][1], fano_aux[i][3]], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_159.gif" width="241" height="14" alt="Af5 := 500; -1; Bf5 := 0.1e-1; -1; npntsf5 := 1000; -1; fanof5b := []; -1; fanof5c := []; -1; fano_aux := FanoS(Af5, Bf5, npntsf5); -1; fanof5b := [op(fanof5b), [seq([fano_aux[i][1], fano_aux[i][3]], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_160.gif" width="544" height="14" alt="Af5 := 500; -1; Bf5 := 0.1e-1; -1; npntsf5 := 1000; -1; fanof5b := []; -1; fanof5c := []; -1; fano_aux := FanoS(Af5, Bf5, npntsf5); -1; fanof5b := [op(fanof5b), [seq([fano_aux[i][1], fano_aux[i][3]], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_161.gif" width="541" height="14" alt="Af5 := 500; -1; Bf5 := 0.1e-1; -1; npntsf5 := 1000; -1; fanof5b := []; -1; fanof5c := []; -1; fano_aux := FanoS(Af5, Bf5, npntsf5); -1; fanof5b := [op(fanof5b), [seq([fano_aux[i][1], fano_aux[i][3]], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_162.gif" width="180" height="14" alt="Af5 := 500; -1; Bf5 := 0.1e-1; -1; npntsf5 := 1000; -1; fanof5b := []; -1; fanof5c := []; -1; fano_aux := FanoS(Af5, Bf5, npntsf5); -1; fanof5b := [op(fanof5b), [seq([fano_aux[i][1], fano_aux[i][3]], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_163.gif" width="8" height="14" alt="Af5 := 500; -1; Bf5 := 0.1e-1; -1; npntsf5 := 1000; -1; fanof5b := []; -1; fanof5c := []; -1; fano_aux := FanoS(Af5, Bf5, npntsf5); -1; fanof5b := [op(fanof5b), [seq([fano_aux[i][1], fano_aux[i][3]], ..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_164.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="center"><tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_165.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
</dl>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark10" />
<p align="left"><font color="#000000" size="5" face="Serif"><strong>Results</strong></font>&nbsp;</p>
<p align="left"><font color="#000000" size="3" face="Times New Roman">The graphs of correlations, probabilities distributions and Fano factor, the statistical quantities and the kinectic parameters obtained for a ERG and a SRG models are shown in the two subsections below. &nbsp;</font>&nbsp;</p>
<dl style="margin-left:40px"><a name="MapleAutoBookmark11" />
<p align="left"><font color="#000000" size="4" face="Serif"><strong>ERG</strong></font>&nbsp;</p>
<dl style="margin-left:40px"><a name="MapleAutoBookmark12" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Correlation</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_166.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_167.gif" width="338" height="14" alt="Nf2a := 50; -1; Bf2a := [.1, 1, 2, 5, 20]; -1; npntsf2a := 1000; -1; corrf2a := []; -1; for i to nops(Bf2a) do corrf2a := [op(corrf2a), CorrE(Nf2a, Bf2a[i], npntsf2a)] end do; -1" align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_168.gif" width="97" height="14" alt="Nf2a := 50; -1; Bf2a := [.1, 1, 2, 5, 20]; -1; npntsf2a := 1000; -1; corrf2a := []; -1; for i to nops(Bf2a) do corrf2a := [op(corrf2a), CorrE(Nf2a, Bf2a[i], npntsf2a)] end do; -1" align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_169.gif" width="182" height="14" alt="Nf2a := 50; -1; Bf2a := [.1, 1, 2, 5, 20]; -1; npntsf2a := 1000; -1; corrf2a := []; -1; for i to nops(Bf2a) do corrf2a := [op(corrf2a), CorrE(Nf2a, Bf2a[i], npntsf2a)] end do; -1" align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_170.gif" width="351" height="14" alt="Nf2a := 50; -1; Bf2a := [.1, 1, 2, 5, 20]; -1; npntsf2a := 1000; -1; corrf2a := []; -1; for i to nops(Bf2a) do corrf2a := [op(corrf2a), CorrE(Nf2a, Bf2a[i], npntsf2a)] end do; -1" align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_171.gif" width="30" height="14" alt="Nf2a := 50; -1; Bf2a := [.1, 1, 2, 5, 20]; -1; npntsf2a := 1000; -1; corrf2a := []; -1; for i to nops(Bf2a) do corrf2a := [op(corrf2a), CorrE(Nf2a, Bf2a[i], npntsf2a)] end do; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_172.gif" width="648" height="14" alt="plot(corrf2a, view = [0 .. 1, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "ERG: Pearson correlation (N=50)", labels = ["palpha", "Pearson correlation"], la..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_173.gif" width="648" height="14" alt="plot(corrf2a, view = [0 .. 1, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "ERG: Pearson correlation (N=50)", labels = ["palpha", "Pearson correlation"], la..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_174.gif" width="648" height="14" alt="plot(corrf2a, view = [0 .. 1, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "ERG: Pearson correlation (N=50)", labels = ["palpha", "Pearson correlation"], la..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_175.gif" width="12" height="14" alt="plot(corrf2a, view = [0 .. 1, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "ERG: Pearson correlation (N=50)", labels = ["palpha", "Pearson correlation"], la..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_176.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark13" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Quasi-Fano distributions</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_177.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_178.gif" width="392" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_179.gif" width="101" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_180.gif" width="124" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_181.gif" width="419" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_182.gif" width="29" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_183.gif" width="12" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_184.gif" width="135" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_185.gif" width="338" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_186.gif" width="29" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_187.gif" width="12" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_188.gif" width="648" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_189.gif" width="648" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_190.gif" width="648" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_191.gif" width="12" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_192.gif" width="124" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_193.gif" width="249" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_194.gif" width="29" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_195.gif" width="8" height="13" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_196.gif" width="8" height="14" alt="Nf3c := 50; -1; Af3c := [36, 40, 44, 48, 50]; -1; Bf3c := 50; -1; Kf3c := 100; -1; probsf3c := []; -1; for i to 5 do probsf3c := [op(probsf3c), PrE(Nf3c, Af3c[i], Bf3c, 0.1e-1, Kf3c, false)] end do; -..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_197.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="left"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="monospace">################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N=50.0000 	 a=36.0000 	 b=50.0000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.720000 	 &lt;n&gt;=36.0000 	 Fano=1.274510 	 cov=9.882353 
<br>
<br>#################### Kinetic parameters ###########################
<br>k= 0.5000 	 f= 0.3600 	 h2= 0.1400 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N=50.0000 	 a=40.0000 	 b=50.0000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.800000 	 &lt;n&gt;=40.0000 	 Fano=1.196078 	 cov=7.843137 
<br>
<br>#################### Kinetic parameters ###########################
<br>k= 0.5000 	 f= 0.4000 	 h2= 0.1000 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N=50.0000 	 a=44.0000 	 b=50.0000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.880000 	 &lt;n&gt;=44.0000 	 Fano=1.117647 	 cov=5.176471 
<br>
<br>#################### Kinetic parameters ###########################
<br>k= 0.5000 	 f= 0.4400 	 h2= 0.0600 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N=50.0000 	 a=48.0000 	 b=50.0000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.960000 	 &lt;n&gt;=48.0000 	 Fano=1.039216 	 cov=1.882353 
<br>
<br>#################### Kinetic parameters ###########################
<br>k= 0.5000 	 f= 0.4800 	 h2= 0.0200 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N=50.0000 	 a=50.0000 	 b=50.0000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=1.000000 	 &lt;n&gt;=50.0000 	 Fano=1.000000 	 cov=0.000000 
<br>
<br>#################### Kinetic parameters ###########################
<br>k= 0.5000 	 f= 0.5000 	 h2= 0.0000 
<br></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark14" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Super-Fano distributions</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_198.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_199.gif" width="474" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_200.gif" width="107" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_201.gif" width="124" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_202.gif" width="438" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_203.gif" width="29" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_204.gif" width="8" height="13" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_205.gif" width="135" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_206.gif" width="338" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_207.gif" width="30" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_208.gif" width="648" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_209.gif" width="648" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_210.gif" width="648" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_211.gif" width="648" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_212.gif" width="12" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_213.gif" width="124" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_214.gif" width="264" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_215.gif" width="29" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_216.gif" width="8" height="13" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_217.gif" width="8" height="14" alt="Nf4c := 50; -1; Af4c := [.3, .5, 1, 1.5, 1.7]; -1; Bf4c := [.5, 1, 2, 3, 20]; -1; Kf4c := 100; -1; probsf4c := []; -1; for i to 5 do probsf4c := [op(probsf4c), PrE(Nf4c, Af4c[i], Bf4c[i], 0.1e-1, Kf4c..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_218.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="left"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="monospace">################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N=50.0000 	 a= 0.3000 	 b= 0.5000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.600000 	 &lt;n&gt;=30.0000 	 Fano=14.333333 	 cov=400.000000 
<br>
<br>#################### Kinetic parameters ###########################
<br>k= 0.5000 	 f= 0.0030 	 h2= 0.0020 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N=50.0000 	 a= 0.5000 	 b= 1.0000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.500000 	 &lt;n&gt;=25.0000 	 Fano=13.500000 	 cov=312.500000 
<br>
<br>#################### Kinetic parameters ###########################
<br>k= 0.5000 	 f= 0.0050 	 h2= 0.0050 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N=50.0000 	 a= 1.0000 	 b= 2.0000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.500000 	 &lt;n&gt;=25.0000 	 Fano=9.333333 	 cov=208.333333 
<br>
<br>#################### Kinetic parameters ###########################
<br>k= 0.5000 	 f= 0.0100 	 h2= 0.0100 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N=50.0000 	 a= 1.5000 	 b= 3.0000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.500000 	 &lt;n&gt;=25.0000 	 Fano=7.250000 	 cov=156.250000 
<br>
<br>#################### Kinetic parameters ###########################
<br>k= 0.5000 	 f= 0.0150 	 h2= 0.0150 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N=50.0000 	 a= 1.7000 	 b=20.0000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.085000 	 &lt;n&gt;= 4.2500 	 Fano=3.178571 	 cov=9.258929 
<br>
<br>#################### Kinetic parameters ###########################
<br>k= 0.5000 	 f= 0.0170 	 h2= 0.1830 
<br></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark15" />
<p align="left"><font color="#000000" size="4" face="Serif"><strong>SRG</strong></font>&nbsp;</p>
<dl style="margin-left:40px"><a name="MapleAutoBookmark16" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Correlation</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_219.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_220.gif" width="362" height="14" alt="zf2 := .45; -1; Bf2 := [0.1e-1, .1, 1, 10, 100]; -1; npntsf2 := 10000; -1; corrf2b := []; -1; corrf2c := []; -1; for i to nops(Bf2) do corr_aux := CorrS(zf2, Bf2[i], npntsf2); corrf2b := [op(corrf2b),..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_221.gif" width="182" height="14" alt="zf2 := .45; -1; Bf2 := [0.1e-1, .1, 1, 10, 100]; -1; npntsf2 := 10000; -1; corrf2b := []; -1; corrf2c := []; -1; for i to nops(Bf2) do corr_aux := CorrS(zf2, Bf2[i], npntsf2); corrf2b := [op(corrf2b),..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_222.gif" width="175" height="14" alt="zf2 := .45; -1; Bf2 := [0.1e-1, .1, 1, 10, 100]; -1; npntsf2 := 10000; -1; corrf2b := []; -1; corrf2c := []; -1; for i to nops(Bf2) do corr_aux := CorrS(zf2, Bf2[i], npntsf2); corrf2b := [op(corrf2b),..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_223.gif" width="247" height="14" alt="zf2 := .45; -1; Bf2 := [0.1e-1, .1, 1, 10, 100]; -1; npntsf2 := 10000; -1; corrf2b := []; -1; corrf2c := []; -1; for i to nops(Bf2) do corr_aux := CorrS(zf2, Bf2[i], npntsf2); corrf2b := [op(corrf2b),..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_224.gif" width="534" height="14" alt="zf2 := .45; -1; Bf2 := [0.1e-1, .1, 1, 10, 100]; -1; npntsf2 := 10000; -1; corrf2b := []; -1; corrf2c := []; -1; for i to nops(Bf2) do corr_aux := CorrS(zf2, Bf2[i], npntsf2); corrf2b := [op(corrf2b),..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_225.gif" width="531" height="14" alt="zf2 := .45; -1; Bf2 := [0.1e-1, .1, 1, 10, 100]; -1; npntsf2 := 10000; -1; corrf2b := []; -1; corrf2c := []; -1; for i to nops(Bf2) do corr_aux := CorrS(zf2, Bf2[i], npntsf2); corrf2b := [op(corrf2b),..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_226.gif" width="33" height="14" alt="zf2 := .45; -1; Bf2 := [0.1e-1, .1, 1, 10, 100]; -1; npntsf2 := 10000; -1; corrf2b := []; -1; corrf2c := []; -1; for i to nops(Bf2) do corr_aux := CorrS(zf2, Bf2[i], npntsf2); corrf2b := [op(corrf2b),..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<dl style="margin-left:40px"><a name="MapleAutoBookmark17" />
<p align="left"><font color="#000000" size="3" face="Serif"><em></em></font><font color="#000000" size="3" face="Serif"><strong><em>Correlation versus p[alpha]:</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_227.gif" width="608" height="14" alt="plot(corrf2b, view = [0 .. 1, -.5 .. .5], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Pearson correlation (z0=0.45)", labels = ["palpha", "Pearson correlation..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_228.gif" width="608" height="14" alt="plot(corrf2b, view = [0 .. 1, -.5 .. .5], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Pearson correlation (z0=0.45)", labels = ["palpha", "Pearson correlation..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_229.gif" width="608" height="14" alt="plot(corrf2b, view = [0 .. 1, -.5 .. .5], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Pearson correlation (z0=0.45)", labels = ["palpha", "Pearson correlation..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_230.gif" width="608" height="14" alt="plot(corrf2b, view = [0 .. 1, -.5 .. .5], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Pearson correlation (z0=0.45)", labels = ["palpha", "Pearson correlation..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_231.gif" width="12" height="14" alt="plot(corrf2b, view = [0 .. 1, -.5 .. .5], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Pearson correlation (z0=0.45)", labels = ["palpha", "Pearson correlation..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_232.gif" width="8" height="14" alt="plot(corrf2b, view = [0 .. 1, -.5 .. .5], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Pearson correlation (z0=0.45)", labels = ["palpha", "Pearson correlation..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_233.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark18" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_234.gif" width="183" height="14" alt="Typesetting:-delayDotProduct(`*`(Correlation, `*`(versus)), `<,>`(n), true); -1" align="center" border="0"></em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_235.gif" width="608" height="16" alt="semilogplot(corrf2c, view = [`^`(10, -3) .. 100, -.5 .. .5], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Pearson correlation (z0=0.45)", labels = ["<n>", "Pea..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_236.gif" width="608" height="14" alt="semilogplot(corrf2c, view = [`^`(10, -3) .. 100, -.5 .. .5], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Pearson correlation (z0=0.45)", labels = ["<n>", "Pea..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_237.gif" width="608" height="14" alt="semilogplot(corrf2c, view = [`^`(10, -3) .. 100, -.5 .. .5], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Pearson correlation (z0=0.45)", labels = ["<n>", "Pea..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_238.gif" width="608" height="14" alt="semilogplot(corrf2c, view = [`^`(10, -3) .. 100, -.5 .. .5], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Pearson correlation (z0=0.45)", labels = ["<n>", "Pea..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_239.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark19" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Fano distributions</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_240.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_241.gif" width="485" height="14" alt="Af3a := [10, 20, 30, 40, 50]; -1; Bf3a := [10, 20, 30, 40, 50]; -1; Zf3a := .9; -1; Kf3a := 80; -1; probsf3a := []; -1; for i to 5 do probsf3a := [op(probsf3a), PrS(Af3a[i], Bf3a[i], Zf3a, 0.1e-1, Kf3..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_242.gif" width="108" height="14" alt="Af3a := [10, 20, 30, 40, 50]; -1; Bf3a := [10, 20, 30, 40, 50]; -1; Zf3a := .9; -1; Kf3a := 80; -1; probsf3a := []; -1; for i to 5 do probsf3a := [op(probsf3a), PrS(Af3a[i], Bf3a[i], Zf3a, 0.1e-1, Kf3..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_243.gif" width="124" height="14" alt="Af3a := [10, 20, 30, 40, 50]; -1; Bf3a := [10, 20, 30, 40, 50]; -1; Zf3a := .9; -1; Kf3a := 80; -1; probsf3a := []; -1; for i to 5 do probsf3a := [op(probsf3a), PrS(Af3a[i], Bf3a[i], Zf3a, 0.1e-1, Kf3..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_244.gif" width="461" height="14" alt="Af3a := [10, 20, 30, 40, 50]; -1; Bf3a := [10, 20, 30, 40, 50]; -1; Zf3a := .9; -1; Kf3a := 80; -1; probsf3a := []; -1; for i to 5 do probsf3a := [op(probsf3a), PrS(Af3a[i], Bf3a[i], Zf3a, 0.1e-1, Kf3..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_245.gif" width="29" height="14" alt="Af3a := [10, 20, 30, 40, 50]; -1; Bf3a := [10, 20, 30, 40, 50]; -1; Zf3a := .9; -1; Kf3a := 80; -1; probsf3a := []; -1; for i to 5 do probsf3a := [op(probsf3a), PrS(Af3a[i], Bf3a[i], Zf3a, 0.1e-1, Kf3..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_246.gif" width="8" height="13" alt="Af3a := [10, 20, 30, 40, 50]; -1; Bf3a := [10, 20, 30, 40, 50]; -1; Zf3a := .9; -1; Kf3a := 80; -1; probsf3a := []; -1; for i to 5 do probsf3a := [op(probsf3a), PrS(Af3a[i], Bf3a[i], Zf3a, 0.1e-1, Kf3..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_247.gif" width="135" height="14" alt="Af3a := [10, 20, 30, 40, 50]; -1; Bf3a := [10, 20, 30, 40, 50]; -1; Zf3a := .9; -1; Kf3a := 80; -1; probsf3a := []; -1; for i to 5 do probsf3a := [op(probsf3a), PrS(Af3a[i], Bf3a[i], Zf3a, 0.1e-1, Kf3..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_248.gif" width="340" height="14" alt="Af3a := [10, 20, 30, 40, 50]; -1; Bf3a := [10, 20, 30, 40, 50]; -1; Zf3a := .9; -1; Kf3a := 80; -1; probsf3a := []; -1; for i to 5 do probsf3a := [op(probsf3a), PrS(Af3a[i], Bf3a[i], Zf3a, 0.1e-1, Kf3..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_249.gif" width="29" height="14" alt="Af3a := [10, 20, 30, 40, 50]; -1; Bf3a := [10, 20, 30, 40, 50]; -1; Zf3a := .9; -1; Kf3a := 80; -1; probsf3a := []; -1; for i to 5 do probsf3a := [op(probsf3a), PrS(Af3a[i], Bf3a[i], Zf3a, 0.1e-1, Kf3..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_250.gif" width="648" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .13], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano (a=b, z0 = 0.9)", labels = ["n", "Probabilities"]..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_251.gif" width="648" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .13], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano (a=b, z0 = 0.9)", labels = ["n", "Probabilities"]..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_252.gif" width="648" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .13], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano (a=b, z0 = 0.9)", labels = ["n", "Probabilities"]..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_253.gif" width="12" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .13], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano (a=b, z0 = 0.9)", labels = ["n", "Probabilities"]..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_254.gif" width="12" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .13], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano (a=b, z0 = 0.9)", labels = ["n", "Probabilities"]..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_255.gif" width="124" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .13], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano (a=b, z0 = 0.9)", labels = ["n", "Probabilities"]..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_256.gif" width="289" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .13], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano (a=b, z0 = 0.9)", labels = ["n", "Probabilities"]..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_257.gif" width="29" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .13], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano (a=b, z0 = 0.9)", labels = ["n", "Probabilities"]..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_258.gif" width="8" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .13], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano (a=b, z0 = 0.9)", labels = ["n", "Probabilities"]..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_259.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="left"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="monospace">################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;11.1 	 a=10.0000 	 b=10.0000 	 z0= 0.9000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.900000 	 &lt;n&gt;=10.0000 	 Fano=1.000000 	 cov=-0.000000 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.1111 	 f= 0.1000 	 h1= 0.0011 h1_eff= 0.0111 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;22.2 	 a=20.0000 	 b=20.0000 	 z0= 0.9000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.900000 	 &lt;n&gt;=20.0000 	 Fano=1.000000 	 cov=-0.000000 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.2222 	 f= 0.2000 	 h1= 0.0011 h1_eff= 0.0222 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;33.3 	 a=30.0000 	 b=30.0000 	 z0= 0.9000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.900000 	 &lt;n&gt;=30.0000 	 Fano=1.000000 	 cov=-0.000000 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.3333 	 f= 0.3000 	 h1= 0.0011 h1_eff= 0.0333 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;44.4 	 a=40.0000 	 b=40.0000 	 z0= 0.9000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.900000 	 &lt;n&gt;=40.0000 	 Fano=1.000000 	 cov=-0.000000 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.4444 	 f= 0.4000 	 h1= 0.0011 h1_eff= 0.0444 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;55.6 	 a=50.0000 	 b=50.0000 	 z0= 0.9000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.900000 	 &lt;n&gt;=50.0000 	 Fano=1.000000 	 cov=-0.000000 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.5556 	 f= 0.5000 	 h1= 0.0011 h1_eff= 0.0556 
<br></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark20" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Quasi-Fano distributions</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_260.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_261.gif" width="410" height="14" alt="Af3b := [16, 18, 20, 20.7, 21.5]; -1; Bf3b := 20; -1; Zf3b := .9; -1; Kf3b := 80; -1; probsf3b := []; -1; for i to 5 do probsf3b := [op(probsf3b), PrS(Af3b[i], Bf3b, Zf3b, 0.1e-1, Kf3b, false)[1]] end..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_262.gif" width="108" height="14" alt="Af3b := [16, 18, 20, 20.7, 21.5]; -1; Bf3b := 20; -1; Zf3b := .9; -1; Kf3b := 80; -1; probsf3b := []; -1; for i to 5 do probsf3b := [op(probsf3b), PrS(Af3b[i], Bf3b, Zf3b, 0.1e-1, Kf3b, false)[1]] end..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_263.gif" width="124" height="14" alt="Af3b := [16, 18, 20, 20.7, 21.5]; -1; Bf3b := 20; -1; Zf3b := .9; -1; Kf3b := 80; -1; probsf3b := []; -1; for i to 5 do probsf3b := [op(probsf3b), PrS(Af3b[i], Bf3b, Zf3b, 0.1e-1, Kf3b, false)[1]] end..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_264.gif" width="446" height="14" alt="Af3b := [16, 18, 20, 20.7, 21.5]; -1; Bf3b := 20; -1; Zf3b := .9; -1; Kf3b := 80; -1; probsf3b := []; -1; for i to 5 do probsf3b := [op(probsf3b), PrS(Af3b[i], Bf3b, Zf3b, 0.1e-1, Kf3b, false)[1]] end..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_265.gif" width="29" height="14" alt="Af3b := [16, 18, 20, 20.7, 21.5]; -1; Bf3b := 20; -1; Zf3b := .9; -1; Kf3b := 80; -1; probsf3b := []; -1; for i to 5 do probsf3b := [op(probsf3b), PrS(Af3b[i], Bf3b, Zf3b, 0.1e-1, Kf3b, false)[1]] end..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_266.gif" width="8" height="13" alt="Af3b := [16, 18, 20, 20.7, 21.5]; -1; Bf3b := 20; -1; Zf3b := .9; -1; Kf3b := 80; -1; probsf3b := []; -1; for i to 5 do probsf3b := [op(probsf3b), PrS(Af3b[i], Bf3b, Zf3b, 0.1e-1, Kf3b, false)[1]] end..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_267.gif" width="135" height="14" alt="Af3b := [16, 18, 20, 20.7, 21.5]; -1; Bf3b := 20; -1; Zf3b := .9; -1; Kf3b := 80; -1; probsf3b := []; -1; for i to 5 do probsf3b := [op(probsf3b), PrS(Af3b[i], Bf3b, Zf3b, 0.1e-1, Kf3b, false)[1]] end..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_268.gif" width="340" height="14" alt="Af3b := [16, 18, 20, 20.7, 21.5]; -1; Bf3b := 20; -1; Zf3b := .9; -1; Kf3b := 80; -1; probsf3b := []; -1; for i to 5 do probsf3b := [op(probsf3b), PrS(Af3b[i], Bf3b, Zf3b, 0.1e-1, Kf3b, false)[1]] end..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_269.gif" width="29" height="14" alt="Af3b := [16, 18, 20, 20.7, 21.5]; -1; Bf3b := 20; -1; Zf3b := .9; -1; Kf3b := 80; -1; probsf3b := []; -1; for i to 5 do probsf3b := [op(probsf3b), PrS(Af3b[i], Bf3b, Zf3b, 0.1e-1, Kf3b, false)[1]] end..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_270.gif" width="648" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .155], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: quasi-Fano (b=20, z0=0.9)", labels = ["n", "Probabili..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_271.gif" width="648" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .155], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: quasi-Fano (b=20, z0=0.9)", labels = ["n", "Probabili..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_272.gif" width="648" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .155], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: quasi-Fano (b=20, z0=0.9)", labels = ["n", "Probabili..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_273.gif" width="12" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .155], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: quasi-Fano (b=20, z0=0.9)", labels = ["n", "Probabili..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_274.gif" width="12" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .155], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: quasi-Fano (b=20, z0=0.9)", labels = ["n", "Probabili..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_275.gif" width="124" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .155], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: quasi-Fano (b=20, z0=0.9)", labels = ["n", "Probabili..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_276.gif" width="274" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .155], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: quasi-Fano (b=20, z0=0.9)", labels = ["n", "Probabili..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_277.gif" width="29" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .155], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: quasi-Fano (b=20, z0=0.9)", labels = ["n", "Probabili..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_278.gif" width="8" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 80, 0 .. .155], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: quasi-Fano (b=20, z0=0.9)", labels = ["n", "Probabili..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_279.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="left"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="monospace">################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;62.2 	 a=16.0000 	 b=20.0000 	 z0= 0.9000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.753025 	 &lt;n&gt;=46.8549 	 Fano=1.373870 	 cov=17.517657 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.6222 	 f= 0.1600 	 h1= 0.0011 h1_eff= 0.0622 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;42.2 	 a=18.0000 	 b=20.0000 	 z0= 0.9000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.822842 	 &lt;n&gt;=34.7422 	 Fano=1.136361 	 cov=4.737475 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.4222 	 f= 0.1800 	 h1= 0.0011 h1_eff= 0.0422 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;22.2 	 a=20.0000 	 b=20.0000 	 z0= 0.9000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.900000 	 &lt;n&gt;=20.0000 	 Fano=1.000000 	 cov=-0.000000 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.2222 	 f= 0.2000 	 h1= 0.0011 h1_eff= 0.0222 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;15.2 	 a=20.7000 	 b=20.0000 	 z0= 0.9000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.929506 	 &lt;n&gt;=14.1491 	 Fano=0.979890 	 cov=-0.284538 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.1522 	 f= 0.2070 	 h1= 0.0011 h1_eff= 0.0152 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;&nbsp;7.2 	 a=21.5000 	 b=20.0000 	 z0= 0.9000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.965328 	 &lt;n&gt;= 6.9718 	 Fano=0.978236 	 cov=-0.151733 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.0722 	 f= 0.2150 	 h1= 0.0011 h1_eff= 0.0072 
<br></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark21" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Super-Fano distributions</em></strong></font>&nbsp;</p>
<dl style="margin-left:40px"><a name="MapleAutoBookmark22" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Graph with b fixed</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_280.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_281.gif" width="547" height="14" alt="Af4a := [1.2, 1.0, .8, .8, .8]; -1; Bf4a := 2; -1; Zf4a := [.99, .99, .99, .98, .97]; -1; Kf4a := 150; -1; probsf4a := []; -1; for i to 5 do probsf4a := [op(probsf4a), PrS(Af4a[i], Bf4a, Zf4a[i], 0.1e..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_282.gif" width="108" height="14" alt="Af4a := [1.2, 1.0, .8, .8, .8]; -1; Bf4a := 2; -1; Zf4a := [.99, .99, .99, .98, .97]; -1; Kf4a := 150; -1; probsf4a := []; -1; for i to 5 do probsf4a := [op(probsf4a), PrS(Af4a[i], Bf4a, Zf4a[i], 0.1e..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_283.gif" width="124" height="14" alt="Af4a := [1.2, 1.0, .8, .8, .8]; -1; Bf4a := 2; -1; Zf4a := [.99, .99, .99, .98, .97]; -1; Kf4a := 150; -1; probsf4a := []; -1; for i to 5 do probsf4a := [op(probsf4a), PrS(Af4a[i], Bf4a, Zf4a[i], 0.1e..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_284.gif" width="461" height="14" alt="Af4a := [1.2, 1.0, .8, .8, .8]; -1; Bf4a := 2; -1; Zf4a := [.99, .99, .99, .98, .97]; -1; Kf4a := 150; -1; probsf4a := []; -1; for i to 5 do probsf4a := [op(probsf4a), PrS(Af4a[i], Bf4a, Zf4a[i], 0.1e..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_285.gif" width="29" height="14" alt="Af4a := [1.2, 1.0, .8, .8, .8]; -1; Bf4a := 2; -1; Zf4a := [.99, .99, .99, .98, .97]; -1; Kf4a := 150; -1; probsf4a := []; -1; for i to 5 do probsf4a := [op(probsf4a), PrS(Af4a[i], Bf4a, Zf4a[i], 0.1e..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_286.gif" width="8" height="13" alt="Af4a := [1.2, 1.0, .8, .8, .8]; -1; Bf4a := 2; -1; Zf4a := [.99, .99, .99, .98, .97]; -1; Kf4a := 150; -1; probsf4a := []; -1; for i to 5 do probsf4a := [op(probsf4a), PrS(Af4a[i], Bf4a, Zf4a[i], 0.1e..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_287.gif" width="135" height="14" alt="Af4a := [1.2, 1.0, .8, .8, .8]; -1; Bf4a := 2; -1; Zf4a := [.99, .99, .99, .98, .97]; -1; Kf4a := 150; -1; probsf4a := []; -1; for i to 5 do probsf4a := [op(probsf4a), PrS(Af4a[i], Bf4a, Zf4a[i], 0.1e..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_288.gif" width="340" height="14" alt="Af4a := [1.2, 1.0, .8, .8, .8]; -1; Bf4a := 2; -1; Zf4a := [.99, .99, .99, .98, .97]; -1; Kf4a := 150; -1; probsf4a := []; -1; for i to 5 do probsf4a := [op(probsf4a), PrS(Af4a[i], Bf4a, Zf4a[i], 0.1e..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_289.gif" width="29" height="14" alt="Af4a := [1.2, 1.0, .8, .8, .8]; -1; Bf4a := 2; -1; Zf4a := [.99, .99, .99, .98, .97]; -1; Kf4a := 150; -1; probsf4a := []; -1; for i to 5 do probsf4a := [op(probsf4a), PrS(Af4a[i], Bf4a, Zf4a[i], 0.1e..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_290.gif" width="608" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.3e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG super-Fano (b=2)", labels = ["n", "Probabilities"],..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_291.gif" width="608" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.3e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG super-Fano (b=2)", labels = ["n", "Probabilities"],..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_292.gif" width="608" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.3e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG super-Fano (b=2)", labels = ["n", "Probabilities"],..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_293.gif" width="608" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.3e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG super-Fano (b=2)", labels = ["n", "Probabilities"],..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_294.gif" width="12" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.3e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG super-Fano (b=2)", labels = ["n", "Probabilities"],..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_295.gif" width="12" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.3e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG super-Fano (b=2)", labels = ["n", "Probabilities"],..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_296.gif" width="124" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.3e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG super-Fano (b=2)", labels = ["n", "Probabilities"],..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_297.gif" width="289" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.3e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG super-Fano (b=2)", labels = ["n", "Probabilities"],..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_298.gif" width="29" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.3e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG super-Fano (b=2)", labels = ["n", "Probabilities"],..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_299.gif" width="8" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.3e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG super-Fano (b=2)", labels = ["n", "Probabilities"],..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_300.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="left"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="monospace">################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;82.0 	 a= 1.2000 	 b= 2.0000 	 z0= 0.9900 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.655173 	 &lt;n&gt;=53.7374 	 Fano=9.788682 	 cov=472.281200 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.8202 	 f= 0.0120 	 h1= 0.0001 h1_eff= 0.0082 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;102.0 	 a= 1.0000 	 b= 2.0000 	 z0= 0.9900 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.576942 	 &lt;n&gt;=58.8597 	 Fano=14.734677 	 cov=808.419339 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 1.0202 	 f= 0.0100 	 h1= 0.0001 h1_eff= 0.0102 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;122.0 	 a= 0.8000 	 b= 2.0000 	 z0= 0.9900 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.495255 	 &lt;n&gt;=60.4312 	 Fano=21.286357 	 cov=1225.927970 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 1.2202 	 f= 0.0080 	 h1= 0.0001 h1_eff= 0.0122 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;62.0 	 a= 0.8000 	 b= 2.0000 	 z0= 0.9800 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.490911 	 &lt;n&gt;=30.4565 	 Fano=11.194947 	 cov=310.502815 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.6204 	 f= 0.0080 	 h1= 0.0002 h1_eff= 0.0124 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;42.1 	 a= 0.8000 	 b= 2.0000 	 z0= 0.9700 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.486554 	 &lt;n&gt;=20.4654 	 Fano=7.830994 	 cov=139.798719 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.4206 	 f= 0.0080 	 h1= 0.0003 h1_eff= 0.0126 
<br></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark23" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Graph without fixed parameter </em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_301.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_302.gif" width="608" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_303.gif" width="608" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_304.gif" width="108" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_305.gif" width="124" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_306.gif" width="476" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_307.gif" width="29" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_308.gif" width="8" height="13" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_309.gif" width="135" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_310.gif" width="340" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_311.gif" width="29" height="14" alt="Af4b := [.38, .6, .75, 1.75, .3]; -1; Bf4b := [.6, 1.2, 2, 3, 20]; -1; Zf4b := [.99, .99, .99, .99, .9]; -1; Kf4b := 150; -1; probsf4b := []; -1; for i to 5 do probsf4b := [op(probsf4b), PrS(Af4b[i], ..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_312.gif" width="608" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.51e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: super-Fano", labels = ["n", "Probabilities"], lab..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_313.gif" width="608" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.51e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: super-Fano", labels = ["n", "Probabilities"], lab..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_314.gif" width="608" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.51e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: super-Fano", labels = ["n", "Probabilities"], lab..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_315.gif" width="608" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.51e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: super-Fano", labels = ["n", "Probabilities"], lab..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_316.gif" width="12" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.51e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: super-Fano", labels = ["n", "Probabilities"], lab..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_317.gif" width="12" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.51e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: super-Fano", labels = ["n", "Probabilities"], lab..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_318.gif" width="124" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.51e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: super-Fano", labels = ["n", "Probabilities"], lab..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_319.gif" width="304" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.51e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: super-Fano", labels = ["n", "Probabilities"], lab..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_320.gif" width="29" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.51e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: super-Fano", labels = ["n", "Probabilities"], lab..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_321.gif" width="8" height="14" alt="plot([seq(g[k1], k1 = 1 .. 5)], view = [0 .. 150, 0 .. 0.51e-1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: super-Fano", labels = ["n", "Probabilities"], lab..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_322.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="left"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="monospace">################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;22.6 	 a= 0.3800 	 b= 0.6000 	 z0= 0.9900 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.658370 	 &lt;n&gt;=14.8831 	 Fano=5.638022 	 cov=69.028331 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.2261 	 f= 0.0038 	 h1= 0.0001 h1_eff= 0.0023 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;&nbsp;61.2 	 a= 0.6000 	 b= 1.2000 	 z0= 0.9900 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.562507 	 &lt;n&gt;=34.4322 	 Fano=12.766538 	 cov=405.148046 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 0.6121 	 f= 0.0060 	 h1= 0.0001 h1_eff= 0.0061 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;127.0 	 a= 0.7500 	 b= 2.0000 	 z0= 0.9900 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.473873 	 &lt;n&gt;=60.1914 	 Fano=23.246285 	 cov=1339.034939 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 1.2702 	 f= 0.0075 	 h1= 0.0001 h1_eff= 0.0127 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;128.0 	 a= 1.7500 	 b= 3.0000 	 z0= 0.9900 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.649541 	 &lt;n&gt;=83.1610 	 Fano=11.315696 	 cov=857.863321 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 1.2803 	 f= 0.0175 	 h1= 0.0001 h1_eff= 0.0128 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;219.2 	 a= 0.3000 	 b=20.0000 	 z0= 0.9000 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.064677 	 &lt;n&gt;=14.1787 	 Fano=25.866882 	 cov=352.580909 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 2.1922 	 f= 0.0030 	 h1= 0.0011 h1_eff= 0.2192 
<br></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark24" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Sub-Fano distributions</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_323.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_324.gif" width="550" height="16" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_325.gif" width="220" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_326.gif" width="111" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_327.gif" width="124" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_328.gif" width="471" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_329.gif" width="488" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_330.gif" width="549" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_331.gif" width="29" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_332.gif" width="12" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_333.gif" width="8" height="13" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_334.gif" width="135" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_335.gif" width="346" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_336.gif" width="346" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_337.gif" width="29" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_338.gif" width="12" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_339.gif" width="648" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_340.gif" width="648" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_341.gif" width="648" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_342.gif" width="648" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_343.gif" width="648" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_344.gif" width="12" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_345.gif" width="84" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_346.gif" width="251" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_347.gif" width="124" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_348.gif" width="289" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_349.gif" width="29" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_350.gif" width="84" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_351.gif" width="220" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_352.gif" width="124" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_353.gif" width="287" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_354.gif" width="30" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_355.gif" width="8" height="13" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_356.gif" width="8" height="13" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_357.gif" width="8" height="13" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_358.gif" width="12" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_359.gif" width="12" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_360.gif" width="12" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_361.gif" width="12" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_362.gif" width="12" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_363.gif" width="8" height="14" alt="Af5a := [833, 1667, 3333, 5000, 6667]; -1; Bf5a := [.5, 1, 2, 3, 4]; -1; Zf5a := `+`(`*`(5, `*`(`^`(10, -4)))); -1; Kf5a := 100; -1; probsf5a1 := []; -1; nmeanf5a1 := []; -1; probsf5a2 := []; -1; for ..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_364.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
</tr></font>&nbsp;</p>
<p align="left"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="monospace">
<br>For sub-Fano distributions:
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;167.1 	 a=833.0000 	 b= 0.5000 	 z0= 0.0005 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.050183 	 &lt;n&gt;= 8.3848 	 Fano=0.502254 	 cov=-4.173491 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 1.6708 	 f= 8.3300 	 h1=19.9900 h1_eff= 1.6700 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;333.2 	 a=1667.0000 	 b= 1.0000 	 z0= 0.0005 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.049517 	 &lt;n&gt;=16.4973 	 Fano=0.509992 	 cov=-8.083793 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 3.3317 	 f=16.6700 	 h1=19.9900 h1_eff= 3.3300 
<br></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
<p align="left"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="monospace">################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= &nbsp;667.3 	 a=3333.0000 	 b= 2.0000 	 z0= 0.0005 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.049108 	 &lt;n&gt;=32.7714 	 Fano=0.513676 	 cov=-15.937528 
<br>
<br>#################### Kinetic parameters ############################
<br>k= 6.6733 	 f=33.3300 	 h1=19.9900 h1_eff= 6.6700 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= 1000.5 	 a=5000.0000 	 b= 3.0000 	 z0= 0.0005 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.049003 	 &lt;n&gt;=49.0271 	 Fano=0.514881 	 cov=-23.783969 
<br>
<br>#################### Kinetic parameters ############################
<br>k=10.0050 	 f=50.0000 	 h1=19.9900 h1_eff=10.0000 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= 1333.7 	 a=6667.0000 	 b= 4.0000 	 z0= 0.0005 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.048950 	 &lt;n&gt;=65.2833 	 Fano=0.515480 	 cov=-31.631067 
<br>
<br>#################### Kinetic parameters ############################
<br>k=13.3367 	 f=66.6700 	 h1=19.9900 h1_eff=13.3300 
<br>
<br>
<br>For Fano distributions:
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= 1000.0 	 a= 0.5000 	 b= 0.5000 	 z0= 0.0005 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.000500 	 &lt;n&gt;= 0.5000 	 Fano=1.000000 	 cov=0.000000 
<br>
<br>#################### Kinetic parameters ############################
<br>k=10.0000 	 f= 0.0050 	 h1=19.9900 h1_eff= 9.9950 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= 2000.0 	 a= 1.0000 	 b= 1.0000 	 z0= 0.0005 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.000500 	 &lt;n&gt;= 1.0000 	 Fano=1.000000 	 cov=0.000000 
<br>
<br>#################### Kinetic parameters ############################
<br>k=20.0000 	 f= 0.0100 	 h1=19.9900 h1_eff=19.9900 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= 4000.0 	 a= 2.0000 	 b= 2.0000 	 z0= 0.0005 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.000500 	 &lt;n&gt;= 2.0000 	 Fano=1.000000 	 cov=0.000000 
<br>
<br>#################### Kinetic parameters ############################
<br>k=40.0000 	 f= 0.0200 	 h1=19.9900 h1_eff=39.9800 
<br></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
<p align="left"><tr>
<td valign="top" align="center"><font color="#0000ff" size="3" face="monospace">################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= 6000.0 	 a= 3.0000 	 b= 3.0000 	 z0= 0.0005 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.000500 	 &lt;n&gt;= 3.0000 	 Fano=1.000000 	 cov=0.000000 
<br>
<br>#################### Kinetic parameters ############################
<br>k=60.0000 	 f= 0.0300 	 h1=19.9900 h1_eff=59.9700 
<br>
<br>################################################################
<br>################################################################
<br>
<br>For the KummerM function parameter values being
<br>N= 8000.0 	 a= 4.0000 	 b= 4.0000 	 z0= 0.0005 
<br>
<br>#################### Statistical quantities ###########################
<br>P[alpha]=0.000500 	 &lt;n&gt;= 4.0000 	 Fano=1.000000 	 cov=0.000000 
<br>
<br>#################### Kinetic parameters ############################
<br>k=80.0000 	 f= 0.0400 	 h1=19.9900 h1_eff=79.9600 
<br></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark25" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Fano factor</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_365.gif" width="83" height="14" alt="Digits := 20; -1" align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman">&gt; </font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_366.gif" width="368" height="14" alt="Af5 := 500; -1; Bf5 := [0.1e-1, 0.5e-1, .1, .5, 2]; -1; npntsf5 := 10000; -1; fanof5b := []; -1; fanof5c := []; -1; for i to nops(Bf5) do fano_aux := FanoS(Af5, Bf5[i], npntsf5); fanof5b := [op(fanof5..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_367.gif" width="186" height="14" alt="Af5 := 500; -1; Bf5 := [0.1e-1, 0.5e-1, .1, .5, 2]; -1; npntsf5 := 10000; -1; fanof5b := []; -1; fanof5c := []; -1; for i to nops(Bf5) do fano_aux := FanoS(Af5, Bf5[i], npntsf5); fanof5b := [op(fanof5..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_368.gif" width="175" height="14" alt="Af5 := 500; -1; Bf5 := [0.1e-1, 0.5e-1, .1, .5, 2]; -1; npntsf5 := 10000; -1; fanof5b := []; -1; fanof5c := []; -1; for i to nops(Bf5) do fano_aux := FanoS(Af5, Bf5[i], npntsf5); fanof5b := [op(fanof5..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_369.gif" width="256" height="14" alt="Af5 := 500; -1; Bf5 := [0.1e-1, 0.5e-1, .1, .5, 2]; -1; npntsf5 := 10000; -1; fanof5b := []; -1; fanof5c := []; -1; for i to nops(Bf5) do fano_aux := FanoS(Af5, Bf5[i], npntsf5); fanof5b := [op(fanof5..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_370.gif" width="544" height="14" alt="Af5 := 500; -1; Bf5 := [0.1e-1, 0.5e-1, .1, .5, 2]; -1; npntsf5 := 10000; -1; fanof5b := []; -1; fanof5c := []; -1; for i to nops(Bf5) do fano_aux := FanoS(Af5, Bf5[i], npntsf5); fanof5b := [op(fanof5..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_371.gif" width="541" height="14" alt="Af5 := 500; -1; Bf5 := [0.1e-1, 0.5e-1, .1, .5, 2]; -1; npntsf5 := 10000; -1; fanof5b := []; -1; fanof5c := []; -1; for i to nops(Bf5) do fano_aux := FanoS(Af5, Bf5[i], npntsf5); fanof5b := [op(fanof5..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_372.gif" width="33" height="14" alt="Af5 := 500; -1; Bf5 := [0.1e-1, 0.5e-1, .1, .5, 2]; -1; npntsf5 := 10000; -1; fanof5b := []; -1; fanof5c := []; -1; for i to nops(Bf5) do fano_aux := FanoS(Af5, Bf5[i], npntsf5); fanof5b := [op(fanof5..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_373.gif" width="8" height="14" alt="Af5 := 500; -1; Bf5 := [0.1e-1, 0.5e-1, .1, .5, 2]; -1; npntsf5 := 10000; -1; fanof5b := []; -1; fanof5c := []; -1; for i to nops(Bf5) do fano_aux := FanoS(Af5, Bf5[i], npntsf5); fanof5b := [op(fanof5..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<dl style="margin-left:40px"><a name="MapleAutoBookmark26" />
<p align="left"><font color="#000000" size="3" face="Serif"><em></em></font><font color="#000000" size="3" face="Serif"><strong><em>Fano versus p[alpha]:</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_374.gif" width="608" height="14" alt="plot(fanof5b, view = [0 .. 1, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano Factor (a=500)", labels = ["palpha", "Fano factor"], labeldirections =..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_375.gif" width="608" height="14" alt="plot(fanof5b, view = [0 .. 1, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano Factor (a=500)", labels = ["palpha", "Fano factor"], labeldirections =..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_376.gif" width="608" height="14" alt="plot(fanof5b, view = [0 .. 1, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano Factor (a=500)", labels = ["palpha", "Fano factor"], labeldirections =..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_377.gif" width="608" height="14" alt="plot(fanof5b, view = [0 .. 1, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano Factor (a=500)", labels = ["palpha", "Fano factor"], labeldirections =..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_378.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
<td width='5%' align='center'></td>
</tr>
</table></font>&nbsp;</p>
</dl>
<dl style="margin-left:40px"><a name="MapleAutoBookmark27" />
<p align="left"><font color="#000000" size="3" face="Serif"><strong><em>Fano versus &lt;n&gt;:</em></strong></font>&nbsp;</p>
<p align="left"><table>
<tr>
<td valign="top" align="center"><font color="#ff0000" size="3" face="monospace"><strong>&gt; </strong></font></td>
<td valign="top"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_379.gif" width="608" height="14" alt="plot(fanof5c, view = [0 .. 7, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano Factor (a=500)", labels = ["<n>", "Fano factor"], labeldirections = ["..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_380.gif" width="608" height="14" alt="plot(fanof5c, view = [0 .. 7, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano Factor (a=500)", labels = ["<n>", "Fano factor"], labeldirections = ["..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_381.gif" width="608" height="14" alt="plot(fanof5c, view = [0 .. 7, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano Factor (a=500)", labels = ["<n>", "Fano factor"], labeldirections = ["..." align="center" border="0"><br><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_382.gif" width="13" height="14" alt="plot(fanof5c, view = [0 .. 7, 0 .. 1], color = [red, blue, green, cyan, magenta], thickness = 2, axes = boxed, title = "SRG: Fano Factor (a=500)", labels = ["<n>", "Fano factor"], labeldirections = ["..." align="center" border="0"></td>
</tr>
</table>&nbsp;</p>
<p align="center"><table width='100%'>
<tr>
<td valign="top" align="center"><font color="#000000" size="3" face="Times New Roman"><img src="img/ComparativeAnalysisNoise_ProbabilitesAndMoments_383.gif" width="400" height="400" alt="Plot_2d" align="center" border="0"></td>
<td width='5%' align='center'></td>
</tr>
</dl>
</dl>
</dl>
</dl>
</body>
</html>

