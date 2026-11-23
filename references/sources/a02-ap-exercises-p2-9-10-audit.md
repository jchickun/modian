# AP A02 习题 P2.9–P2.10 原页与计算核查

## 来源与页图

- 来源文件：`模拟电子技术基础 学习辅导与习题解答 第六版 (华成英 童诗白).pdf`，PDF SHA-256：`2BF2C33FFA1CAAE7291892EE8B9EC7F001741A62861089955E4D593EB65DDC00`。
- 直接目视核对 PDF p.81（印刷 p.72）和 p.82（印刷 p.73）。PDF p.81 可见图 P2.9、固定偏置共射结构、输入/输出耦合电容及 P2.9 两问；PDF p.82 可见 P2.9 解答、P2.10 题干及完整解答。
- 图 P2.9 标出 \(V_{CC}=12\,\mathrm V\)、\(R_C=3\,\mathrm{k\Omega}\)，并由耦合电容接入输入源和 \(R_L\)。P2.9 给出 \(\beta=100\)、\(r_{be}=1\,\mathrm{k\Omega}\)；P2.10 沿用图 P2.9，另给 \(I_{CQ}=2\,\mathrm{mA}\)、\(U_{CES}=0.6\,\mathrm V\) 和 \(R_L=3\,\mathrm{k\Omega}\)。

## P2.9：偏置与增益门槛

### 原页内容

第（1）问给定 \(U_{CEQ}=6\,\mathrm V\)，求固定偏置电阻。第（2）问保持 \(R_B\) 不变，令 \(R_L=5\,\mathrm{k\Omega}\)，要求输入有效值 \(U_i=1\,\mathrm{mV}\) 时输出有效值 \(U_o>200\,\mathrm{mV}\)，求 \(R_C\) 至少取多少。原书题解写出 \(I_{CQ}=2\,\mathrm{mA}\)、\(I_{BQ}=20\,\mu\mathrm A\)、\(R_B\approx565\,\mathrm{k\Omega}\)，并给出 \(R_C\) 应大于约 \(3.3\,\mathrm{k\Omega}\)。

### 独立复算

\[
I_{CQ}=\frac{12-6}{3\,\mathrm{k\Omega}}=2\,\mathrm{mA},\qquad
I_{BQ}\approx\frac{2\,\mathrm{mA}}{100}=20\,\mu\mathrm A,
\]
\[
R_B\approx\frac{12-0.7}{20\,\mu\mathrm A}=565\,\mathrm{k\Omega}.
\]
对第（2）问，要求 \(|A_u|>200\)。按题给中频小信号关系 \(|A_u|\approx\beta(R_C\parallel R_L)/r_{be}\)：
\[
R_C\parallel5\,\mathrm{k\Omega}>2\,\mathrm{k\Omega}
\Longrightarrow
\frac{5R_C}{R_C+5}>2
\Longrightarrow
R_C>\frac{10}{3}\,\mathrm{k\Omega}=3.333\ldots\,\mathrm{k\Omega},
\]
其中并联式中的电阻数值以 kΩ 计。严格不等号来自题设 \(U_o>200\,\mathrm{mV}\)；等于阈值只得到 200 倍增益。原书将阈值写为约 3.3 kΩ，选取值必须高于精确边界。

### 条件与边界

\(R_B\) 不变时，改变 \(R_C\) 仍须重新求 Q 点并确认晶体管保持放大区。P2.9 未给饱和边界电压，也未要求最大摆幅；因此“满足小信号增益门槛”本身不能证明任意所选 \(R_C\) 下均无削顶。阈值附近输出要求仅为 0.2 V rms（峰值约 0.283 V）；最终选值应使用器件的饱和模型复核直流工作点和交流余量，不把 P2.10 的 \(U_{CES}=0.6\,\mathrm V\) 倒灌为 P2.9 的题设。

## P2.10：最大不失真输出

### 原页内容

P2.10 沿用图 P2.9，给定静态 \(I_{CQ}=2\,\mathrm{mA}\)、\(\beta=100\)、\(U_{CES}=0.6\,\mathrm V\)，并接入电容耦合的 \(R_L=3\,\mathrm{k\Omega}\)。题目先求最大不失真输出，再要求在其他电路参数不变时调节 \(R_B\) 使输出最大。原书初始输出约为 2.12 V；优化后给出 \(I_{CQ}\approx2.53\,\mathrm{mA}\)、\(R_B\approx447\,\mathrm{k\Omega}\)、输出约 2.68 V。

### 独立复算

负载由电容耦合，直流 Q 点仍由未接负载时的偏置决定：
\[
U_{CEQ}=V_{CC}-I_{CQ}R_C=12-(2\,\mathrm{mA})(3\,\mathrm{k\Omega})=6\,\mathrm V,
\qquad
R'_L=R_C\parallel R_L=1.5\,\mathrm{k\Omega}.
\]
截止方向的峰值余量为 \(I_{CQ}R'_L=3\,\mathrm V\)，饱和方向为 \(U_{CEQ}-U_{CES}=5.4\,\mathrm V\)，先达到截止边界。因此
\[
U_{o,\mathrm{rms,max}}=\frac{3}{\sqrt2}=2.1213\,\mathrm V\approx2.12\,\mathrm V.
\]
这里 3 V 是峰值，除以 \(\sqrt2\) 才是正弦有效值。

优化偏置时令两侧峰值余量相等：
\[
I_{CQ}R'_L=U_{CEQ}-U_{CES},\qquad U_{CEQ}=V_{CC}-I_{CQ}R_C,
\]
\[
I_{CQ}=\frac{V_{CC}-U_{CES}}{R_C+R'_L}
=\frac{11.4}{4.5\,\mathrm{k\Omega}}
=2.5333\,\mathrm{mA}.
\]
于是 \(I_{BQ}=25.333\,\mu\mathrm A\)，按 \(U_{BEQ}\approx0.7\,\mathrm V\)：
\[
R_B\approx\frac{12-0.7}{25.333\,\mu\mathrm A}=446.1\,\mathrm{k\Omega}.
\]
新静态电压 \(U_{CEQ}=4.40\,\mathrm V\)，两侧峰值余量均为 3.80 V，故
\[
U_{o,\mathrm{rms,max}}=\frac{3.80}{\sqrt2}=2.6870\,\mathrm V.
\]

### 差异判定

未发现新增原书算术错误。原书先把 \(I_{CQ}\) 取为 2.53 mA，再代入偏置式得到约 447 kΩ；保留未舍入电流时为 446.1 kΩ。原书约 2.68 V 与先将余量取为约 3.79 V 后计算相符；保留完整精度约为 2.687 V（四舍五入到百分位为 2.69 V）。这些是中间量取位造成的末位差别。若负载改成直流直连，必须将其纳入直流 Q 点方程，以上“耦合负载不改变 Q 点”不再适用。
