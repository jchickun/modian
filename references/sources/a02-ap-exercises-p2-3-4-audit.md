# AP A02 P2.3–P2.4 原页与计算复核

**来源：**《模拟电子技术基础学习辅导与习题解答（第六版）》第 2 章。  
**核对页：**P2.3 题干及 Q 点关系 PDF p.76 / 印刷 p.67，四种原电路 PDF p.77 / 印刷 p.68，交流等效图与小信号式 PDF p.78 / 印刷 p.69；P2.4 电路、输出特性图、负载线与解答 PDF p.79 / 印刷 p.70。已查看图像并按原图对照器件、电阻和电容编号。

## P2.3：两种电路的模型复核

### (a) 集电极反馈共射

按原图 DC 回路，基极偏置电流经过 \(R_1,R_2\) 和 B-E 结，集电极支路的 \(R_3\) 承载 \(I_C+I_B=(1+\beta)I_B\)。KVL 给出：

\[
V_{CC}-U_{BEQ}=I_{BQ}(R_1+R_2)+(1+\beta)I_{BQ}R_3,
\]
\[
I_{CQ}=\beta I_{BQ},\qquad
U_{CEQ}=V_{CC}-(1+\beta)I_{BQ}R_3.
\]

中频时 \(C_2\) 使 \(R_1,R_2\) 的连接点交流接地；故基极支路为 \(R_1\)，集电极负载为 \(R_2\parallel R_3\)。忽略晶体管 \(r_o\)：

\[
A_u=-\frac{\beta(R_2\parallel R_3)}{r_{be}},\quad
R_i=r_{be}\parallel R_1,\quad
R_o=R_2\parallel R_3.
\]

符号、连接和公式与原书等效图一致；Q 点公式还假设器件处于放大区。

### (b) 分压偏置共基

基极分压网络的戴维南等效为
\[
V_{BB}=\frac{R_2}{R_2+R_3}V_{CC},\qquad R_b=R_2\parallel R_3.
\]
发射极电阻为 \(R_1\)，故
\[
I_{BQ}=\frac{V_{BB}-U_{BEQ}}{R_b+(1+\beta)R_1},\quad
I_{CQ}=\beta I_{BQ}.
\]
精确的外回路关系可写为
\[
U_{CEQ}=V_{CC}-I_{CQ}R_4-I_{EQ}R_1.
\]
原书使用 \(I_E\approx I_C\)，因此给出 \(U_{CEQ}\approx V_{CC}-I_{CQ}(R_4+R_1)\)。这属于常用近似；当需保留有限基极电流时用 \(I_E=(1+\beta)I_B\)。

中频 \(C_3\) 将基极交流接地，输入从发射极进入：
\[
A_u=\frac{\beta R_4}{r_{be}},\quad
R_i=R_1\parallel\frac{r_{be}}{1+\beta},\quad
R_o=R_4,
\]
其中忽略晶体管输出电阻，并按题目端口定义测量输入/输出电阻。正增益符号与共基同相关系一致。

## P2.4：图解 Q 点和最大不失真输出

题图给 \(V_{CC}=12\,\text{V}\)、\(R_C=3\,\text{k}\Omega\)、\(R_B=15\,\text{k}\Omega\)、\(V_{BB}=1\,\text{V}\)、\(\beta=100\)、\(U_{BEQ}=0.7\,\text{V}\)。空载时
\[
I_{BQ}=\frac{1-0.7}{15\,\text{k}\Omega}=20\,\mu\text{A},\quad
I_{CQ}=2\,\text{mA},\quad
U_{CEQ}=12-(2\,\text{mA})(3\,\text{k}\Omega)=6\,\text{V}.
\]
按原书用 \(U_{CES}\approx U_{BEQ}=0.7\,\text{V}\)，饱和侧峰值余量约 \(5.3\,\text{V}\)，截止侧余量为 \(6\,\text{V}\)，故最大输出有效值约 \(5.3/\sqrt2=3.75\,\text{V}\)。

当 \(R_L=3\,\text{k}\Omega\) 直连时，输出回路戴维南等效为
\[
V'_{CC}=12\frac{R_L}{R_C+R_L}=6\,\text{V},\qquad
R'_C=R_C\parallel R_L=1.5\,\text{k}\Omega.
\]
基极偏置不变，\(I_{CQ}=2\,\text{mA}\)，新 Q 点 \(U_{CEQ}=6-(2\,\text{mA})(1.5\,\text{k}\Omega)=3\,\text{V}\)。截止侧余量 \(3\,\text{V}\)，饱和侧余量 \(3-0.7=2.3\,\text{V}\) 较小，故输出有效值约 \(2.3/\sqrt2=1.63\,\text{V}\)，与 AP 图解读数相符。

## 结论与边界

- P2.3 的两个拓扑、小信号共用端和 Q 点表达式与原书等效图一致；共基 Q 点的 \(I_E\approx I_C\) 近似已单独标明。
- P2.4 的 Q 点及带载负载线计算与原页结果相符。\(U_{CES}\approx U_{BEQ}\) 是该题的图解估算，实际器件应使用题设或数据手册给出的饱和压降。
- 本批未发现算术勘误；AP A02 的其他未复核题目仍保留在[逐章台账](chapter-distillation-status.md)。
