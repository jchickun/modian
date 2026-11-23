# AP A02 习题 P2.11–P2.12 原页与计算审计

## 来源与页图

- 来源文件：模拟电子技术基础 学习辅导与习题解答 第六版 (华成英 童诗白).pdf；SHA-256：2BF2C33FFA1CAAE7291892EE8B9EC7F001741A62861089955E4D593EB65DDC00。
- 目视核对 PDF pp.82–84（印刷 pp.73–75）。PDF p.82 可见图 P2.11、题目三问及解答开头；p.83 可见 P2.11 的偏置、交流模型和电容开路结果，以及 P2.12 图和题干；p.84 可见 P2.12 的 Q 点、带载输入电阻/增益和输出电阻公式。
- P2.11 图中 $V_{CC}=12\,\mathrm V$、$R_{b2}=25\,\mathrm{k\Omega}$ 接电源、$R_{b1}=5\,\mathrm{k\Omega}$ 接地、$R_C=R_L=5\,\mathrm{k\Omega}$、未旁路 $R_f=300\,\Omega$、由 $C_e$ 旁路的 $R_e=1\,\mathrm{k\Omega}$，并给出 $\beta=100$、$r_{bb'}=100\,\Omega$。
- P2.12 图中为共集级，集电极接 $+15\,\mathrm V$，$R_B=200\,\mathrm{k\Omega}$、$R_E=3\,\mathrm{k\Omega}$、$R_s=2\,\mathrm{k\Omega}$；输入/输出由电容耦合，题给 $\beta=80$、$r_{be}=1\,\mathrm{k\Omega}$，比较 $R_L=\infty$ 与 $R_L=3\,\mathrm{k\Omega}$。

## P2.11：分压偏置与发射极旁路

### 原页解题路线

原书先用 $R_{b1}/(R_{b1}+R_{b2})$ 估算基极电压约 2 V，再近似 $I_E\approx1\,\mathrm{mA}$、$I_B\approx10\,\mu\mathrm A$、$U_{CEQ}\approx5.7\,\mathrm V$。中频时 $C_e$ 旁路 $R_e$，但 $R_f$ 保留在发射极交流通路；原页给出 $r_{be}\approx2.73\,\mathrm{k\Omega}$、$A_u\approx-7.6$、$R_i\approx3.7\,\mathrm{k\Omega}$、$R_o=R_C=5\,\mathrm{k\Omega}$。把 $\beta$ 改为 200 时，原书认为 Q 点基本不变而基极电流约减半。$C_e$ 开路时 Q 点不变，$R_i\approx4.1\,\mathrm{k\Omega}$、$A_u\approx-1.92$。

### 独立复算与近似边界

分压网络戴维南等效为 $V_{th}=2\,\mathrm V$、$R_{th}=4.167\,\mathrm{k\Omega}$。以 $U_{BE}=0.7\,\mathrm V$ 和完整基极电流负载方程计算：
\[
I_B=\frac{V_{th}-U_{BE}}{R_{th}+(1+\beta)(R_f+R_e)}
=9.596\,\mu\mathrm A,
\]
\[
I_E=0.9692\,\mathrm{mA},\qquad I_C=0.9596\,\mathrm{mA},
\qquad U_{CEQ}=12-I_CR_C-I_E(R_f+R_e)=5.942\,\mathrm V.
\]
原书用理想分压并取 $I_E\approx I_C\approx1\,\mathrm{mA}$，得到 5.7 V；差异来自该近似，不是原书算术错误。

按 $U_T=26\,\mathrm{mV}$，由未圆整 $I_E$ 得 $r_{be}=2.809\,\mathrm{k\Omega}$。中频负载 $R'_L=R_C\parallel R_L=2.5\,\mathrm{k\Omega}$，因 $R_f$ 未旁路：
\[
A_u=-\frac{\beta R'_L}{r_{be}+(1+\beta)R_f}=-7.551,
\]
\[
R_i=R_{b1}\parallel R_{b2}\parallel[r_{be}+(1+\beta)R_f]
=3.701\,\mathrm{k\Omega}.
\]
若按原书 $I_E\approx1\,\mathrm{mA}$ 计算 $r_{be}\approx2.73\,\mathrm{k\Omega}$，便得到 $A_u\approx-7.57$，与印出的约 $-7.6$ 一致。

用同一完整分压方程将 $\beta$ 改为 200，得到 $I_B=4.897\,\mu\mathrm A$、$I_E=0.9843\,\mathrm{mA}$、$I_C=0.9794\,\mathrm{mA}$、$U_{CEQ}=5.823\,\mathrm V$；电流和 Q 点变化较小，符合原书定性判断。

$C_e$ 开路时直流 Q 点不变，交流退化电阻变成 $R_f+R_e=1.3\,\mathrm{k\Omega}$：
\[
R_i=R_{b1}\parallel R_{b2}\parallel[r_{be}+(1+\beta)(R_f+R_e)]
=4.041\,\mathrm{k\Omega},
\]
\[
A_u=-\frac{\beta R'_L}{r_{be}+(1+\beta)(R_f+R_e)}
=-1.864.
\]
原书强退化近似 $-R'_L/(R_f+R_e)=-1.923$ 忽略了 $r_{be}/\beta$ 项；约 3% 的差异是模型精度不同。忽略晶体管 $r_o$ 时，$R_o\approx R_C=5\,\mathrm{k\Omega}$。

## P2.12：共集级带载与输出电阻

### Q 点与负载

按原书采用的 $U_{BEQ}=0.7\,\mathrm V$，输入耦合电容在直流下开路，因此信号源及 $R_s$ 与基极隔离，不参与 Q 点偏置：
\[
I_{BQ}=\frac{15-0.7}{200\,\mathrm{k\Omega}+81(3\,\mathrm{k\Omega})}
=32.280\,\mu\mathrm A,
\]
\[
I_{EQ}=2.6147\,\mathrm{mA},\quad I_{CQ}=2.5824\,\mathrm{mA},
\quad U_{CEQ}=15-I_{EQ}R_E=7.156\,\mathrm V.
\]
输出负载也经电容耦合，所以 $R_L$ 不改变直流 Q 点。题给 $r_{be}=1\,\mathrm{k\Omega}$；按原书公式：
\[
R_i=R_B\parallel[r_{be}+(1+\beta)R'_E],\qquad
A_u=\frac{(1+\beta)R'_E}{r_{be}+(1+\beta)R'_E},
\]
其中空载时 $R'_E=R_E=3\,\mathrm{k\Omega}$，带 $3\,\mathrm{k\Omega}$ 负载时 $R'_E=R_E\parallel R_L=1.5\,\mathrm{k\Omega}$。独立代入分别得：

| 负载 | $R'_E$ | $R_i$ | $A_u$ |
|---|---:|---:|---:|
| $R_L=\infty$ | $3\,\mathrm{k\Omega}$ | $109.91\,\mathrm{k\Omega}$ | $0.9959$ |
| $R_L=3\,\mathrm{k\Omega}$ | $1.5\,\mathrm{k\Omega}$ | $75.97\,\mathrm{k\Omega}$ | $0.9918$ |

与原书约 $110\,\mathrm{k\Omega}/76\,\mathrm{k\Omega}$、$0.996/0.992$ 相符。增益以放大器输入端 $u_i$ 为参考；源到输出的总增益还须乘 $R_i/(R_s+R_i)$。

### 输出电阻及技能稿订正

求输出电阻时移去 $R_L$、将理想输入电压源置零，基极到交流地的电阻为 $R_s\parallel R_B$。忽略晶体管 $r_o$：
\[
R_o=R_E\parallel\frac{r_{be}+(R_s\parallel R_B)}{1+\beta}
=36.35\,\Omega\approx37\,\Omega.
\]
原书公式和约 37 Ω 的答案正确。现有练习稿曾写“若错误地省掉 $R_s$，结果约为 12 Ω”，这句话不准确：若只漏掉 $R_s$、仍保留 $R_B$，该模型给出约 $1.36\,\mathrm{k\Omega}$；约 12.3 Ω 来自把基极错误地视作理想交流地，使用 $R_E\parallel[r_{be}/(1+\beta)]$。因此已将练习稿改为准确描述该错误假设。

## 审计结论

P2.11/P2.12 的题图参数和原书约数均已核对，未发现新增原书算术错误。P2.11 的 Q 点精算与教材理想分压估算、P2.11 电容开路增益与强退化近似，分别保留为不同近似层级。P2.12 必须保留源内阻 $R_s$ 的置零后交流通路来求 $R_o$；外接负载按端口定义先移去。
