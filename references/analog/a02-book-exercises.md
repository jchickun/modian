# AP 第 2 章自测与习题重构

**来源：**《模拟电子技术基础学习辅导与习题解答（第六版）》§2.4，印刷页 63–80 / PDF 页 72–89。原题图不复制；涉及端口、偏置极性或电阻标号时，需对照原书相应图。这里保留题目要点、关键推导和答案，避免把题解整页转录进技能。

AT 主教材的章末小结、自测与 P2.1–P2.18 原题图位于 PDF pp.139–149（印刷 pp.106–116），页图范围和数字资源边界见[AT A02 章末页图记录](../sources/a02-at-chapter-end-pages-106-116-audit.md)。

**配套：**[A02 放大电路知识](a02-amplifiers-knowledge.md) · [A02 练习方法与题型路由](a02-amplifiers-practice.md) · [AT A02 例题重构与索引](a02-at-book-examples.md) · [AP 例 2.3.1–2.3.3、2.3.5–2.3.11](a02-book-examples.md) · [AP 例 2.3.4 直流带载共射](a02-loaded-amplifier-example.md)

## 一、§2.4.1 自测题

### 1. 放大原理判断

**原书定位：**AP §2.4.1 自测一，PDF pp.72–73（印刷 pp.63–64）；题干、答案序列及解释见[自测题页图记录](../sources/a02-ap-self-test-pages-63-66-audit.md)。

| 项 | 判断 | 核验要点 |
|---|---|---|
| (1) | × | 放大不要求电压、电流增益同时大于 1；共集可放大电流，共基可放大电压。 |
| (2) | √ | 负载获得的功率大于信号源提供的控制功率，电路具有功率放大特征。 |
| (3) | × | 输出能量由直流电源提供，器件控制其转换，不是有源器件凭空供能。 |
| (4) | × | 交流输入提供控制量；电源功率经器件转换为交流输出。 |
| (5) | √ | 正常放大需要合适的直流偏置和电源。 |
| (6) | × | 直接耦合级可放大缓慢变化且极性不变的信号，输出不会“毫无变化”。 |
| (7) | × | PNP 共射底部削顶可为截止失真，不能一概归为饱和失真。 |

答案序列为 **×、√、×、×、√、×、×**。

### 2. 图 T2.2 的正弦放大可行性

**原书定位：**AP §2.4.1 自测二，PDF pp.73–74（印刷 pp.64–65）；图 T2.2 和逐项判据见[自测题页图记录](../sources/a02-ap-self-test-pages-63-66-audit.md)。

假定电容对交流短路。逐图看信号是否叠加在可用静态工作点上、是否存在完整的输入和输出通路：

| 图 | 判断 | 关键理由或接法 |
|---|---|---|
| (a) | 不可 | 输入被偏置电源短路 |
| (b) | 可 | 共射放大 |
| (c) | 不可 | 信号接在基极与地之间，未叠加在合适的静态偏置上 |
| (d) | 不可 | 偏置电源直接加在发射结，缺少限流，可能损坏晶体管 |
| (e) | 不可 | 输入被电容旁路短路 |
| (f) | 不可 | 输出被直流电源短路 |
| (g) | 可 | N 沟道耗尽型 MOS 共源，静态栅源电压可取 0 |
| (h) | 可 | N 沟道 JFET 共源、自给偏压；\(U_{GSQ}=-I_{DQ}R_S\) |
| (i) | 不可 | N 沟道增强型 MOS 的栅源电压不足，器件截止 |

### 3. 图 T2.3：偏置、增益和负载

**原书定位：**AP §2.4.1 自测三，PDF p.74（印刷 p.65）；参数图和答案见[自测题页图记录](../sources/a02-ap-self-test-pages-63-66-audit.md)。

已知 \(V_{CC}=12\,\text{V}\)、\(\beta=100\)、\(R_b'=100\,\text{k}\Omega\)、静态 \(U_{BEQ}=0.7\,\text{V}\)。

- 若 \(I_{BQ}=20\,\mu\text{A}\)，偏置串联电阻总和
  \[
  R_b=R_b'+R_w=\frac{V_{CC}-U_{BEQ}}{I_{BQ}}\approx565\,\text{k}\Omega .
  \]
- 若 \(U_{CEQ}=6\,\text{V}\)，
  \[
  R_C=\frac{V_{CC}-U_{CEQ}}{\beta I_{BQ}}\approx3\,\text{k}\Omega .
  \]
- \(U_i=5\,\text{mV}_{\rm rms}\)、\(U_o=0.6\,\text{V}_{\rm rms}\) 时，\(A_u=-U_o'/U_i=-120\)；负号表示反相。
- 若 \(R_L=R_C\) 且为电容耦合，中频交流负载减半，输出有效值约为 \(0.3\,\text{V}\)。

### 4. 图 T2.3：不失真摆幅与失真方向

**原书定位：**AP §2.4.1 自测四，PDF p.74（印刷 p.65）；答案选项与结果见[自测题页图记录](../sources/a02-ap-self-test-pages-63-66-audit.md)。

本题给 \(V_{CC}=12\,\text{V}\)、\(R_C=3\,\text{k}\Omega\)、\(U_{CEQ}=6\,\text{V}\)、\(R_L=3\,\text{k}\Omega\)。

- \(R_C\parallel R_L=1.5\,\text{k}\Omega\)，截止侧峰值约 \(I_{CQ}(R_C\parallel R_L)=3\,\text{V}\)，对应有效值 \(3/\sqrt2\approx2.12\,\text{V}\)；按原书给定选项选 **2 V**。
- 减小偏置电阻 \(R_w\) 会增大静态基极电流及可用输出幅度：**增大**。
- 调至最大不失真后再增大输入，答案为**底部失真**。
- 已出现饱和失真时，减小 \(R_C\) 可增加饱和方向的工作余量。

以上选择按原题给出的电路及其小信号/图解近似；实际电路还受器件余量和负载条件限制。

### 5. 基本接法性能对照

**原书定位：**AP §2.4.1 自测五，PDF pp.74–75（印刷 pp.65–66）；比较条件和答案见[自测题页图记录](../sources/a02-ap-self-test-pages-63-66-audit.md)。A–E 依次为共射、共集、共基、共源、共漏；题目规定 \(R_E<R_B\)，并令 \(I_{CQ}\)、\(I_{DQ}\) 相等：

| 性能 | 答案 |
|---|---|
| 输入电阻最小 / 最大 | 最小 C；最大 D、E |
| 输出电阻最小 | B |
| 有电压增益 | A、C、D |
| 有电流增益 | A、B、D、E |
| 高频特性最好 | C |
| 输出与输入同相 / 反相 | 同相 B、C、E；反相 A、D |

性能结论依题目指定的基本电路模型和比较条件；不能脱离偏置、负载与器件参数推广成绝对排名。

### 6. 未完成的 FET 放大电路

**原书定位：**AP §2.4.1 自测六，PDF p.75（印刷 p.66）；未完成电路及两种解图见[自测题页图记录](../sources/a02-ap-self-test-pages-63-66-audit.md)。原书给出 N 沟道耗尽型 MOS 管或 P 沟道耗尽型 MOS 管两种方案。接线时按图检查器件沟道、源漏极方向、静态栅源偏置和漏极电流到输出电压的转换通路。

## 二、§2.4.2 习题 2.1–2.18

### 2.1 修正四个共射电路

**原书定位：**AP P2.1，PDF p.75（印刷 p.66）为原图，PDF p.76（印刷 p.67）为改正图/答案；逐图连线见[P2.1–P2.2 原页核对记录](../sources/a02-ap-exercises-p2-1-2-audit.md)。保持原来的共射接法，按图改正：

- (a) 把错误的 \(-V_{CC}\) 改为 \(+V_{CC}\)。
- (b) 断开 \(+V_{CC}\) 到基极的直连，在电源与基极之间串入 \(R_b\)，以建立可控基极电流。
- (c) 反接 \(V_{BB}\)，并在输入信号支路串入限流电阻或隔直电容，避免输入源支路破坏偏置/形成过大结电流。
- (d) 在 \(V_{BB}\) 支路加基极限流电阻；按静态端电位将耦合电容左极板接正；在 \(-V_{CC}\) 与集电极之间补入 \(R_C\)，形成集电极直流负载。

核对逻辑：基极—发射极结须有正确正向偏置且输入直流电流受限；集电极须经负载电阻接到与管型/电源极性相符的电源；耦合电容极性按两侧静态电位确定。修正只要求电路具备放大正弦信号的可能，不代表任意电阻值都能得到合适 Q 点。

### 2.2 画直流与交流通路

**原书定位：**AP P2.2，PDF pp.76–78（印刷 pp.67–69）；图 P2.2 和直流/交流等效图 P2.2.1、P2.2.2 均已核对，见[P2.1–P2.2 原页核对记录](../sources/a02-ap-exercises-p2-1-2-audit.md)。

统一规则：直流等效时所有电容开路、理想变压器绕组按直流导线处理；中频交流等效时所有耦合/旁路电容短路、理想直流电源交流接地，理想变压器保留绕组耦合并按匝比折算负载。

| 电路 | 直流通路 | 中频交流通路与接法 |
|---|---|---|
| (a) | \(+V_{CC}\to R_3\to\) 集电极—发射极支路；基极偏置还经过 \(R_2,R_1\) 与基极—发射极结形成反馈通路 | \(C_2\) 将 \(R_1,R_2\) 中间节点交流接地，基极看到 \(R_1\)，集电极负载为 \(R_2\parallel R_3\)，发射极为共用端；共射 |
| (b) | \(R_2,R_3\) 分压偏置基极；集电极电流经 \(R_4\)，发射极电流经 \(R_1\) 返回地 | \(C_3\) 使基极交流接地，输入从发射极进入、输出从集电极取出；共基 |
| (c) | 两管直接耦合，按各自偏置电阻建立 Q 点；\(T_1\) 集电极连接到 \(T_2\) 发射极 | \(C_1\) 交流接地 \(T_2\) 基极，\(T_1\) 为共射级、\(T_2\) 为共基级；共射—共基组合 |
| (d) | 电容开路，变压器绕组按直流导线处理；偏置与集电极/发射极电阻建立静态电流 | 输入、输出变压器保留耦合关系，次级负载按匝比反射；输入/输出电容短路，发射极为共用端；变压器耦合共射 |

先由直流通路确认偏置和完整电流回路，再由交流通路识别共用端；变压器电路不能把绕组在交流模型中也一概短接。

### 2.3 识别接法并写出两种电路的 Q 点与小信号关系

**原书定位：**AP P2.3，PDF pp.76–78（印刷 pp.67–69），沿用 P2.2 的图及 DC/AC 等效图；电流路径与表达式来源见[P2.3–P2.4 原页复核](../sources/a02-ap-exercises-p2-3-4-audit.md)。

图 P2.2 中，(a) 为带集电极反馈的共射，(b) 为分压偏置共基，(c) 为共射—共基组合，(d) 为变压器耦合共射。

**(a) 集电极反馈共射：**

\[
I_{BQ}=\frac{V_{CC}-U_{BEQ}}{R_1+R_2+(1+\beta)R_3},\quad
I_{CQ}=\beta I_{BQ},\quad
U_{CEQ}=V_{CC}-(1+\beta)I_{BQ}R_3 .
\]

这里 \(R_3\) 中流过集电极电流与基极电流之和；公式假设晶体管处于放大区。

中频近似为
\[
A_u=-\frac{\beta(R_2\parallel R_3)}{r_{be}},\quad
R_i=r_{be}\parallel R_1,\quad
R_o=R_2\parallel R_3 .
\]

**(b) 分压偏置共基：**

先把基极分压网络化为戴维南源：
\[
V_{BB}=\frac{R_2}{R_2+R_3}V_{CC},\qquad
R_b=R_2\parallel R_3 .
\]
再求
\[
I_{BQ}=\frac{V_{BB}-U_{BEQ}}{R_b+(1+\beta)R_1},\quad
I_{CQ}=\beta I_{BQ},\quad
U_{CEQ}\approx V_{CC}-I_{CQ}(R_4+R_1).
\]

最后一式采用 \(I_E\approx I_C\) 的教材近似；若需保留有限基极电流，应将发射极压降写成 \(I_{EQ}R_1=(1+\beta)I_{BQ}R_1\)。小信号式还假设题图中的旁路电容在中频近似短路、忽略晶体管输出电阻。
其小信号近似：
\[
A_u=\frac{\beta R_4}{r_{be}},\quad
R_i=R_1\parallel\frac{r_{be}}{1+\beta},\quad
R_o=R_4 .
\]

使用这些表达式前先按题图确认电阻编号、输入/输出端和旁路电容状态；近似式忽略晶体管输出电阻等二阶影响。

### 2.4 图解 Q 点并比较带载摆幅

**原书定位：**AP P2.4，图与题干见 PDF p.79（印刷 p.70），负载线和题解同页；核图与数值复核见[P2.3–P2.4 原页复核](../sources/a02-ap-exercises-p2-3-4-audit.md)。

给定 \(V_{CC}=12\,\text{V}\)、\(R_C=3\,\text{k}\Omega\)、\(R_B=15\,\text{k}\Omega\)、\(V_{BB}=1\,\text{V}\)、\(\beta=100\)、\(U_{BEQ}=0.7\,\text{V}\)。

- 空载时 \(I_{BQ}=(1-0.7)/15\,\text{k}\Omega=20\,\mu\text{A}\)、\(I_{CQ}=2\,\text{mA}\)、\(U_{CEQ}=12-I_{CQ}R_C=6\,\text{V}\)。最大正弦输出峰值约 \(U_{CEQ}-U_{CES}\approx U_{CEQ}-U_{BEQ}=5.3\,\text{V}\)，有效值约 \(3.75\,\text{V}\)。
- \(R_L=3\,\text{k}\Omega\) 是**直流直连负载**，所以 Q 点也改变。将输出回路化为戴维南等效：\(V'_{CC}=6\,\text{V}\)、\(R'_C=R_C\parallel R_L=1.5\,\text{k}\Omega\)。新 Q 点约 \(I_{CQ}=2\,\text{mA}\)、\(U_{CEQ}=3\,\text{V}\)，输出峰值约 \(2.3\,\text{V}\)，有效值约 \(1.63\,\text{V}\)。

这里沿原书取 \(U_{CES}\approx U_{BEQ}=0.7\,\text{V}\)，属于本题的图解估算，不是所有晶体管的固定饱和压降。带载时截止侧余量为 \(I_{CQ}R'_C=3\,\text{V}\)，饱和侧余量约 \(U_{CEQ}-U_{CES}=2.3\,\text{V}\)，因此饱和侧先限制。不要把直连负载当作隔直电容后的纯交流负载；后一种情况才通常不改变静态 Q 点。

### 2.5 共射小信号判断

**原书定位：**AP 图 P2.5，印刷 pp.70–71 / PDF pp.79–80。题给 \(\beta=80\)、\(r_{be}=1\,\text{k}\Omega\)、\(U_i=20\,\text{mV}\)、静态 \(U_{BEQ}=0.7\,\text{V}\)、\(U_{CEQ}=4\,\text{V}\)、\(I_{BQ}=20\,\mu\text{A}\)；图中 \(R_B=510\,\text{k}\Omega\)、\(R_C=R_L=5\,\text{k}\Omega\)、\(R_s=2\,\text{k}\Omega\)。输入和输出均为电容耦合，发射极交流接地。见[P2.5/P2.7 原页审计](../sources/a02-ap-exercises-p2-5-7-audit.md)。

先从图和小信号定义求出比较基准：

\[
R_C'=R_C\parallel R_L=2.5\,\text{k}\Omega,\quad
A_u=-\frac{\beta R_C'}{r_{be}}=-200,
\]
\[
R_i=R_B\parallel r_{be}=510\,\text{k}\Omega\parallel1\,\text{k}\Omega\approx0.998\,\text{k}\Omega\approx1\,\text{k}\Omega,
\quad R_o\approx R_C=5\,\text{k}\Omega.
\]

这里 \(A_u=u_o/u_i\) 的 \(u_i\) 是放大器输入端电压；信号源电压为
\[
U_s=U_i\frac{R_s+R_i}{R_i}\approx20\,\text{mV}\times\frac{2+1}{1}=60\,\text{mV}.
\]

| 项 | 原书断言 | 判断 | 核对理由 |
|---:|---|:---:|---|
| 1 | \(A_u=-U_{CEQ}/U_i=-4/(20\,\text{mV})=-200\) | × | 数值碰巧等于正确增益，但 \(U_{CEQ}=4\,\text{V}\) 是静态管压降，不能当作动态输出 \(u_o\)。正确的 −200 来自 \(-\beta(R_C\parallel R_L)/r_{be}\)。 |
| 2 | \(A_u=-U_{CEQ}/U_{BEQ}=-4/0.7\approx-5.71\) | × | 静态端电压之比不是小信号电压增益；增益必须用交流增量和正确输入端口定义。 |
| 3 | \(A_u=-\beta R_C/r_{be}=-400\) | × | 漏掉电容耦合负载，算成空载增益；中频应使用 \(R_C\parallel R_L=2.5\,\text{k}\Omega\)。 |
| 4 | \(A_u=-\beta(R_C\parallel R_L)/r_{be}=-200\) | √ | 与图 P2.5 的中频小信号等效电路相符。 |
| 5 | \(R_i=U_i/I_{BQ}=20\,\text{mV}/20\,\mu\text{A}=1\,\text{k}\Omega\) | × | 数值近似正确但量错：静态基极电流 \(I_{BQ}\) 不是交流输入电流。按小信号图求 \(R_i=R_B\parallel r_{be}\approx1\,\text{k}\Omega\)。 |
| 6 | \(R_i=U_{BEQ}/I_{BQ}=0.7\,\text{V}/20\,\mu\text{A}=35\,\text{k}\Omega\) | × | 这是静态端电压/电流比，不是 Q 点附近的增量输入电阻。 |
| 7 | \(R_i\approx3\,\text{k}\Omega\) | × | 把 \(R_s+R_i\) 当成放大器自身输入电阻；\(R_s\) 属于信号源。 |
| 8 | \(R_i\approx1\,\text{k}\Omega\) | √ | 与 \(R_B\parallel r_{be}\approx0.998\,\text{k}\Omega\) 一致。 |
| 9 | \(R_o=5\,\text{k}\Omega\) | √ | 移去外负载并将输入信号置零后，忽略晶体管输出电阻，输出端看见 \(R_C\)。 |
| 10 | \(R_o=R_C\parallel R_L=2.5\,\text{k}\Omega\) | × | 求放大器输出电阻时应移去负载；把 \(R_L\) 留在端口内会把带载电阻误当作 \(R_o\)。 |
| 11 | \(U_s\approx20\,\text{mV}\) | × | 20 mV 是放大器输入端电压 \(U_i\)，不是信号源电压。 |
| 12 | \(U_s\approx60\,\text{mV}\) | √ | 计入 \(R_s=2\,\text{k}\Omega\) 与 \(R_i\approx1\,\text{k}\Omega\) 的分压后反算。 |

独立核对的判断序列为 **×、×、×、√、×、×、×、√、√、×、×、√**，与 AP 原答案一致。第 (1)、(5) 项尤其说明：数值碰巧相同不代表定义和推理正确。题面未注明 \(U_i=20\,\text{mV}\) 的峰值/有效值口径，也未给饱和边界；按同一幅值口径代入小信号增益会要求约 4 V 输出，而静态 \(U_{CEQ}=4\,\text{V}\)，因此不能把该线性外推当作未削顶波形预测。本题 12 项是在比较小信号增益/阻抗公式，不保证该输入下仍在线性区。

### 2.6 直流故障诊断

**原书定位：**AP P2.6，PDF p.80（印刷 p.71），图 P2.6 和六种故障题解；页图与独立复算见[P2.6/P2.8 原页记录](../sources/a02-ap-exercises-p2-6-8-audit.md)。令输入源直流分量为零；因此输入理想电压源短路，\(R_{b1}\) 成为基极到地的支路。题给 \(V_{CC}=15\,\text{V}\)、\(R_C=5.1\,\text{k}\Omega\)、\(R_{b1}=4.3\,\text{k}\Omega\)、\(R_{b2}=82\,\text{k}\Omega\)、\(\beta=120\)、\(U_{BE}=0.7\,\text{V}\)、\(U_{CES}=0.5\,\text{V}\)。

正常时两条偏置支路电流相减，不能把 \(R_{b1}\) 当成开路：
\[
I_{BQ}=\frac{V_{CC}-U_{BE}}{R_{b2}}-\frac{U_{BE}}{R_{b1}}
\approx11.60\,\mu\text{A},\qquad
I_{CQ}\approx\beta I_{BQ}=1.392\,\text{mA},
\]
\[
U_C=V_{CC}-I_{CQ}R_C\approx7.90\,\text{V}.
\]

| 情况 | 电流通路与工作区判断 | 集电极电位 \(U_C\) |
|---|---|---:|
| 正常 | \(I_{BQ}\approx11.60\,\mu\text{A}\)、\(I_C\approx1.392\,\text{mA}\)，处于放大区 | 约 7.90 V |
| \(R_{b1}\) 短路 | 基极被拉到地，\(U_{BE}\approx0\)，晶体管截止 | 15 V |
| \(R_{b1}\) 开路 | \(I_B=(15-0.7)/82\,\text{k}\Omega\approx0.1744\,\text{mA}\)；临界饱和基极电流 \((15-0.5)/(120\cdot5.1\,\text{k}\Omega)\approx23.7\,\mu\text{A}\)，故进入饱和 | 0.5 V |
| \(R_{b2}\) 开路 | 正向基极供电支路断开，\(R_{b1}\) 将基极接到已置零的输入端，晶体管截止 | 15 V |
| \(R_{b2}\) 短路 | 基极被直接接到 \(+15\,\text{V}\)，\(U_{BE}\) 超限并可能损坏；题解按 b–e 烧断/烧短的简化故障结果估为约 15 V | 约 15 V* |
| \(R_C\) 短路 | 集电极直接接到 \(+V_{CC}\) | 15 V |

此题用集电极电位区分截止、放大和饱和。*“损坏后约 15 V”沿用原书对烧毁模式并忽略集电结反向电流的估计，不是器件损坏后可普遍预测的读数。

### 2.7 共射空载与带载

**原书定位：**图 P2.7，印刷 pp.71–72 / PDF pp.80–81。给定 \(V_{CC}=15\,\text{V}\)、\(R_B=56\,\text{k}\Omega\)、\(R_s=3\,\text{k}\Omega\)、\(R_C=5\,\text{k}\Omega\)、\(\beta=80\)、\(r_{bb'}=100\,\Omega\)、\(U_{BEQ}=0.7\,\text{V}\)。分别比较空载与 \(R_L=3\,\text{k}\Omega\) **直连**集电极的情况。原页/独立复算见[P2.5/P2.7 审计](../sources/a02-ap-exercises-p2-5-7-audit.md)。

直流分析时将理想信号源 \(u_s\) 置零（短路），但保留串联内阻 \(R_s\)。由于输入端直连，\(R_s\) 成为基极到地的直流支路，故

\[
I_{BQ}=\frac{V_{CC}-U_{BEQ}}{R_B}-\frac{U_{BEQ}}{R_s}
=\frac{14.3}{56\,\text{k}\Omega}-\frac{0.7}{3\,\text{k}\Omega}
\approx22.0\,\mu\text{A},\quad I_{CQ}\approx1.762\,\text{mA}.
\]

空载时 \(U_{CEQ}=V_{CC}-I_{CQ}R_C\approx6.19\,\text{V}\)。按教材近似
\[
r_{be}\approx r_{bb'}+\frac{\beta U_T}{I_{CQ}}
\approx100\,\Omega+\frac{80\times26\,\text{mV}}{1.762\,\text{mA}}
\approx1.28\,\text{k}\Omega\approx1.3\,\text{k}\Omega.
\]

接入直连负载后，把集电极回路作戴维南变换：
\[
V'_{CC}=V_{CC}\frac{R_L}{R_C+R_L}=5.625\,\text{V},\qquad
R'_C=R_C\parallel R_L=1.875\,\text{k}\Omega.
\]
基极偏置没有改变，所以 \(I_{CQ}\) 与 \(r_{be}\) 近似不变，但
\[
U_{CEQ}=V'_{CC}-I_{CQ}R'_C\approx2.32\,\text{V}.
\]

| 状态 | Q 点 | \(r_{be}\) | \(A_u\) | \(R_i\) | \(R_o\) |
|---|---|---:|---:|---:|---:|
| 空载 | \(I_{BQ}\approx22.0\,\mu\text{A}\)、\(I_{CQ}\approx1.762\,\text{mA}\)、\(U_{CEQ}\approx6.19\,\text{V}\) | 精算约 1.28 kΩ（教材取 1.3 kΩ） | 精算约 −312（教材约 −308） | \(R_B\parallel r_{be}\approx1.25\,\text{k}\Omega\)（教材近似 1.3 kΩ） | 约 5 kΩ |
| \(R_L=3\,\text{k}\Omega\) 直连 | \(I_{CQ}\approx1.762\,\text{mA}\)、\(U_{CEQ}\approx2.32\,\text{V}\) | 近似不变 | 精算约 −117（教材约 −115） | 近似不变 | 约 5 kΩ |

电压增益按放大器输入端电压定义：空载用 \(-\beta R_C/r_{be}\)，带载用 \(-\beta R'_C/r_{be}\)。输出电阻在移去外接负载后求，故近似仍为 \(R_C\)，不把 \(R_L\) 并入 \(R_o\)。教材答案用 \(r_{be}\approx1.3\,\text{k}\Omega\) 的圆整值，故表内同时保留原书约数与按未圆整参数的复算值；两者差异属于中间量取位，不是原书答案冲突。

### 2.8 NPN 换为 PNP

**原书定位：**AP P2.8，PDF p.81（印刷 p.72），文字题与解答；接线参照同页的 P2.7 图，原页/复算记录见[P2.6/P2.8 审核](../sources/a02-ap-exercises-p2-6-8-audit.md)。将 NPN 共射改为 PNP 并保持参数绝对值不变时，应反转直流电源极性。按 P2.7 的输入源置零条件，
\[
|I_{BQ}|=\frac{|V_{CC}|-|U_{BEQ}|}{R_B}-\frac{|U_{BEQ}|}{R_s}
\approx22\,\mu\text{A},\qquad
|I_{CQ}|\approx1.76\,\text{mA},\qquad
|U_{CEQ}|\approx6.2\,\text{V}.
\]
因此 Q 点各量的幅值、\(A_u\)、\(R_i\)、\(R_o\) 在相同小信号参数近似下不变；按 \(U_{BE}=U_B-U_E\)、\(U_{CE}=U_C-U_E\) 定义，PNP 的 \(U_{BEQ}\)、\(U_{CEQ}\) 极性反向，共射仍反相。

原书指出，PNP 输出底部削顶对应截止失真。减小 \(R_B\) 会增大偏置电流幅值、提高静态 \(I_C\)，把 Q 点移离截止边界；这是按 P2.7 电路与负电源极性反接条件得到的修正方向。调整后仍应复核饱和余量和最大摆幅。

### 2.9 共射增益指标反推

**原书定位：** AP 习题 P2.9，图 P2.9 在 PDF p.81（印刷 p.72），题解续于 PDF p.82（印刷 p.73）。电路为固定偏置共射，图示 \(V_{CC}=12\,\text{V}\)、\(R_C=3\,\text{k}\Omega\)；给定 \(\beta=100\)、\(r_{be}=1\,\text{k}\Omega\)。见[原页与计算核查](../sources/a02-ap-exercises-p2-9-10-audit.md)。

（1）由 \(U_{CEQ}=6\,\text{V}\) 得
\[
I_{CQ}=\frac{V_{CC}-U_{CEQ}}{R_C}
=\frac{12-6}{3\,\text{k}\Omega}=2\,\text{mA},\qquad
I_{BQ}\approx\frac{I_{CQ}}{\beta}=20\,\mu\text{A}.
\]
按 \(U_{BEQ}\approx0.7\,\text{V}\)，固定偏置电阻为
  \[
R_B=\frac{V_{CC}-U_{BEQ}}{I_{BQ}}
=\frac{12-0.7}{20\,\mu\text{A}}\approx565\,\text{k}\Omega.
  \]

（2）保持 \(R_B\) 不变，题给 \(R_L=5\,\text{k}\Omega\)，并要求放大器输入 \(U_i=1\,\text{mV}_{\rm rms}\) 时输出 \(U_o>200\,\text{mV}_{\rm rms}\)，故需 \(|A_u|>200\)。采用题给 \(r_{be}=1\,\text{k}\Omega\)：
\[
|A_u|\approx\frac{\beta(R_C\parallel R_L)}{r_{be}}>200
\quad\Longrightarrow\quad
R_C\parallel5\,\text{k}\Omega>2\,\text{k}\Omega
\quad\Longrightarrow\quad
R_C>\frac{10}{3}\,\text{k}\Omega\approx3.33\,\text{k}\Omega.
\]
由于要求严格大于 \(200\,\text{mV}\)，恰取 \(R_C=3.33\,\text{k}\Omega\) 只到边界；实际选值应高于精确阈值 \(10/3\,\text{k}\Omega\)。线性增益下同频输入、输出的有效值比等于电压增益幅值比。P2.9 未给饱和边界电压，故增益门槛本身不能证明任意选值下的无失真摆幅；选定 \(R_C\) 后应按器件模型回算 Q 点和交流余量，避免选值过大导致饱和侧余量不足。

### 2.10 最大不失真输出

**原书定位：** AP 习题 P2.10，PDF p.82（印刷 p.73）；电路沿用图 P2.9（PDF p.81，印刷 p.72）。题给 \(I_{CQ}=2\,\text{mA}\)、\(\beta=100\)、\(U_{CES}=0.6\,\text{V}\)，图 P2.9 给出 \(V_{CC}=12\,\text{V}\)、\(R_C=3\,\text{k}\Omega\)；P2.10 接入经电容耦合的 \(R_L=3\,\text{k}\Omega\)。见[原页与计算核查](../sources/a02-ap-exercises-p2-9-10-audit.md)。

耦合电容隔断直流，因此接入 \(R_L\) 不改变初始 Q 点；交流负载为
\[
R'_L=R_C\parallel R_L=1.5\,\text{k}\Omega,
\qquad U_{CEQ}=V_{CC}-I_{CQ}R_C=6\,\text{V}.
\]
截止侧峰值余量是 \(I_{CQ}R'_L=3\,\text{V}\)，饱和侧余量是 \(U_{CEQ}-U_{CES}=5.4\,\text{V}\)，所以截止侧先限制输出。原书按有效值报告最大不失真输出：
\[
U_{o,\mathrm{rms,max}}=\frac{I_{CQ}R'_L}{\sqrt2}
=\frac{3}{\sqrt2}\approx2.12\,\text{V}
\]
（对应峰值约 \(3\,\text{V}\)）。

若调节固定偏置电阻 \(R_B\) 以最大化正弦输出，应使截止和饱和两侧余量相等：
\[
I_{CQ}R'_L=U_{CEQ}-U_{CES},\qquad U_{CEQ}=V_{CC}-I_{CQ}R_C .
\]
因此
\[
I_{CQ}=\frac{V_{CC}-U_{CES}}{R_C+R'_L}
=\frac{12-0.6}{3\,\text{k}\Omega+1.5\,\text{k}\Omega}
\approx2.533\,\text{mA}.
\]
按题解采用 \(I_{BQ}=I_{CQ}/\beta\) 和 \(U_{BEQ}\approx0.7\,\text{V}\)，得到
\[
I_{BQ}\approx25.33\,\mu\text{A},\qquad
R_B=\frac{V_{CC}-U_{BEQ}}{I_{BQ}}
\approx446\,\text{k}\Omega\approx447\,\text{k}\Omega.
\]
新 Q 点 \(U_{CEQ}\approx4.40\,\text{V}\)，两侧余量均约 \(3.80\,\text{V}\)，故
\[
U_{o,\mathrm{rms,max}}\approx\frac{3.80}{\sqrt2}
\approx2.69\,\text{V}
\]
（原书约 \(2.68\,\text{V}\)，差异来自中间量取位）。这道题的 \(U_{om}\) 按原书公式是有效值；不要把 \(I_{CQ}R'_L\) 的峰值直接当成该答案。若负载改为直流直连，必须把负载重新纳入直流 Q 点计算。

### 2.11 分压偏置、未旁路反馈与电容开路

**原书定位：** AP 习题 P2.11，PDF pp.82–83（印刷 pp.73–74）。图中 \(R_{b2}=25\,\text{k}\Omega\) 接 \(V_{CC}\)，\(R_{b1}=5\,\text{k}\Omega\) 接地；\(R_C=R_L=5\,\text{k}\Omega\)，\(R_f=300\,\Omega\) 不旁路，\(R_e=1\,\text{k}\Omega\) 由 \(C_e\) 旁路，\(\beta=100\)、\(r_{bb'}=100\,\Omega\)、\(V_{CC}=12\,\text{V}\)。原页与复算见[P2.11/P2.12 审计](../sources/a02-ap-exercises-p2-11-12-audit.md)。

**直流 Q 点：** \(C_e\) 开路，发射极直流电阻为 \(R_f+R_e=1.3\,\text{k}\Omega\)。分压网络的戴维南等效为
\[
V_{th}=12\frac{5}{25+5}=2\,\text{V},\qquad
R_{th}=25\,\text{k}\Omega\parallel5\,\text{k}\Omega=4.167\,\text{k}\Omega.
\]
教材用 \((1+\beta)(R_f+R_e)\gg R_{th}\) 的近似，取 \(V_B\approx2\,\text{V}\)、\(I_E\approx1\,\text{mA}\)、\(I_B\approx10\,\mu\text{A}\)、\(U_{CEQ}\approx5.7\,\text{V}\)。按题解取 \(U_{BE}\approx0.7\,\text{V}\)，用完整戴维南基极方程复算有限分压负载：
\[
I_B=\frac{V_{th}-U_{BE}}{R_{th}+(1+\beta)(R_f+R_e)}
\approx9.60\,\mu\text{A},\quad
I_E=(1+\beta)I_B\approx0.969\,\text{mA},\quad
I_C=\beta I_B\approx0.960\,\text{mA}.
\]
于是 \(U_{CEQ}=V_{CC}-I_CR_C-I_E(R_f+R_e)\approx5.94\,\text{V}\)。这与教材 5.7 V 的差别来自教材先把分压视为理想、再用 \(I_E\) 近似 \(I_C\)；两种方法都显示电路处于放大区，后续应保持所用近似一致。

**\(C_e\) 正常旁路时的中频参数：** 交流负载 \(R'_L=R_C\parallel R_L=2.5\,\text{k}\Omega\)，发射极只保留未旁路的 \(R_f\)。按完整直流复算的 \(I_E\)，
\[
r_{be}\approx r_{bb'}+\frac{(1+\beta)U_T}{I_E}
\approx2.81\,\text{k}\Omega
\]
其中取室温 \(U_T=26\,\text{mV}\)；教材用 \(I_E\approx1\,\text{mA}\) 得 \(r_{be}\approx2.73\,\text{k}\Omega\)。因此
\[
A_u\approx-\frac{\beta R'_L}{r_{be}+(1+\beta)R_f}
\approx-7.55,\qquad
R_i=R_{b1}\parallel R_{b2}\parallel[r_{be}+(1+\beta)R_f]
\approx3.70\,\text{k}\Omega.
\]
教材值为 \(A_u\approx-7.6\)、\(R_i\approx3.7\,\text{k}\Omega\)。移去负载、将输入置零并忽略晶体管 \(r_o\) 后，\(R_o\approx R_C=5\,\text{k}\Omega\)。

**把 \(\beta\) 改为 200：** 完整分压方程给出 \(I_B\approx4.90\,\mu\text{A}\)、\(I_E\approx0.984\,\text{mA}\)、\(I_C\approx0.979\,\text{mA}\)、\(U_{CEQ}\approx5.82\,\text{V}\)。相对 \(\beta=100\) 时电流变化很小，符合教材“Q 点基本不变、基极电流约减半”的近似描述。

**\(C_e\) 开路：** 直流 Q 点不变；交流时 \(R_e\) 也不再旁路，发射极总退化电阻变为 \(R_f+R_e=1.3\,\text{k}\Omega\)。完整小信号式给出
\[
R_i=R_{b1}\parallel R_{b2}\parallel[r_{be}+(1+\beta)(R_f+R_e)]
\approx4.04\,\text{k}\Omega\approx4.1\,\text{k}\Omega,
\]
\[
A_u\approx-\frac{\beta R'_L}{r_{be}+(1+\beta)(R_f+R_e)}
\approx-1.86.
\]
原书用强退化近似 \(A_u\approx-R'_L/(R_f+R_e)\approx-1.92\)，忽略了 \(r_{be}/\beta\) 项；约 3% 的差异是近似层级不同。\(R_i\) 只从约 \(3.70\,\text{k}\Omega\) 升至 \(4.04\,\text{k}\Omega\)，因为输入端还并联着 \(R_{b1}\parallel R_{b2}=4.167\,\text{k}\Omega\)；而增益明显下降。忽略 \(r_o\) 时 \(R_o\) 仍约 \(5\,\text{k}\Omega\)。

### 2.12 共集电路

**原书定位：** AP 习题 P2.12，题图在 PDF p.83（印刷 p.74），解答在 PDF p.84（印刷 p.75）。参数为 \(\beta=80\)、题给 \(r_{be}=1\,\text{k}\Omega\)、\(V_{CC}=15\,\text{V}\)、\(R_B=200\,\text{k}\Omega\)、\(R_E=3\,\text{k}\Omega\)、\(R_s=2\,\text{k}\Omega\)。输入、输出都经电容耦合，负载比较 \(R_L=\infty\) 和 \(R_L=3\,\text{k}\Omega\)。原页与复算见[P2.11/P2.12 审计](../sources/a02-ap-exercises-p2-11-12-audit.md)。

**直流 Q 点：** 耦合电容隔断信号源和负载的直流通路。按 \(U_{BEQ}\approx0.7\,\text{V}\)，
\[
I_{BQ}=\frac{V_{CC}-U_{BEQ}}{R_B+(1+\beta)R_E}
=\frac{14.3}{200\,\text{k}\Omega+81(3\,\text{k}\Omega)}
\approx32.28\,\mu\text{A},
\]
\[
I_{EQ}=(1+\beta)I_{BQ}\approx2.614\,\text{mA},\quad
I_{CQ}=\beta I_{BQ}\approx2.582\,\text{mA},\quad
U_{CEQ}=V_{CC}-I_{EQ}R_E\approx7.16\,\text{V}.
\]
教材圆整为 \(I_{BQ}\approx32.3\,\mu\text{A}\)、\(I_{EQ}\approx2.62\,\text{mA}\)、\(U_{CEQ}\approx7.14\,\text{V}\)。中频计算沿用题给 \(r_{be}=1\,\text{k}\Omega\)，不再由 Q 点反推该参数。

**输入电阻和电压增益：** 共集射极交流负载为 \(R'_E=R_E\parallel R_L\)。输入电阻是在放大器输入端测量，不包含信号源 \(R_s\)：
\[
R_i=R_B\parallel[r_{be}+(1+\beta)R'_E],\qquad
A_u=\frac{(1+\beta)R'_E}{r_{be}+(1+\beta)R'_E}.
\]

| 负载 | \(R'_E\) | \(R_i\) | \(A_u=u_o/u_i\) |
|---|---:|---:|---:|
| \(R_L=\infty\) | \(3\,\text{k}\Omega\) | \(200\,\text{k}\Omega\parallel244\,\text{k}\Omega\approx110\,\text{k}\Omega\) | \(243/244\approx0.996\) |
| \(R_L=3\,\text{k}\Omega\) | \(1.5\,\text{k}\Omega\) | \(200\,\text{k}\Omega\parallel122.5\,\text{k}\Omega=76\,\text{k}\Omega\) | \(121.5/122.5\approx0.992\) |

带载后 \(R_E'\) 下降，所以输入电阻下降，电压增益仍接近 1 且不反相；不能把信号源内阻并入 \(R_i\) 或误当成共射增益。

**输出电阻：** 求 \(R_o\) 时移去 \(R_L\)，并将理想电压信号源置零；此时基极到交流地的电阻为 \(R_s\parallel R_B\)。忽略晶体管 \(r_o\)：
\[
R_o=R_E\parallel\frac{r_{be}+(R_s\parallel R_B)}{1+\beta}
=3\,\text{k}\Omega\parallel
\frac{1\,\text{k}\Omega+(2\,\text{k}\Omega\parallel200\,\text{k}\Omega)}{81}
\approx36.4\,\Omega\approx37\,\Omega.
\]
因此，置零后的基极交流回路必须保留 \(R_s\parallel R_B\)。若只漏掉 \(R_s\) 但仍保留 \(R_B\)，按同一模型会得到约 \(1.36\,\text{k}\Omega\)；约 \(12.3\,\Omega\) 对应的是把基极错误地视作理想交流地、同时忽略基极到地电阻。原书公式保留 \(R_s\parallel R_B\)，结果约 \(36.4\,\Omega\)。同一放大器的 \(R_o\) 不随外接 \(R_L\) 改变，前提是按定义先移去负载再测量。

### 2.13 共射带载与发射极旁路失效

**原书定位：** AP 习题 P2.13，题图在 PDF p.84（印刷 p.75），解答续于 PDF p.85（印刷 p.76）。参数为 \(\beta=60\)、\(r_{bb'}=100\,\Omega\)、\(V_{CC}=12\,\text{V}\)、\(R_B=300\,\text{k}\Omega\)、\(R_C=3\,\text{k}\Omega\)、\(R_E=1\,\text{k}\Omega\)（正常时由 \(C_3\) 旁路）、\(R_L=3\,\text{k}\Omega\)、\(R_s=2\,\text{k}\Omega\)。原页与独立复算见[P2.13–P2.16 审计](../sources/a02-ap-exercises-p2-13-16-audit.md)。

**直流 Q 点：** 输入/输出耦合电容在直流下开路；\(C_3\) 在直流下也开路，所以正常和故障两种状态的 Q 点相同。取 \(U_{BEQ}=0.7\,\text{V}\)：
\[
I_{BQ}=\frac{V_{CC}-U_{BEQ}}{R_B+(1+\beta)R_E}
=\frac{11.3}{300\,\text{k}\Omega+61(1\,\text{k}\Omega)}
\approx31.30\,\mu\text{A},
\]
\[
I_{CQ}=\beta I_{BQ}\approx1.878\,\text{mA},\qquad
I_{EQ}=(1+\beta)I_{BQ}\approx1.909\,\text{mA},
\]
\[
U_{CEQ}=V_{CC}-I_{CQ}R_C-I_{EQ}R_E\approx4.46\,\text{V}.
\]
AP 报 \(I_{CQ}\approx1.86\,\text{mA}\)、\(U_{CEQ}\approx4.56\,\text{V}\)，按其大 \(\beta\) 近似 \(I_E\approx I_C\) 并用圆整电流可得该值。此处保留有限 \(\beta\) 的支路电流后，Q 点约为 \(4.46\,\text{V}\)，不是另一个电路状态。

**\(C_3\) 正常旁路：** 中频时 \(R_E\) 被旁路，\(R'_L=R_C\parallel R_L=1.5\,\text{k}\Omega\)。由精算 \(I_E\) 得
\[
r_{be}=r_{bb'}+\frac{(1+\beta)U_T}{I_E}
\approx930.6\,\Omega
\]
（教材用圆整电流得约 \(939\,\Omega\)）。按 \(u_i\) 为放大器输入端电压：
\[
R_i=R_B\parallel r_{be}\approx928\,\Omega,\qquad
A_u=-\frac{\beta R'_L}{r_{be}}\approx-96.7,\qquad
R_o\approx R_C=3\,\text{k}\Omega.
\]
教材将 \(R_B\gg r_{be}\) 近似为 \(R_i\approx r_{be}\approx939\,\Omega\)，并给 \(A_u\approx-96\)。当 \(U_s=10\,\text{mV}_{\rm rms}\) 时，还要经过 \(R_s\) 与 \(R_i\) 的分压：
\[
U_i=U_s\frac{R_i}{R_s+R_i}\approx3.17\,\text{mV}_{\rm rms},\qquad
U_o=|A_u|U_i\approx306\,\text{mV}_{\rm rms}.
\]
按教材圆整约为 \(U_i=3.2\,\text{mV}\)、\(U_o=307\,\text{mV}\)。不能把 \(U_s\) 直接当成 \(U_i\)。

**\(C_3\) 开路：** 直流 Q 点不变；中频交流时 \(R_E\) 不再旁路，发射极退化增大：
\[
R_i=R_B\parallel[r_{be}+(1+\beta)R_E]\approx51.33\,\text{k}\Omega,
\]
\[
A_u=-\frac{\beta R'_L}{r_{be}+(1+\beta)R_E}\approx-1.45.
\]
教材用强退化近似 \(A_u\approx-R'_L/R_E=-1.5\)。源分压后
\[
U_i=U_s\frac{R_i}{R_s+R_i}\approx9.63\,\text{mV}_{\rm rms},\qquad
U_o=|A_u|U_i\approx14.0\,\text{mV}_{\rm rms}.
\]
教材按 \(A_u\approx-1.5\) 报 \(U_o\approx14.4\,\text{mV}\)。\(R_i\) 大幅增加，使输入端分到的信号从约 \(3.2\) mV 增至 \(9.6\) mV；但闭环式发射极退化让增益下降，输出仍从约 \(307\) mV 降至约 \(14\) mV。忽略 \(r_o\) 时 \(R_o\) 仍约 \(R_C\)，旁路电容故障不改变直流偏置。

### 2.14 修正三个共源 FET 电路

**原书定位：** AP 习题 P2.14，原图和题解见 PDF pp.85–86（印刷 pp.76–77）。题目要求保留共源接法，让三种电路都具备放大正弦电压的条件；原图、改正图与极性核查见[P2.13–P2.16 审计](../sources/a02-ap-exercises-p2-13-16-audit.md)。

| 电路 | 原图问题 | 修正与工作原理 |
|---|---|---|
| (a) N 沟道常导通器件 | 栅极直流电位约为 0，源极也直接接地，静态 \(U_{GSQ}\approx0\)；输入正向摆动可能使栅—源结正偏。 | 在源极串入 \(R_S\)，使 \(U_{GSQ}\approx-I_D R_S<0\)，并选择 \(R_S\) 使 Q 点仍在导通区；漏极保留 \(R_D\)，输出取漏极，保持共源。 |
| (b) N 沟道自偏置器件 | 漏极直接连电源，漏极电流变化没有电阻转成输出电压；输入缺少隔直，信号源若带直流偏置可能扰动栅极工作点。 | 漏极串入 \(R_D\)，使 \(\Delta i_D\) 转成 \(\Delta u_D\)；保留源极自偏置电阻和栅极泄放电阻，并按原书解图在输入端加耦合电容。解图采用未旁路的 \(R_S\)；源极旁路电容只影响交流增益，不是建立直流自偏置的必要条件。 |
| (c) P 沟道增强型 MOS | 正电源极性与所需的 P 沟道电流方向/栅源偏置相反。 | 把漏极电源改为 \(-V_{DD}\)，栅极偏置支路接负电源，使 \(V_G<V_S\)、\(U_{GS}<0\) 并达到增强导通所需的负偏置；输出仍取漏极，保持共源。原书文字称栅极支路加 \(-V_{CC}\)，解图标为 \(V_{GG}\)；名称虽不同，关键是该偏置必须为负，具体幅值需按器件阈值选取。 |

三图都要保留完整的漏极电流通路和漏极负载，输入/输出耦合电容按需要隔直；偏置电源极性必须从器件类型和 \(U_{GS}\) 条件推出。不能只看“共源”接法名称照搬 N 沟道电源极性。

### 2.15 由 FET 特性曲线求 Q 点和小信号参数

**原书定位：** AP 习题 P2.15，题图和解答见 PDF pp.86–87（印刷 pp.77–78）。图中 \(V_{DD}=10\,\text{V}\)、\(R_D=5\,\text{k}\Omega\)、\(R_S=2\,\text{k}\Omega\)、\(R_G=1\,\text{M}\Omega\)，\(C_3\) 旁路 \(R_S\)；转移曲线约给 \(I_{DSS}=4\,\text{mA}\)、\(U_{GS(off)}=-4\,\text{V}\)。曲线交点和参数复算见[P2.13–P2.16 审计](../sources/a02-ap-exercises-p2-13-16-audit.md)。

直流时 \(C_3\) 开路，栅极经 \(R_G\) 接地，故自偏压线为 \(U_{GS}=-I_D R_S\)。它与转移特性的交点给出
\[
I_{DQ}\approx1\,\text{mA},\quad U_{GSQ}\approx-2\,\text{V},\quad U_{DSQ}\approx3\,\text{V}.
\]
再用直流负载线检查输出特性：
\[
U_{DS}=V_{DD}-I_D(R_D+R_S).
\]
端点为 \(I_D=0\) 时 \(U_{DS}=10\,\text{V}\)，以及 \(U_{DS}=0\) 时 \(I_D=10/(5+2)\,\text{k}\Omega\approx1.43\,\text{mA}\)；与 \(U_{GS}\approx-2\,\text{V}\) 输出曲线交于约 \(I_D=1\,\text{mA},U_{DS}=3\,\text{V}\)，与转移曲线求得的 Q 点吻合。

中频时假设 \(C_3\) 近似短路，交流源极接地，且输出无外接负载、忽略晶体管 \(r_o\)。由平方律转移曲线在 Q 点的斜率，
\[
g_m\approx\frac{2\sqrt{I_{DSS}I_{DQ}}}{|U_{GS(off)}|}
=\frac{2\sqrt{4\,\text{mA}\cdot1\,\text{mA}}}{4\,\text{V}}
\approx1\,\text{mS}.
\]
于是 \(A_u\approx-g_mR_D\approx-5\)、\(R_i\approx R_G=1\,\text{M}\Omega\)、\(R_o\approx R_D=5\,\text{k}\Omega\)。这些是图解读数与中频近似，不应报告过多有效位；若 \(C_3\) 未能充分旁路，增益将低于此值。

### 2.16 增强型 NMOS 的转移特性、增益和原书算术核查

**原书定位：** AP 习题 P2.16，题图与题解见 PDF p.88（印刷 p.79）。图给 \(V_{DD}=15\,\text{V}\)、\(R_D=6.2\,\text{k}\Omega\)、源极接地、栅极直流电压 \(V_{GG}=3\,\text{V}\)；转移曲线约有 \(U_{GS(th)}=2\,\text{V}\)、\(I_{D0}=4\,\text{mA}\)，且 \(U_{GS}=3\,\text{V}\) 时 \(I_D=1\,\text{mA}\)。原页算术错误和模型条件见[P2.13–P2.16 审计](../sources/a02-ap-exercises-p2-13-16-audit.md)。

初始 Q 点为 \(U_{GSQ}=3\,\text{V}\)、\(I_{DQ}=1\,\text{mA}\)。按平方律，
\[
g_m\approx\frac{2}{U_{GS(th)}}\sqrt{I_{DQ}I_{D0}}
=\frac{2}{2\,\text{V}}\sqrt{1\,\text{mA}\cdot4\,\text{mA}}
=2\,\text{mS},
\qquad A_u\approx-g_mR_D=-12.4.
\]

**原书题解的算术错误：** 原书把 \(U_{DSQ}=V_{DD}-I_{DQ}R_D\) 写成 \(5\,\text{V}\)，但图示的三个数直接给出
\[
U_{DSQ}=15-(1\,\text{mA})(6.2\,\text{k}\Omega)=8.8\,\text{V}.
\]
因此保留原书 5 V 作为勘误记录，采用按图参数计算的 \(8.8\,\text{V}\)。初始过驱动电压为 \(U_{GSQ}-U_{GS(th)}=1\,\text{V}\)，\(U_{DSQ}=8.8\,\text{V}\) 满足增强型 NMOS 饱和区条件。

若要求 \(|A_u|=15\)，在 \(R_D\) 不变且忽略负载、沟道长度调制时，
\[
g_m=\frac{15}{6.2\,\text{k}\Omega}\approx2.419\,\text{mS},\qquad
I_{DQ}=\frac{[g_mU_{GS(th)}/2]^2}{I_{D0}}
\approx1.463\,\text{mA}.
\]
平方律反解得
\[
U_{GSQ}=U_{GS(th)}+U_{GS(th)}\sqrt{\frac{I_{DQ}}{I_{D0}}}
\approx3.21\,\text{V},
\]
即应提高栅极静态电压。相应 \(U_{DSQ}=15-(1.463\,\text{mA})(6.2\,\text{k}\Omega)\approx5.93\,\text{V}\)，仍大于过驱动电压约 \(1.21\,\text{V}\)，工作区假设成立。

### 2.17 共源失真、增益和输入电阻的调节方向

原页：AP PDF p.88（印刷 p.79，题图），题解在 PDF p.89（印刷 p.80）；页图与端子关系见[原页核对记录](../sources/a02-ap-exercises-pages-71-80-audit.md)。图中 \(R_1,R_2\) 构成栅极分压，\(R_3\) 把分压中点接到栅极。FET 栅极直流电流近似为零，故 \(R_3\) 上直流压降近似为零：

\[
U_{GQ}\approx V_{DD}\frac{R_2}{R_1+R_2},\qquad
U_{GSQ}=U_{GQ}-I_{DQ}R_S.
\]

在本题器件的单调转移特性和原书偏置假设下，降低 \(R_1\)、增大 \(R_2\) 会提高 \(U_{GQ}\)；增大 \(R_S\) 会增强自偏置负反馈、降低 \(I_{DQ}\)。漏极对地静态电压为 \(V_{D,Q}=V_{DD}-I_{DQ}R_D\)，而管压降还要扣除源极电压 \(I_{DQ}R_S\)。共源级输入增大时漏极电流上升、漏极电压下降，因此底部削顶对应的余量不足与顶部削顶对应的截止余量不足，应通过移动 Q 点分别修正。原书给出的方向为：

- 输出底部失真：增大 \(R_1\)、\(R_S\)，或减小 \(R_2\)、\(R_D\)。
- 输出顶部失真：减小 \(R_1\)、\(R_S\)，或增大 \(R_2\)。
- 增大 \(|A_u|\)：可通过减小 \(R_1\)、减小 \(R_S\)、增大 \(R_2\) 来提高 \(I_{DQ}\) 和 \(g_m\)，或直接增大 \(R_D\)。
- 中频、\(C_S\) 充分旁路且忽略 \(r_o\) 时，栅极到输出的增益约为 \(A_{u,g}\approx-g_m(R_D\parallel R_L)\)；增大 \(R_D\) 也会移动直流 Q 点，不能只按增益决定。
- 忽略栅极电流时，输入电阻约为 \(R_i\approx R_3+(R_1\parallel R_2)\)。因此提高 \(R_1\)、\(R_2\)、\(R_3\) 中一个或多个，可提高该偏置/输入网络的电阻；若信号源内阻不可忽略，源到输出增益还要乘输入分压因子 \(R_i/(R_{\text{src}}+R_i)\)。

这些是题目假设下的调节趋势，不保证同时满足摆幅、增益和输入电阻指标。每次改值后重新求 \(U_{GSQ}\)、\(I_{DQ}\)、\(U_{DSQ}\)，检查截止/饱和边界、负载摆幅和信号源加载。

### 2.18 判断两管组合能否构成复合管

原页：AP PDF p.89（印刷 p.80，图和解答）。按图中从左到右把两只管记为 \(T_1,T_2\)。判据是：外加合适电压后，控制端应能建立工作状态，且 \(T_1\) 的主电流通路必须经 \(T_2\) 或公共端闭合；FET 绝缘栅不能替相邻双极型管提供集电极/发射极或漏极/源极电流通路。

| 图 | 可构成复合管 | 等效类型与端子（上 / 中 / 下），或不成立原因 |
|---|---|---|
| (a) | 否 | \(T_1\) 缺少集电极电流通路 |
| (b) | 否 | \(T_2\) 为 MOS 管，绝缘栅使 \(T_1\) 的集电极—发射极通路断开 |
| (c) | 是 | NPN；集电极 / 基极 / 发射极 |
| (d) | 否 | \(T_1\) 缺少集电极电流通路 |
| (e) | 否 | \(T_2\) 的栅源绝缘使 \(T_1\) 的漏极—源极通路断开 |
| (f) | 是 | PNP；发射极 / 基极 / 集电极 |
| (g) | 是 | NPN；集电极 / 基极 / 发射极 |

类型与端子方向按原图符号、箭头和连线判定；以上结论只适用于题图所示组合，不应推广成任意两管串接规则。

## 三、跨题可复用的解题顺序

1. 先按题图和电容状态分别画直流、交流等效图；辨明负载是直连还是电容耦合。
2. 求 Q 点并检查截止、放大/恒流、饱和边界；故障题逐种重建电流通路。
3. 需要曲线时先图解读数，再用电路方程回代；需要中频增益/阻抗时再换小信号模型。
4. 计算最大正弦摆幅时比较截止和饱和两个方向，输出若要求有效值再除以 \(\sqrt{2}\)。
5. 分别核对输入源内阻、负载、相位、单位和器件区域；更改偏置后重新检查 Q 点。

## 四、来源边界与未覆盖项

- P2.11 的分压偏置/旁路电容边界与 P2.12 的共集带载、输出电阻已逐页核对并复算，见[P2.11/P2.12 原页审计](../sources/a02-ap-exercises-p2-11-12-audit.md)。
- P2.13–P2.16 的共射旁路故障/FET 改接、曲线 Q 点和 NMOS 勘误已逐页核对并独立复算，见[P2.13–P2.16 原页审计](../sources/a02-ap-exercises-p2-13-16-audit.md)。
- P2.5 的 12 项端口判断和 P2.7 的源电阻偏置/直连负载已逐页核对并独立复算，见[P2.5/P2.7 原页审计](../sources/a02-ap-exercises-p2-5-7-audit.md)。

- AP PDF pp.72–89（印刷 pp.63–80）已目视回核自测及习题 2.1–2.18；本页重构关键方法和答案，不替代题图。另已逐题复核：P2.1–P2.2 改错/交直流通路（PDF pp.75–78）、P2.3–P2.4 Q 点/负载线/摆幅（PDF pp.76–79）、P2.5 的 12 项判断（pp.79–80）、P2.6 故障诊断（p.80）、P2.7 直连输入/负载（pp.80–81）、P2.8 PNP 极性迁移（p.81）、P2.9–P2.10 增益/摆幅设计（pp.81–82）、P2.11 分压偏置与旁路失效（pp.82–83）、P2.12 共集带载（pp.83–84）、P2.13 旁路电容故障与源分压（pp.84–85）、P2.14 FET 共源接线改错（pp.85–86）、P2.15 JFET 图解 Q 点与小信号参数（pp.86–87）、P2.16 NMOS 算术核查（p.88）、P2.17 偏置/失真调节和 P2.18 复合管判定（pp.88–89）；逐页证据见[AP A02 P2.17–P2.18 核对记录](../sources/a02-ap-exercises-pages-71-80-audit.md)，括号页码均为物理 PDF 页码，对应印刷页见各题定位。
- P2.16 原书题解的 5 V 是算术错误，按图参数应为 8.8 V，见上面的显式核算；P2.6 烧毁后的集电极读数采用题解的简化假设。
- AP §2.3 例 2.3.1–2.3.11 已全部重构，例 2.3.4 见独立推导页；仍需抽查 A02 全章图表，且 AT §2.8 Multisim 当前只有二维码/项目标题，缺可复现的操作正文。因此 A02 整章仍标“部分”。

