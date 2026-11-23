# AP A02 §2.3 例 2.3.8–2.3.10 原页核对

**来源：**《模拟电子技术基础学习辅导与习题解答（第六版）》。原书 PDF SHA-256：`2BF2C33FFA1CAAE7291892EE8B9EC7F001741A62861089955E4D593EB65DDC00`，与[来源目录](catalog.md)记录一致。  
**核对范围：**PDF pp.66–69（印刷 pp.57–60）；逐页查看原始页面图，并将电路、器件参数、图表读数及公式与[例题重构](../analog/a02-book-examples.md)对照。

| PDF 页 | 印刷页 | 原页内容与核对要点 |
|---:|---:|---|
| 66 | 57 | 开始例 2.3.8 共集电路。页面上端续写的前例输出电阻约 5 kΩ 属于例 2.3.7，不能误归入例 2.3.8。 |
| 67 | 58 | 完成例 2.3.8 的空载/带载增益、输入电阻、源到输出增益和输出电阻；下半页开始例 2.3.9。 |
| 68 | 59 | 完成例 2.3.9 增强型 NMOS 共源计算；下半页开始例 2.3.10 自偏压 JFET。 |
| 69 | 60 | 完成例 2.3.10 的输出特性图解和中频小信号参数；页末转入 §2.3.5。 |

## 例 2.3.8：共集级复算

按题给参数独立计算：

$$
I_{BQ}=\frac{12-0.7}{300\,\mathrm{k\Omega}+121(3\,\mathrm{k\Omega})}
=17.0437\,\mu\mathrm{A},\qquad I_{EQ}=121I_{BQ}=2.06229\,\mathrm{mA},
$$

$$
U_{CEQ}=12-I_{EQ}(3\,\mathrm{k\Omega})=5.8131\,\mathrm{V}.
$$

令 $R'_E=R_E\parallel R_L$。按教材小信号模型，

$$
A_u=\frac{121R'_E}{1.6\,\mathrm{k\Omega}+121R'_E},\qquad
R_i=300\,\mathrm{k\Omega}\parallel[1.6\,\mathrm{k\Omega}+121R'_E],\qquad
A_{us}=A_u\frac{R_i}{R_i+2\,\mathrm{k\Omega}}.
$$

| 负载 | 独立复算 $A_u$ | 独立复算 $R_i$ | 独立复算 $A_{us}$ |
|---|---:|---:|---:|
| $R_L=\infty$ | 0.995612 | 164.580 kΩ | 0.983658 |
| $R_L=3\,\mathrm{k\Omega}$ | 0.991262 | 113.703 kΩ | 0.974127 |

结果与原书舍入值一致。$A_u$ 是放大器输入端至输出端的电压增益，$A_{us}$ 还计入信号源内阻 $R_s$ 的分压；带载时 $R_i$ 与 $A_u$ 均改变。

输出电阻保留基极网络及发射极电阻的完整并联项为

$$
R_o=R_E\parallel\frac{r_{be}+(R_b\parallel R_s)}{1+\beta}
=29.3526\,\Omega.
$$

原书以 $R_b\gg R_s$ 近似 $R_b\parallel R_s\approx R_s$，再略去远大于该支路的 $R_E$ 并联修正，得到 $(1.6+2.0)\,\mathrm{k\Omega}/121\approx29.8\,\Omega$。两者相差约 $0.45\,\Omega$（约为教材值的 1.5%），属于近似层级差异，不是算术错误。测量 $R_o$ 时负载应移除；负载改变不进入该端口输出电阻表达式。

## 例 2.3.9：增强型 NMOS 共源复算

原页曲线读数为 $U_{GSQ}=3\,\mathrm V$、$I_{DQ}=1\,\mathrm{mA}$，$U_{GS(th)}=2\,\mathrm V$，$I_{D0}=4\,\mathrm{mA}$。由直流负载线：

$$
U_{DSQ}=18-(1\,\mathrm{mA})(10\,\mathrm{k\Omega})=8\,\mathrm V.
$$

按页上使用的平方律近似，$g_m=2\sqrt{I_{DQ}I_{D0}}/U_{GS(th)}=2\,\mathrm{mS}$；忽略沟道长度调制且无外接负载时，$A_u\approx-g_mR_D=-20$、$R_o\approx R_D=10\,\mathrm{k\Omega}$。过驱动电压为 $1\,\mathrm V$，故 $U_{DSQ}=8\,\mathrm V$ 满足该理想长沟道模型的饱和区条件 $U_{DSQ}\ge U_{GSQ}-U_{GS(th)}$。输入电阻趋于无穷只针对绝缘栅器件本体；实际级输入仍受偏置网络与漏电影响。

## 例 2.3.10：自偏压 JFET 图解与精算边界

转移特性参数给出 $I_{DSS}=4\,\mathrm{mA}$、$U_{GS(off)}=-4\,\mathrm V$，自偏压线为 $U_{GS}=-I_DR_S$，其中 $R_S=2\,\mathrm{k\Omega}$。联立 Shockley 转移关系后，令 $I_D$ 以 mA 计，有

$$
I_D=4\left(1-\frac{I_D}{2}\right)^2.
$$

代数根为 $I_D=1\,\mathrm{mA}$、$4\,\mathrm{mA}$。物理范围要求 $U_{GS(off)}\le U_{GS}\le0$；第二根对应 $U_{GS}=-8\,\mathrm V$，超出模型有效范围，应舍弃。因此 $I_{DQ}=1\,\mathrm{mA}$、$U_{GSQ}=-2\,\mathrm V$。按题目电阻值精确落在直流负载线上：

$$
U_{DSQ}=10-(1\,\mathrm{mA})(R_D+R_S)=10-(1\,\mathrm{mA})(7\,\mathrm{k\Omega})=3.0\,\mathrm V.
$$

原书按输出特性图读为约 $3.2\,\mathrm V$。这是图解读数与参数代数值之间的约 $0.2\,\mathrm V$ 差异；引用原图读数时保留“约 3.2 V”，按给定电阻和 $1\,\mathrm{mA}$ 精算时写 $3.0\,\mathrm V$，不把两者说成相等或据此判定负载线方程错误。

在中频且源极旁路电容视为短路、忽略器件输出电阻时，$g_m=1\,\mathrm{mS}$，$R_D\parallel R_L=5\,\mathrm{k\Omega}\parallel10\,\mathrm{k\Omega}=3.333\,\mathrm{k\Omega}$，故 $A_u\approx-3.333$、$R_i\approx R_G=2\,\mathrm{M\Omega}$、$R_o\approx R_D=5\,\mathrm{k\Omega}$。增益计算中的旁路条件不适用于低频旁路失效时。

## 审计结论与范围

- 题图参数、管型、连接关系、转移/输出曲线读数及书上公式与例题重构页对应；本批没有发现新的原书算术勘误。
- 两项差异分别保留为明确的近似/图解精度边界：例 2.3.8 的 $R_o$ 约 29.8 Ω（完整并联约 29.35 Ω）；例 2.3.10 的 $U_{DSQ}$ 图读约 3.2 V（按电阻/电流精算 3.0 V）。
- 本记录只覆盖 PDF pp.66–69 的例 2.3.8–2.3.10 原页，不表示 AP §2.3 的其他页面已经逐页复核，也不替代 §2.4 习题页记录。
