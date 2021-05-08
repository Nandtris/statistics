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

- 总体方差 p14 p16
  - population variance 
  - `= σ²=[Σ(xi-μ)²]/N`
  - `=[Σ(xi)²]/N-μ² ` 
  - `=[Σ(xi)²]/N-[Σ(xi)]²/N²` 
  - μ~总体平均数
  - 数据点距离中间（均值）有多远
 
- 样本方差  
  - sample variance = s²=[Σ(xi-x)²]/n   
  - x~样本平均数
  - sample variance 通常会低估总体方差
 
- 无偏样本方差 
  - unbised sample variance
  - `s²=[Σ(xi-x)²]/(n-1)`
  - 更好的样本方差公式

- satandard deviation 标准差
  - satandard deviation = sqrt（σ²）
  - 与样本单位一致，可以更好的比较数据
  - 方差（样本单位m)，求出的数据单位m²

- Random Variable:X Y Z...
  - discrete random variable 类似 if...else...函数
    - P(Y=2)=0.5 Y=3 出现的概率是 0.5
  - continuous random variable 
    - 任何完全正好的值，如 P(Y=2)，其概率趋近于0
    - `P(|Y-2|<0.1) = 微积分求区间面积`
    - 概率相当于求 1.9<P<2.1 区间的面积

- 二项分布
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
 
 - 随机变量期望值（E(X)）= 总体均值
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
