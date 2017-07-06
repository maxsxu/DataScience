| 时间 | 论文 | 发表 | 方法概述 | 处理对象 | 数据集 | 网络结构 | 特点 |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| 2016 | Multivariate Industrial Time Series with Cyber-Attack Simulation: Fault Detection Using an LSTM-based Predictive Data Model | NIPS Time-Series Workshop 2016 | 1.多维度数据归一化到同一尺度，数据分组，每组长度为 w <br> 2.使用 LSTM 预测, 用前 *i* 组数据预测第 *i+1* 组数据 <br> 3.计算预测值和观测值的误差（MSE）, 比较误差和阈值判断是否为异常 <br> | 多维度时间序列（使用了6维） | 模拟生成的瓦斯油工厂数据 | 2个隐含层+1 个线性输出层 | 阈值的选取，作为一个可调节参数存在 |
| 2016 | Anomaly detection in aircraft data using Recurrent Neural Networks (RNN) | 2016 Integrated Communications Navigation and Surveillance (ICNS) Conference | 1.使用 RNN-LSTM 和 RNN-GRU 预测，用时刻 *t* 的观测值预测 *t+1* 时刻的值，<br> 2.计算误差（MSE）判断异常，对比方法为 MKAD。文章没有介绍更多细节 | 多维度时间序列 | 模拟生成的飞机飞行数据 | 设计了10种结构，对 epochs/batch size/validation/dropout/time stemps 取了10个组合 |  |
| 2016 | Using LSTM recurrent neural networks to predict excess vibration events in aircraft engines | e-Science (e-Science), 2016 IEEE 12th International Conference | 预测发动机振动。只是利用 LSTM 预测 | 多维度时间序列（选取了 15 维） | 飞机发动机振动数据 | 设计了三种 LSTM 架构 | | 
| 2016 | Lstm-based encoder-decoder for multi-sensor anomaly detection | CoRR | 1.对正常数据进行训练，得到正常数据的模型，基于 LSTM | 多维度时间序列 | 电力需求/航天飞机/心电图 | 2个隐含层 | 输出的是异常分值，比较异常分值的高低来判断异常 |
| 2015 | Long short term memory networks for anomaly detection in time series | In 23rd European Symposium on Artificial Neural Networks, Computational Intelligence and Machine Learning. | 1.在正常数据上训练网络，预测误差建模为多变量高斯分布评估异常。预测之后 *l* 个值，<br> 2. 对每个数据点可以计算出一个长度为 *dxl* 的预测误差向量，将这个误差向量建模为多变量高斯分布，<br> 3.计算误差分布的似然，比较似然和一个阈值判断异常 | 多维度时间序列 | 心电图/航天飞机/电力需求/多传感器引擎数据 | 2个隐含层 | 阈值通过正常数据的验证集和异常数据的测试集来计算 $F_{\beta} score$ 得到 | 

# Similarity
1. 数据。对数据集的划分。train/validation/test
2. 预测。预测的 timestep 不同。分组预测/点预测
3. 误差。对预测误差的处理，值比较/分布
4. 阈值。阈值的选取。人工指定/动态调节/计算得到
