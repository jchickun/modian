# AP A02 习题 P2.5 与 P2.7 原页、定义和计算核查

## 来源与页图范围

- 来源文件：`模拟电子技术基础 学习辅导与习题解答 第六版 (华成英 童诗白).pdf`，SHA-256：`2BF2C33FFA1CAAE7291892EE8B9EC7F001741A62861089955E4D593EB65DDC00`。
- 目视核对 PDF pp.79–81（印刷 pp.70–72）：PDF p.79 为 P2.5 题干和图 P2.5；p.80 为 P2.5 第（4）–（12）项、答案序列及 P2.7 题干开头；p.81 为图 P2.7、P2.7 题解及 P2.8。
- P2.5 图示为固定偏置共射，输入、输出电容耦合，发射极交流接地；图值 $R_B=510\,\mathrm{k\Omega}$、$R_C=R_L=5\,\mathrm{k\Omega}$、$R_s=2\,\mathrm{k\Omega}$。P2.7 图示为偏置电阻和信号源都直连基极、负载直连集电极；$V_{CC}=15\,\mathrm V$、$R_B=56\,\mathrm{k\Omega}$、$R_s=3\,\mathrm{k\Omega}$、$R_C=5\,\mathrm{k\Omega}$、$\beta=80$、$r_{bb'}=100\,\Omega$。

## P2.5：小信号增益、端口电阻与源分压

### 原页数据和答案

题给 $\beta=80$、$r_{be}=1\,\mathrm{k\Omega}$、$U_i=20\,\mathrm{mV}$，静态 $U_{BEQ}=0.7\,\mathrm V$、$U_{CEQ}=4\,\mathrm V$、$I_{BQ}=20\,\mu\mathrm A$。PDF p.80 印出的判断答案依次为：

**×、×、×、√、×、×、×、√、√、×、×、√。**

### 独立复算及定义

中频下耦合电容视为短路、电源为交流地，因此集电极交流负载为
\[
R_C'=R_C\parallel R_L=2.5\,\mathrm{k\Omega},\qquad
A_u=\frac{u_o}{u_i}\approx-\frac{\beta R_C'}{r_{be}}=-200.
\]
这里 $u_i$ 是放大器输入端的小信号电压；$R_s$ 不属于放大器的输入电阻。输入电阻、输出电阻在本题采用的混合 (pi) 近似下分别为
\[
R_i=R_B\parallel r_{be}=510\,\mathrm{k\Omega}\parallel1\,\mathrm{k\Omega}
=0.998\,\mathrm{k\Omega},\qquad
R_o\approx R_C=5\,\mathrm{k\Omega}.
\]
求 $R_o$ 时移去外接 $R_L$，并忽略晶体管有限输出电阻。源电压要计入 $R_s$ 与 $R_i$ 的分压：
\[
U_s=U_i\frac{R_s+R_i}{R_i}
=20\,\mathrm{mV}\frac{2+0.998}{0.998}
\approx60.08\,\mathrm{mV}\approx60\,\mathrm{mV},
\]
式中电阻以 kΩ 计。

| 项 | 原页判断内容 | 复核结论 |
|---:|---|---|
| 1 | 用 $-U_{CEQ}/U_i$ 得 $A_u=-200$ | 错。数值巧合；静态管压降不是动态输出电压。 |
| 2 | 用 $-U_{CEQ}/U_{BEQ}$ 得增益 | 错。静态电压比不是小信号增益。 |
| 3 | $A_u=-\beta R_C/r_{be}=-400$ | 错。漏掉电容耦合的 $R_L$。 |
| 4 | $A_u=-\beta(R_C\parallel R_L)/r_{be}=-200$ | 对。 |
| 5 | $R_i=U_i/I_{BQ}=1\,\mathrm{k\Omega}$ | 错。静态基极电流不是交流输入电流。 |
| 6 | $R_i=U_{BEQ}/I_{BQ}=35\,\mathrm{k\Omega}$ | 错。静态端电压/电流比不是增量电阻。 |
| 7 | $R_i\approx R_s+1\,\mathrm{k\Omega}=3\,\mathrm{k\Omega}$ | 错。把信号源内阻并入放大器输入电阻。 |
| 8 | $R_i\approx1\,\mathrm{k\Omega}$ | 对。 |
| 9 | $R_o=5\,\mathrm{k\Omega}$ | 对，按移去负载且忽略晶体管 $r_o$ 的模型。 |
| 10 | $R_o=R_C\parallel R_L=2.5\,\mathrm{k\Omega}$ | 错。保留了外接负载。 |
| 11 | $U_s\approx U_i=20\,\mathrm{mV}$ | 错。忽略了 $R_s$ 与 $R_i$ 的分压。 |
| 12 | $U_s\approx60\,\mathrm{mV}$ | 对。 |

### 输入幅值边界

题目没有注明 $U_i=20\,\mathrm{mV}$ 是峰值还是有效值，也未给饱和压降。若把它按同一幅值口径代入小信号增益式，线性外推要求输出幅值约 4 V；但静态 $U_{CEQ}=4\,\mathrm V$，任何正的饱和压降都会使饱和方向可用摆幅小于 4 V。因此不能把这一输入幅值下的 (-200) 小信号增益直接当作未削顶输出预测。此题的 12 项判断检验公式和端口定义；精确失真幅值需要器件边界和输入幅值口径。

## P2.7：输入源直连、负载直连与端口定义

### 原页数据和直流计算

PDF p.80 题干要求分别在 $R_L=\infty$ 和 $R_L=3\,\mathrm{k\Omega}$ 时求 (Q) 点、$A_u$、$R_i$、$R_o$。输入源经 $R_s$ 直连基极，故直流置零时理想信号源短路，但 $R_s$ 仍是基极到地支路。题解按硅管近似 $U_{BEQ}=0.7\,\mathrm V$（这是题解采用的模型值）计算：
\[
I_{BQ}=\frac{15-0.7}{56\,\mathrm{k\Omega}}-\frac{0.7}{3\,\mathrm{k\Omega}}
=22.024\,\mu\mathrm A,\qquad
I_{CQ}=\beta I_{BQ}=1.7619\,\mathrm{mA}.
\]
空载时
\[
U_{CEQ}=15-I_{CQ}$5\,\mathrm{k\Omega}$=6.1905\,\mathrm V.
\]
有 $R_L=3\,\mathrm{k\Omega}$ 直连时，输出直流网络的戴维南等效为
\[
V'_{CC}=15\frac{3}{5+3}=5.625\,\mathrm V,\qquad
R'_C=5\parallel3=1.875\,\mathrm{k\Omega}.
\]
基极网络未变，所以 $I_{BQ}$ 和 $I_{CQ}$ 不变；但集电极直流电压变为
\[
U_{CEQ}=V'_{CC}-I_{CQ}R'_C=2.3214\,\mathrm V\approx2.3\,\mathrm V.
\]

### 小信号复算

沿原书公式并使用 $U_T=26\,\mathrm{mV}$，令 $I_{EQ}=(1+\beta)I_{BQ}=1.7839\,\mathrm{mA}$：
\[
r_{be}=r_{bb'}+$1+\beta$\frac{26\,\mathrm{mV}}{I_{EQ}}
=1.281\,\mathrm{k\Omega}\approx1.3\,\mathrm{k\Omega}.
\]
于是（电阻均以 kΩ 计）
\[
R_i=R_B\parallel r_{be}=1.252\,\mathrm{k\Omega}\approx1.3\,\mathrm{k\Omega},
\]
\[
A_{u,\,R_L=\infty}\approx-\frac{80(5)}{1.281}=-312.4,
\qquad
A_{u,\,R_L=3\,\mathrm{k\Omega}}\approx-\frac{80(1.875)}{1.281}=-117.1.
\]
采用原书圆整的 $r_{be}=1.3\,\mathrm{k\Omega}$，分别得到约 (-308) 和 (-115)，与原页一致。$A_u$ 按放大器输入端 $u_i$ 定义；如要求从信号源 $u_s$ 到输出的总增益，还须再乘 $R_i/(R_s+R_i)$。

在本题忽略晶体管输出电阻的模型下，输出电阻为 $R_o\approx R_C=5\,\mathrm{k\Omega}$：测量时移去外接 $R_L$，不把负载并入 $R_o$。直连负载会改变直流 Q 点和中频集电极负载，但不改变由 $R_B\parallel r_{be}$ 得到的放大器输入电阻近似。

## 差异判定

P2.5 的 12 项答案序列与原书印刷答案一致；P2.7 的原书约数与独立复算一致，差别来自 $r_{be}\approx1.3\,\mathrm{k\Omega}$ 等中间量圆整。未发现新增原书算术错误。关键适用边界是：P2.5 的 $U_i$ 未说明幅值口径且缺 $U_{CES}$；P2.7 的 $U_{BEQ}=0.7\,\mathrm V$ 是解题采用的硅管近似，且 $R_i$、$R_o$ 按放大器端口定义，不包含外部 $R_s$ 或 $R_L$。
