# A06 AT/AP 章末习题配套交叉表

本页对照 AT《模拟电子技术基础（第六版）》和 AP《模拟电子技术基础学习辅导与习题解答（第六版）》第 6 章。题号相同只表示编号可对应，不保证题干、数据、符号或答案完全相同。解题时以正在使用的那本书的原页为准。

原页审计：[AT 章末 pp.303–310](../sources/a06-at-pages-303-310-audit.md)；[AP P6.1–P6.5](../sources/a06-ap-exercises-1-5-audit.md)、[P6.6–P6.10](../sources/a06-ap-exercises-6-10-audit.md)、[P6.11–P6.15](../sources/a06-ap-exercises-11-15-audit.md)、[P6.16–P6.20](../sources/a06-ap-exercises-16-20-audit.md)、[P6.21–P6.22](../sources/a06-ap-exercises-21-22-audit.md)、[P6.23](../sources/a06-ap-exercise-23-audit.md)。AT/AP 逐组交叉核对见：[P6.1–P6.5](../sources/a06-at-ap-exercises-1-5-crosscheck.md)、[P6.6–P6.10](../sources/a06-at-ap-exercises-6-10-crosscheck.md)、[P6.11–P6.15](../sources/a06-at-ap-exercises-11-15-crosscheck.md)、[P6.16–P6.18](../sources/a06-at-ap-exercises-16-18-crosscheck.md)、[P6.19–P6.23](../sources/a06-at-ap-exercises-19-23-crosscheck.md)。

## 题号映射与核查范围

| 题号 | 共同题型/主题 | 配套使用时的核查要求 |
|---|---|---|
| P6.1–P6.5 | 运算器选择、输出限幅、比例/T 形反馈、输入电阻和故障分析 | 已逐页确认题目与参数一致：P6.2 的增益、输入值和 ±14 V 限幅相同；P6.3 要求 `R_i=20 kΩ`、增益 −100；P6.4/P6.5 共享相同图 P6.4，且故障顺序相同。AP 答案复算一致；AT QR 答案仍未取回。详见[本组交叉审计](../sources/a06-at-ap-exercises-1-5-crosscheck.md)。 |
| P6.6–P6.10 | 多输入运算、共模电位、恒流源、可调差分级、级联求和 | 已逐题确认电路图、元件值和条件一致；AP 结果经独立复算可用于核验 AT 同题。恒流源顺从范围及运放输入/输出范围仍需按实际器件核对。详见[本组交叉审计](../sources/a06-at-ap-exercises-6-10-crosscheck.md)。 |
| P6.11–P6.15 | 积分波形、直接输入项、四种运算关系、差值级积分和两级积分 | 已逐题确认题干、图、元件值、输入波形与初始条件一致；AP 关键结果经独立复算。P6.12 输入阶跃导致输出同步跳变；积分常数仍取决于电容初态。见[交叉审计](../sources/a06-at-ap-exercises-11-15-crosscheck.md)。 |
| P6.16–P6.18 | 电阻链与复位积分、乘法器反馈除法、运算关系识别 | 已逐图确认接线、参数、乘法器符号及输入条件一致；AP 关系经独立节点方程复核。除法题需保留分母非零、符号与线性范围条件。见[交叉审计](../sources/a06-at-ap-exercises-16-18-crosscheck.md)。 |
| P6.19(1) | 平方和开方 | 两书目标式相同：`u_o1=−√(2u_i1²+2u_i2²)`。两者都是设计题，AT 未给唯一电路/参数；AP 设计仅作为可行实现，不当作 AT 标准答案。见[交叉审计](../sources/a06-at-ap-exercises-19-23-crosscheck.md)。 |
| P6.19(2) | 乘法器反馈除法设计 | 目标式不同：AT 印刷 p.308/PDF p.340 为 `u_o2=4u_i1/(2u_i2+2u_i3)`；AP 印刷 p.239/PDF p.248 为 `u_o2=4u_i1/(2u_i2−u_i3)`。不得套用同一分母级或输入范围，见[交叉审计](../sources/a06-at-ap-exercises-19-23-crosscheck.md)。 |
| P6.19(3) | 乘法器、积分器级联 | 目标尺度存在显著差异：AT 印刷 p.309/PDF p.341 为 `u_o3=−(1/10³)∫(6u_i1·u_i2)dt`；AP 印刷 p.239/PDF p.248 为 `u_o3=−10³∫(6u_i1·u_i2)dt`。两目标相差 `10⁶` 倍；AP 解图实际给出 `+600∫u_i1u_i2dt+K`，还与 AP 题面反号且小 10 倍。AT 二维码答案未取回，不能据 AP 解图推断 AT 答案。详见[交叉审计](../sources/a06-at-ap-exercises-19-23-crosscheck.md)。 |
| P6.20 | 四种滤波器类型和阶数 | AT/AP 四张图的连接对应一致：依次为一阶 HPF、二阶 HPF、二阶 BPF、二阶 BEF。P6.20(b) 的 `C_1` 影响响应系数但不增加极点数；判断依据是约简传递函数分母阶数。见[交叉审计](../sources/a06-at-ap-exercises-19-23-crosscheck.md)。 |
| P6.21 | 一阶 HPF 与二阶 LPF 级联成 BPF | 截止频率不同：AT 印刷 p.309/PDF p.341 为 `2 Hz` 与 `100 kHz`；AP 印刷 p.241/PDF p.250 为 `100 Hz` 与 `2 kHz`。两者都可画出约 `+20 dB/dec` 的低频渐近段、`−40 dB/dec` 的高频渐近段，但通带范围按各自数据；见[交叉审计](../sources/a06-at-ap-exercises-19-23-crosscheck.md)。 |
| P6.22 | 调用 AT 图 6.3.9 的压控二阶 LPF 设计 | AT 与 AP 的题设都是通带增益 2、题面截止频率 1 kHz、`C=1 μF`。AP 解答印出的 `160 kΩ/640 kΩ` 与代入关系相差 1000 倍，应约为 `160 Ω/640 Ω`；其 `Q=1` 响应的 `f_0` 不是严格 −3 dB 点，见[交叉审计](../sources/a06-at-ap-exercises-19-23-crosscheck.md)。AT 的二维码答案尚不可见。 |
| P6.23 | 状态变量滤波器三路输出类型识别 | AT/AP 电路和输出标签一致，按信号链核对 `u_o1` HPF、`u_o2` BPF、`u_o3` LPF；不由题面外推中心频率、Q 或带宽。见[交叉审计](../sources/a06-at-ap-exercises-19-23-crosscheck.md)。 |

## 使用规则

1. 引用题目时先写来源前缀，例如“AT P6.21”或“AP P6.21”，不要只写 P6.21。
2. 同号题先比目标函数和参数，再决定能否复用推导；只要一项不一致，就从该来源题图重新列节点方程。
3. AP 已重构的题解只证明 AP 题页与 AP 解页之间的关系；AT 题目的答案二维码未取回时，独立推导须明确标为“自解”，不能标成 AT 原书答案。
4. P6.19(2)(3) 与 P6.21 已确认存在数据/目标差异。P6.1–P6.18 的本页是题型层面的导航，不代表每个电阻值都已做双书逐元件对照。
