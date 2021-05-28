# statistics
可汗学院公开课 统计学笔记
>https://www.bilibili.com/video/BV1Hx41177Qu?p=16

- mean
- median 中位数
- mode   众数
- range  极差
- midrange 中程数
- stem-leaf
- box-whiskers
- Check cental tendency & average
```
  - (2 3 3 3 3 100)
  - mean---median---mode---midrange 
  - 114/6--(3+3)/2--3------(2+100)/2
```

### 总体方差 p14 p16
  - population variance 
  - `= σ²=[Σ(xi-μ)²]/N`
  - `=[Σ(xi)²]/N-μ² ` 
  - `=[Σ(xi)²]/N-[Σ(xi)]²/N²` 
  - μ~总体平均数
  - 数据点距离中间（均值）有多远
 
### 样本方差  
  - sample variance = s²=[Σ(xi-x)²]/n   
  - x~样本平均数
  - sample variance 通常会低估总体方差
 
### 无偏样本方差 
  - unbised sample variance
  - `s²=[Σ(xi-x)²]/(n-1)`
  - 更好的样本方差公式

### satandard deviation 标准差
  - satandard deviation = sqrt（σ²）
  - 与样本单位一致，可以更好的比较数据
  - 方差（样本单位m)，求出的数据单位m²

### Random Variable:X Y Z...
  - discrete random variable 类似 if...else...函数
    - P(Y=2)=0.5 Y=3 出现的概率是 0.5
  - continuous random variable 
    - 任何完全正好的值，如 P(Y=2)，其概率趋近于0
    - `P(|Y-2|<0.1) = 微积分求区间面积`
    - 概率相当于求 1.9<P<2.1 区间的面积

### 二项分布
  - flip 5 coins：Head-1 Tails-0
  - 出现正面 Head 的情况
  - 二项式系数(N, M)：`fact(N)/(fact(M)*fact(N-M))`
  ```
  - P(X=0)=P(TTTTT)=5*(1/2)=1/32
  - P(X=1)=5*(1/32)=5/32
  - P(X=2)=(5*4)/2*(1/32)=5!/(2!*3!)*(1/32)=10/32
  - P(X=3)=5!/(3!*2!)*(1/32)=10/32
  - P(X=4)=5!/4!*(1/32)=5/32
  - P(X=5)=P(HHHHH)=1/32
  ```
 
### 随机变量期望值（E(X)）
   - = 总体均值
   - 随机变量总体无穷，无法求和取平均值
   - 因此以频率作为权重，计算出所有结果的加权平均值
   - expect value of binomial distribution
     ```
     E(X)=Σk*(
             (fact(n)/(fact(k)fact(n-k)) * 
             P^k * (1-P)^(n-k)
             ) (Σ:0<=k<=n)
     化简后得到：
     E(X)=np (n=试验次数，p=每次成功的概率)
     ```

### Poisson distribution 泊松分布 P26
  - 满足三个条件，它就服从"泊松分布"
    - 1、事件X的发生是小概率事件
    - 2、事件X的发生是随机而且互相独立的
    - 3、事件X发生的概率相对稳定
  - 相当于二项分布总体（N）趋于无穷大 
  - 离散型
  - 适合于描述单位时间内随机事件发生的次数的概率分布
  - 二项分布从简：类似投6硬币得到3正的概率
  - 随着单位时间内随机事件发生次数的增加，泊松分布会逐渐近似于均值和方差都等于λ的正态分布
  - 当二项分布的n很大而p很小时，泊松分布可作为二项分布的近似，其中λ为np
  - 通常当n≧20,p≦0.05时，就可以用泊松公式近似得计算
  - 概率密度函数公式
  ```
  E(X) = λ # 单位时间（或单位面积）内随机事件的平均发生率
  P(X=k) = (λ^k/k!)*e^(-λ)
  ```
- Reference Thought:
  - 正态分布是所有分布趋于极限大样本的分布，属于连续分布。
  - 二项分布与泊松分布，则都是离散分布
  - 二项分布的极限分布是泊松分布、泊松分布的极限分布是正态分布，即np=λ，当n很大时，可以近似相等。
  - 当n很大时（还没达到连续的程度），可以用泊松分布近似代替二项分布；当n再变大，几乎可以看成连续时，二项分布和泊松分布都可以用正态分布来代替！


### Normal Distribution P29
  - `1/(σ*sqrt(2*pi*exp(((x-μ)/σ)^2))`
  - 正态分布的密度函数
    - 关于μ对称，并在μ处取最大值，
    - 在正（负）无穷远处取值为0，在μ±σ处有拐点，
    - 形状呈现中间高两边低，图像是一条位于x轴上方的钟形曲线
  - N愈大，二项分布越接近正态分布
  - 正态分布是连续的，只能求区间概率密度
  - 累计正态分布 CDF(x),小于x点的区域面积
  - Excel公式：false-概率密度函数，true-累积分布函数
    - `normdist(x,mean,standard_deviation, true/false)`
  - experience rule: 68-95-99.7
    - 68% = P(X=μ+/-σ)
    - 95% = P(X=μ+/-2σ)
    - 99.7% = P(X=μ+/-3σ)

### Central Limit theorem P36
  - 样本容量（n）趋于无穷大时，样本均值抽样分布接近正态分布
  - μ(源数据集）= μ（样本）
  - (样本σ)^2=(源数据集σ)^2/n
  - 样本σ = standard error of the mean
  - 样本容量越大，样本样本σ
- Sample Distribution of the sample mean
  - 从总体中随机抽取n=4个样本，求均值 --- sample mean
  - 以上过程进行10000次，看样本均值分布状态 --- Sample Distribution
- Skew 
  - pos skew --- 正偏态分布，右边尾巴拖的较长
  - negative skew
- Kurtosis ？
  - pos K --- 正峰度，相对正态分布，值越大分布曲线越尖瘦
  - negative K --- 负峰度，相对正态分布，值越小分布曲线越粗胖

- Reference Thought:
  - 大数定律研究的是一系列随机变量的均值是否会依概率收敛于其期望 这个数值
  - 中心极限定理进一步研究均值服从什么分布
  - 若随机变量满足一定的条件，当n足够大时，均值近似服从正态分布，这就是中心极限定理的主要思想
  - 大数定律是指在随机试验中，每次出现的结果不同，但是大量重复试验出现的结果的平均值却几乎总是接近于某个确定的值
  
### Confidence Intercal 置信区间 P40
> 20w apples. one sample: n=36, mean=112g, σ=40g. <br>
> Question: 20w个苹果中均值落在100~124g之间的概率是多少
- Solution
```
100<112=σSample<124
# xavg = the Mean Of One Sample
P(μ is within 12 of xavg) 
=P(xavg is within 12 of μ)
# μxavg = 样本均值抽样分布均值 = 总体样本均值μ
=P(xavg is with 12 of μxavg)
# 转化为求：某一特定样本均值落在样本均值抽样分布均值左右12g范围内的概率
# 求 satadard Z-score
# 用最好的估计来代替总体标准差 σ ≈ 40
# σxavg ≈ 40/sqrt(36)=6.67
# z = 12/6.67 = 1.8
# σxavg = 样本均值抽样分布标准差
=P(xavg is with 1.8 σxavg of μxavg)
# 查 z 分表，找 <=1.89 值 v
= (v-0.5)*2
```

### Bernoulli Distribution 
- Typical case
  - 离散型
  - failure 0 (1-p)
  - Success 1 p
  - mean=P
  - 方差=P(1-P)

### P47 Hypothesis Test and P-value
testing the effect of a drug on response time by injecting 100 rats,<br>
the mean response for rats not injected with drug is 1.2 second,<br>
the mean if the 100 injected rats' response times is 1.05s with <br>
a sample standard deviation of 0.5 second,<br>
Do you think that the drug has an effect on response time?<br>

- Solution(null/alternative hypothetcal)
  - H0: Drug was no effect ---> mean = 1.2
  - H1: Drug was an effect ---> mean != 1.2 when the drug is given 
  - 如果 H0 is True, 得到得到样本(n=100, mean=1.05, standard devation=.5)的概率是多
  - 甚至是更极端情况的概率（比如 样本均值 ±3 个标准差之外的概率）
  - 如果这个概率非常非常小，就可以拒绝 H0
  - 继而认为 H1 正确
  - two-tailed test 双侧检验
    - Drug was effect-posotive >1.2
    - Drug was effect-negative <1.2
  - P-value < 5% reject the null hypothesis
  ```
  样本均值抽样分布标准差 ≈ .5/sqrt(100) = .05
  Z-score = (1.2 - 1.05)/.05 = 3
  P-value = 1 - P(X=3σ) = 1 - 99.7% = .003
  所以拒绝 H0
  ```

### P48 one tailed test 
  - H0 Drug was no effect ---> mean = 1.2
  - H1 Drug lowers effect ---> mean < 1.2 when the drug is given 
  - if H0, P(result lowers than 1.05s) = P-value = .003/2 = .0015
  - 得到结果低于1.05s的概率只有.15%, so reject H0

### P49 z-statistic and t-statistic
- 样本容量n，决定z or t
  - if n > 30 z-statistic Normal Distribution
  - if n < 30 t-statistic t-Distribution

### P50 Type 1 Error
- Reject H0 even though it is True

### P51 小样本假设检验
A new engine standard:  <20ppm <br>
now enginessamples: n=10, mean=17.17, s=2.98 <br>
Question: Does the data supply sufficient evidence to conclude <br>
that this type of engine meets the new standard? Assume Type 1 error P=0.01.
- H0 mean(sample)=20ppm
- H1 mean(sample)<20
- one tailed test
- Assum H0 is True, then
```
n=10 < 30 ---> t-statistic
t = (17.17-20)/(2.98/sqrt(10)) = -3
t_table check 自由度=10-1=9,累计概率=1-1%=99% 的值为2.821
# t 标准分布均值=0，两段对称，只是尾巴部分相对正态分布肥而已
# t_table 显示 positive 部分值
也即 <-2.821 区间概率 1%， -3<-2.821 reject H0
```
- P53 大样本占比假设检验
  - Bernoulii distribution 
  - significant level
  - P_value

## Review
- None
- Null
- NaN

### P69-70 线性回归公式与决定系数 sqrt(r)
- 二维坐标上的散点(x1, y1)...(xn, yn)
  - `(-2, -3), (-1, -1), (1, 2), (4, 3)`
- 线性回归方程
  - `LINE y = mx + b`
  - 最小化点到直线的总平方误差直线
- 斜率
  - `m = (mean(xy)-mean(x)meax(y))/(mean(x^2)-(mean(x))^2)`
- 截距
  - `b = mean(y) - m*mean(x)`
- 决定系数 sqrt(r)
  - `SE(LINE)/SE(mean(y))`
  - 衡量直线拟合程度好坏
  - 回归线没有描述的波动，即总波动中不能由直线或x波动解释
    - `SE(LINE) = (y1-y)^2 + ... + (yn-y)^2`
  - total variation in y
    - `SE(mean(y)) = (y1-mean(y))^2 + ... + (yn--mean(y))^2`
  - what percentage of the variation in y is described by the variation in x or LINE
    - `1 - sqrt(r)`


### P71 Covariance 
- covariance between 2 random varianbles
- 两变量多大程度上一同变化
- `cov(X, Y)=E[(X-e[X])(Y-E[Y])] = E[XY]-E[X]E[Y]'
- 用样本近似估计：
  - `E[XY]≈mean(XY) E[X]≈mean(X) E[Y]≈mean(Y)`
  - `cov(X,Y) ≈ mean(XY)-mean(X)mean(Y)`
  - 斜率 `m = cov(X,Y)/cov(X,X)`
  - 随机变量对自身的协方差 = 该随机变量的方差
  - 斜率 `m = cov(X,Y)/var(X)`

###　P72 Chi square distribution
- 检验理论分布同观测结果的吻合度
- Chi square 统计量
  - `Chi square = Σ[(fi-Fi)^2/Fi] (1<= i <=n)`
  - fi 实际观察的量
  - Fi 运用目标分布计算出的量
  - 当样本n趋于无穷大时，统计量收敛于 Chi square distribution
