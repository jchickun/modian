# AP A02 习题 P2.13–P2.16 原页与计算审计

## 来源与页图

- 来源文件：模拟电子技术基础 学习辅导与习题解答 第六版 (华成英 童诗白).pdf；SHA-256：`2BF2C33FFA1CAAE7291892EE8B9EC7F001741A62861089955E4D593EB65DDC00`。
- 目视核对 PDF pp.84–88（印刷 pp.75–79）：P2.13 题图/解答跨 pp.84–85；P2.14 题图/改正图在 pp.85–86；P2.15 题图、转移/输出特性曲线及解图在 pp.86–87；P2.16 题图、转移曲线与解答在 p.88。
- 图中电路连接、器件极性和参数均以页图为准。文字层只用于定位。

## P2.13：带载共射级与发射极旁路电容开路

### 原图和原书结果

原图参数为 \(\beta=60\)、\(r_{bb'}=100\,\Omega\)、\(V_{CC}=12\,\mathrm V\)、\(R_B=300\,\mathrm{k\Omega}\)、\(R_C=3\,\mathrm{k\Omega}\)、\(R_E=1\,\mathrm{k\Omega}\)、\(R_L=3\,\mathrm{k\Omega}\)、\(R_s=2\,\mathrm{k\Omega}\)。\(C_3\) 并联在 \(R_E\) 两端；题目要求正常与 \(C_3\) 开路两种状态的 Q 点、增益和端口电阻，并由 \(U_s=10\,\mathrm{mV}_{\rm rms}\) 求 \(U_i,U_o\)。

原书约给 \(I_{BQ}=31\,\mu\mathrm A\)、\(I_{CQ}=1.86\,\mathrm{mA}\)、\(U_{CEQ}=4.56\,\mathrm V\)、\(r_{be}=939\,\Omega\)。正常旁路时 \(R_i\approx939\,\Omega\)、\(A_u\approx-96\)、\(R_o=3\,\mathrm{k\Omega}\)、\(U_i\approx3.2\,\mathrm{mV}\)、\(U_o\approx307\,\mathrm{mV}\)。电容开路时 \(R_i\approx51.3\,\mathrm{k\Omega}\)、\(A_u\approx-1.5\)、\(U_i\approx9.6\,\mathrm{mV}\)、\(U_o\approx14.4\,\mathrm{mV}\)。

### 独立复算

直流下耦合电容与 \(C_3\) 均开路，故两种交流状态的 Q 点相同。取 \(U_{BEQ}=0.7\,\mathrm V\)，保留有限 \(\beta\)：

\[
I_{BQ}=\frac{12-0.7}{300\,\mathrm{k\Omega}+61(1\,\mathrm{k\Omega})}
=31.302\,\mu\mathrm A,
\]
\[
I_{CQ}=1.8781\,\mathrm{mA},\quad
I_{EQ}=1.9094\,\mathrm{mA},\quad
U_{CEQ}=12-I_{CQ}R_C-I_{EQ}R_E=4.456\,\mathrm V.
\]

原书将 \(I_E\) 近似为 \(I_C\)，并使用圆整电流，因此 \(4.56\,\mathrm V\) 属于其近似结果，不是另一 Q 点。

用 \(U_T=26\,\mathrm{mV}\) 得
\[
r_{be}=r_{bb'}+\frac{(1+\beta)U_T}{I_E}=930.6\,\Omega,\qquad
R'_L=R_C\parallel R_L=1.5\,\mathrm{k\Omega}.
\]

正常旁路时，
\[
R_i=R_B\parallel r_{be}=927.7\,\Omega,\quad
A_u=-\frac{\beta R'_L}{r_{be}}=-96.71.
\]
按题目给的信号源有效值，\(U_i=U_sR_i/(R_s+R_i)=3.169\,\mathrm{mV}_{\rm rms}\)，\(U_o=|A_u|U_i=306.5\,\mathrm{mV}_{\rm rms}\)。与原书圆整值相符。

\(C_3\) 开路时，
\[
R_i=R_B\parallel[r_{be}+61R_E]=51.33\,\mathrm{k\Omega},\quad
A_u=-\frac{\beta R'_L}{r_{be}+61R_E}=-1.453.
\]
于是 \(U_i=9.625\,\mathrm{mV}_{\rm rms}\)，\(U_o=13.99\,\mathrm{mV}_{\rm rms}\)。原书使用强退化近似 \(A_u\approx-R'_L/R_E=-1.5\)，故报 \(14.4\,\mathrm{mV}\)。\(R_i\) 上升是源端分压变小的原因；发射极交流退化则使放大器增益明显下降。忽略晶体管 \(r_o\) 时 \(R_o\approx R_C=3\,\mathrm{k\Omega}\)，且题给 \(R_L\) 不计入放大器自身输出电阻。

## P2.14：修正三种共源 FET 接法

页图显示原题要求保留共源结构。逐图对照解图：

| 原图 | 原书修正图的关键变化 | 核查说明 |
|---|---|---|
| (a) N 沟道常导通器件，源极直接接地 | 源极串入 \(R_S\)，形成 \(U_{GSQ}\approx-I_D R_S<0\) | 负偏置避免正向输入摆动使栅源结正偏；需再按器件曲线选 \(R_S\) 和 Q 点。 |
| (b) N 沟道自偏置器件，漏极直接接电源 | 漏极串入 \(R_D\)，输入端加耦合电容；解图保留未旁路源极电阻 | \(R_D\) 将漏极电流变化转成电压变化；耦合电容隔断信号源直流，栅极泄放电阻与源极电阻建立自偏置。源极旁路电容影响交流增益，不负责建立直流偏置。 |
| (c) P 沟道增强型 MOS | 漏极电源改为 \(-V_{DD}\)，栅极偏置改为负的 \(-V_{GG}\) | 要使 \(V_G<V_S\)、\(U_{GS}<0\) 并维持正确的漏极电流方向。原题图/解图中的电源标注不同，但负极性条件清楚。 |

不应把“共源”本身当作电源极性判据；应检查器件类型、静态 \(U_{GS}\)、电流通路和漏极电阻是否能产生输出电压。

## P2.15：由 JFET 曲线读 Q 点和小信号参数

原图给 \(V_{DD}=10\,\mathrm V\)、\(R_D=5\,\mathrm{k\Omega}\)、\(R_S=2\,\mathrm{k\Omega}\)、\(R_G=1\,\mathrm{M\Omega}\)，且 \(C_3\) 旁路 \(R_S\)。转移曲线约为 \(I_{DSS}=4\,\mathrm{mA}\)、\(U_{GS(off)}=-4\,\mathrm V\)。原解图在自偏压线 \(U_{GS}=-I_DR_S\) 与转移曲线交点读得 \(I_{DQ}\approx1\,\mathrm{mA}\)、\(U_{GSQ}\approx-2\,\mathrm V\)；输出特性与直流负载线交点读得 \(U_{DSQ}\approx3\,\mathrm V\)。

独立关系检查：
\[
I_D=I_{DSS}\left(1-\frac{U_{GS}}{U_{GS(off)}}\right)^2
=4(1-2/4)^2\,\mathrm{mA}=1\,\mathrm{mA},
\]
\[
U_{DS}=V_{DD}-I_D(R_D+R_S)=10-1(5+2)=3\,\mathrm V.
\]
Q 点也满足 JFET 饱和近似边界 \(U_{DS}\gtrsim U_{GS}-U_{GS(off)}=2\,\mathrm V\)。这些是曲线读数和理想化器件关系下的约值。

中频且 \(C_3\) 充分旁路、忽略 \(r_o\) 与外接负载时，\(g_m\approx2\sqrt{I_{DSS}I_{DQ}}/|U_{GS(off)}|=1\,\mathrm{mS}\)，故 \(A_u\approx-g_mR_D=-5\)、\(R_i\approx R_G=1\,\mathrm{M\Omega}\)、\(R_o\approx R_D=5\,\mathrm{k\Omega}\)。若旁路不充分或加接负载，增益/输出电阻须按相应交流等效图重算。

## P2.16：增强型 NMOS 与原书算术错误

原图参数为 \(V_{DD}=15\,\mathrm V\)、\(R_D=6.2\,\mathrm{k\Omega}\)、源极接地、直流栅极 \(V_{GG}=3\,\mathrm V\)。转移曲线读得 \(U_{GS(th)}\approx2\,\mathrm V\)、在 \(U_{GS}=4\,\mathrm V\) 时 \(I_D\approx I_{D0}=4\,\mathrm{mA}\)，在 \(U_{GS}=3\,\mathrm V\) 时 \(I_D\approx1\,\mathrm{mA}\)。

原书 Q 点电流读取正确，但把
\[
U_{DSQ}=V_{DD}-I_{DQ}R_D
=15-(1\,\mathrm{mA})(6.2\,\mathrm{k\Omega})
\]
写成 \(5\,\mathrm V\)。按图中参数结果应为 \(8.8\,\mathrm V\)，此处确认为原书算术错误。

沿用原题平方律模型，
\[
g_m\approx\frac{2}{U_{GS(th)}}\sqrt{I_{DQ}I_{D0}}
=2\,\mathrm{mS},\qquad A_u\approx-g_mR_D=-12.4.
\]
要求 \(|A_u|=15\) 时，
\[
g_m=\frac{15}{6.2\,\mathrm{k\Omega}}=2.419\,\mathrm{mS},\quad
I_{DQ}=\frac{[g_mU_{GS(th)}/2]^2}{I_{D0}}
=1.463\,\mathrm{mA},
\]
\[
U_{GSQ}=U_{GS(th)}\left(1+\sqrt{\frac{I_{DQ}}{I_{D0}}}\right)
=3.210\,\mathrm V,\qquad
U_{DSQ}=15-I_{DQ}R_D=5.927\,\mathrm V.
\]
所以需提高栅极静态电压。改后过驱动 \(U_{GSQ}-U_{GS(th)}=1.210\,\mathrm V\)，而 \(U_{DSQ}>1.210\,\mathrm V\)，满足所用饱和区模型的条件。该推导沿用题目图解平方律，并忽略沟道长度调制、外接负载和器件参数离散；原图读数不应报告为高精度器件参数。
