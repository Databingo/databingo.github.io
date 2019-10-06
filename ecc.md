
<!--- <head>
<script type="text/javascript" async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=Tex-AMS-MML_HTMLorMML"></script>
<script type="text/x-mathjax-config">MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]}});</script>
</head>
-->


## <p align="center"> ECC 原理推导与代码实现 </p>
#### <p align="center">————如何彻底理解 ECC 加密原理并部署代码</p>
&nbsp;  
&nbsp;  
### <p align="center">摘要</p>
&nbsp;  
&emsp;&emsp;比特币 金融 革命 分布式 加密 匿名 确权  libra 央行 CBCD 价值 基础 ECC 不对称加密 数学原理 实现  
&emsp;&emsp;【关键词】 ECC、 椭圆曲线、 不对称加密、 数学原理、 编程实现  
&emsp;&emsp;【作者】 陈钢， 中国政法大学硕士 2007 级研究生  
### 第一章 数学原理
#### 第一节 威尔斯特拉斯方程
#### 第二节 射影平面
#### 第二节 阿尔贝群
### 第二章 代码实现
### 注释
————————————————  
（原理篇+代码篇）  
$d \mid a$</br>
##基于椭圆曲线离散对数难题的不对称加密算法  
射影平面？  
威尔斯特拉斯方程？!!  
非奇异？  
齐次方程？  
一条椭圆曲线是在射影平面上满足威尔斯特拉斯方程(Weierstrass)所有点的集合,且曲线上的每个点都是非奇异（或光滑）的。  
<img src="http://latex.codecogs.com/png.latex?\\Y^2Z+a_1XYZ+a_3YZ^2=X^3+a_2X^2Z+a_4XZ^2+a_6Z^3" />--[t1]</br>

- 1.这是一个齐次方程。
- 2.椭圆曲线的形状，并不是椭圆的，只是因为这个方程类似于计算一个椭圆周长的方程，故取名“椭圆曲线”。
标准椭圆曲线方程： 
<img src="http://latex.codecogs.com/png.latex?\200dpi \frac{x^2 }{a^2} + \frac{y^2}{b^2} = 1" />
(a > b, 焦点在 X 轴， a < b, 焦点在 Y 轴)
- 3.非奇异(偏导数)
- 4.椭圆曲线上有一个无穷远点O∞（0:1:0)， 因为这个点满足方程 [t1]
- 5.放到普通平面直角坐标系，加上无穷远点（推导过程,射影平面坐标到普通平面坐标的推导过程）  
对普通平面直角坐标系上的点A的坐标(x,y)做如下改造：
令x=X/Z， y=Y/Z, Z!=0, 则A点可以表示为（X：Y：Z），变成了有三个参量的坐标点，这就对平面上的点建立了一个新的坐标体系。

并得到如下方程：
<img src="http://latex.codecogs.com/png.latex?\200dpi \\y^2Z^3+a_1xyZ^3+a_3yZ^3=x^3Z^3+a_2x^2Z^3+a_4xZ^3+a_6Z^3" />--[t2]  
约掉 Z<sup>3</sup>可以得到：  
<img src="http://latex.codecogs.com/png.latex?\200dpi \\y^2+a_1xy+a_3y=x^3+a_2x^2+a_4x+a_6" />--[t3]  
简化版的Weierstrass方程:  
<img src="http://latex.codecogs.com/png.latex?\200dpi \\E:y^2=x^3+ax+b" />--[t4]  
其中(保证曲线是光滑的，所有点没有两个或者以上的不同的切线):  
<img src="http://latex.codecogs.com/png.latex?\200dpi \\\Delta = -16(4a^3+27b^2)\neq 0" />  
比特币椭圆曲线 secpk1:  
<img src="http://latex.codecogs.com/png.latex?\200dpi \\y^{2}=x^{3}+x+7" />--[t5]  






曲线公式：y^3 + axy^2 + bx^2y = x^3 + cyx^2 + dxy^2(齐次方程)
<img src="http://latex.codecogs.com/png.latex?\200dpi \\y^{3}+axy^{2}+bx^{2}y=x^{3}+cyx^{2}+dy^{2}x" />  
（椭圆曲线周长公式）



其一 : y^2=X^3 + ax +b 
<img src="http://latex.codecogs.com/png.latex?\200dpi \\y^{2}=x^{3}+ax+b" /></br>

secpk1: y^2=X^3 + x + 7
<img src="http://latex.codecogs.com/png.latex?\200dpi \\y^{2}=x^{3}+x+7" /></br>

1.假设 q,p 是曲线 e 上两点，过 qp 的直线与 e 交于 r 点，若 qp 重合，则过 qp 的切线与 e 相交于 r 点
2. 过 r 点与无限远点的直线，与 e 交于 r’ 点
条件：ab…
推理：123

<!--- 
<img src="http://latex.codecogs.com/png.latex?\dpi{200}&space;\bg_grey&space;35*d_1_5_3+1(\oe%20)" />
<img src="http://latex.codecogs.com/png.latex?\200dpi \bg_grey \35*d_1_5_3+1(\oe%20)" />
<img src="http://latex.codecogs.com/png.latex?\200dpi \bg_grey \inline \35*d_1_5_3+1(\oe%20)" />
<img src="http://latex.codecogs.com/png.latex?\200dpi \bg_grey \inline \LARGE \35*d_1_5_3+1(\oe%20)" />
<img src="http://latex.codecogs.com/png.latex?\200dpi \bg_grey \\Y^2Z+a_1XYZ+a_3YZ^2=X^3+a_2X^2Z+a_4XZ^2+a_6Z^3" />--[t1]</br>
(mod\ n)
-->

<!--- 
https://www.codecogs.com/latex/eqneditor.php 语法提示
https://www.desmos.com/calculator 函数绘图
https://rechneronline.de/function-graphs/ 函数绘图

-->
笛卡尔坐标到射影坐标，多了无限远点（平行线相交于无限远点）



假设这样一个关系：q 与 p 确定 r, r 与 无限远点*确定 r’
- 表示关于 x 轴取对称点
q+p = r’
r + * = r’ 或者  r’ + * = r 或者 r + r’ = * 
q +p + r = r’ + r = *
q+p+r=*
符合这样一个规律：(阿尔贝群定理)
1 q + p = r’ 等价 r’ +p’ = q 交换律
2 (q + p) + r = q+ (p + r )=* 结合律
3 q = -(* + q’) 逆元（相反数）
4 q,p 属于 e, 则 q+p属于 e (闭包)
5.q+* = *+ q = q(单位元)
这就是一个符合加法规律的集合。


模运算，使图像从平滑曲线变为离散的点集合

那么假设在曲线 y^2=X^3 + x + 7 上
kp = p + p+ p +…p=K
知道 k,p 计算 kp 有简单算法..
知道 K,p 计算 k 只能逐步计算，设 k= 2^256 则为 NP-hard 难题，视为无法完成。

加解密原理：
c1, c2..
实际实现代码：信息是如何加密和被解密的。




椭圆曲线Ep(a,b), p为大质数，x,y属于[0,p-1]
y^2=x^3 + ax +b (mod p)
选择两个满足下列约束条件的小于 p 的非负整数a、b
4a^3 + 27b^2 != 0 (mod p) [why?]保证曲线是光滑的，所有点没有两个或者以上的不同的切线？
<img src="http://latex.codecogs.com/png.latex?\200dpi \\4a^{3}+27b^{2} \neq 0\ (mod\ p)" /></br>
P(x1,y1), Q(x2,y2)的和R(x3,y3)有如下关系：
x3=k^2 -x1-x2(mod p)
y3 =k(x1-x3)-y1(mod p)
斜率 
k=(3x2 + a)/2y1 [P=Q]
k=(y2-y1)/(x2-x1)



K=kG, k<n (G 为椭圆曲线Ep(a，b)上的点，n为G的阶，即 nG=*
点G称作基点(base point)
k(k<n)为私有密钥(private key)
K为公开密钥(public key)
