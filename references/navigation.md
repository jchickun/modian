# 模拟电子主题导航

先按问题目的选主题；需要教材题目时，可从对应主题页进入 AT/AP 原题重构和练习路线；完整章节文件清单、书目题号与配套关系见[模电配套索引](analog/index.md)。覆盖状态与未取得的资源正文见[小节覆盖表](sources/subsection-coverage.md)。

| 主题 | 优先阅读 | 典型问题 |
|---|---|---|
| 系统与学习路线 | [A00 系统视角](analog/a00-system-view.md) | 信号链、性能指标、分析/仿真方法选择 |
| 器件模型与判区 | [A01 器件知识](analog/a01-devices-knowledge.md) · [练习路线](analog/a01-devices-practice.md) · [AT 原题](analog/a01-at-book-examples.md) · [AP 例题](analog/a01-book-examples.md) · [AP 自测/习题](analog/a01-book-exercises.md) | 二极管、稳压管、BJT/FET 等效模型与工作区 |
| 偏置与基本放大 | [A02 知识](analog/a02-amplifiers-knowledge.md) · [练习](analog/a02-amplifiers-practice.md) · [AT 例题索引](analog/a02-at-book-examples.md) · [AP 例题](analog/a02-book-examples.md) · [AP 自测/习题](analog/a02-book-exercises.md) | Q 点、负载线、CE/CC/CB、共源/共漏、摆幅 |
| 多级与运放 | [A03 知识](analog/a03-opamps-knowledge.md) · [练习](analog/a03-opamps-practice.md) · [AP 自测/习题](analog/a03-book-self-test-and-exercises.md) | 级间加载、差分级、电流源、有源负载、运放 |
| 频率响应 | [A04 知识](analog/a04-frequency-knowledge.md) · [练习](analog/a04-frequency-practice.md) · [AP 例 4.3.4 推导](analog/a04-book-frequency.md) · [AP 习题 4.1–4.14](analog/a04-book-exercises.md) | 截止频率、波特图、米勒效应、多级带宽 |
| 反馈与稳定性 | [A05 知识](analog/a05-feedback-knowledge.md) · [练习](analog/a05-feedback-practice.md) · [AT 反馈组态与接线原题](analog/a05-at-feedback-examples.md) · [概念/选择/接线原题](analog/a05-book-feedback-selection.md) · [深度反馈与故障原题](analog/a05-book-feedback-analysis-faults.md) · [AP 组态/稳定性原题](analog/a05-book-feedback-examples.md) · [AP §5.4 自测与习题](analog/a05-book-exercises.md) | 四组态、闭环增益、输入/输出阻抗、相位裕度 |
| 运算、滤波与测量前端 | [A06 知识](analog/a06-processing-knowledge.md) · [练习](analog/a06-processing-practice.md) · [AP 原题](analog/a06-book-examples.md) | 运算放大器、积分/微分、滤波器、传感器前端 |
| 振荡、波形与转换 | [A07 知识](analog/a07-waveforms-knowledge.md) · [练习](analog/a07-waveforms-practice.md) · [AP 例题](analog/a07-book-examples.md) · [AP 习题](analog/a07-ap-book-exercises.md) · [AT 习题](analog/a07-at-book-exercises.md) | 振荡器、比较/滞回、整形、V-I/I-V、V-F |
| 功率放大 | [A08 知识](analog/a08-power-knowledge.md) · [练习](analog/a08-power-practice.md) · [AP 原题](analog/a08-book-examples.md) | 甲/乙/甲乙类、OCL/BTL、效率、管耗与散热 |
| 直流电源 | [A09 知识](analog/a09-supplies-knowledge.md) · [练习](analog/a09-supplies-practice.md) · [AT 思考题/例题](analog/a09-at-examples.md) · [AP 原题](analog/a09-book-examples.md) | 整流、滤波、线性稳压、Buck/Boost |
| 综合电路读图 | [A10 读图知识](analog/a10-schematic-knowledge.md) · [读图与故障定位练习](analog/a10-schematic-practice.md) · [AT 实例](analog/a10-book-schematics.md) · [AP 原题](analog/a10-book-exercises.md) | 从系统功能到级间作用、偏置、反馈和故障定位 |

## 按任务查阅

- **求静态工作点：** A01 器件模型 → A02/A03/A06/A08/A09 相应偏置网络 → 核对工作区与功耗。
- **求增益或阻抗：** 明确输入参考端、输出端接条件和负载 → 建立中频/频域小信号图 → A02/A03/A05/A06 对应页。
- **求截止频率：** 先求中频增益和允许下降量 → 标出电容与等效电阻 → A04；逐个极点不可简单相加时查主导极点条件。
- **判断振荡或失真：** 分别检查环路相位/增益、正负限幅和器件工作区 → A05/A07/A08。
- **核对原题：** 使用 A01–A10 对应 `book-*.md` 页；自构题与工程补充不会伪装成教材原题。

