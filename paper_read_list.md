### 2019.11.09
1 《NLP」异构记忆网络让机器客服更像人类客服》
ref：https://mp.weixin.qq.com/s?__biz=MzAwNjM1ODkxNQ==&mid=2650891073&idx=1&sn=2022c2ad1e46e333b10d83ba8597e94f&chksm=80fb51adb78cd8bbf6eab618fda2d1f9cca021f3a2530c3e375d5bc221882bd939339bb1603a&mpshare=1&scene=24&srcid=&sharer_sharetime=1573223767499&sharer_shareid=c06b20cb64d0d100e45d8da7da802543&key=f5935be8e3f9b86a3def7ffd3b8461d0fe66d9dc0b2ad5521103adc07877c33178f1edc6370fb62baf68472cf0bdd2f9206746ef38f51a6afbb022ca971fed4316ee643f6fda334e615e374797497bba&ascene=0&uin=NzM0OTg3ODQw&devicetype=iMac+MacBookPro11%2C4+OSX+OSX+10.12.5+build(16F73)&version=12020610&nettype=WIFI&lang=en&fontScale=100&pass_ticket=oVz42nEjD1j9zjNBg4apkg5goWeSjcmHIaLATYuJDEkhJcXJzUvF%2FLKkDGGEUDAY

相关参考：
a) Mem2seq: Effectively incorporating knowledge bases intoend-to-end task-oriented dialog systems
b) Key-value retrieval networksfor task-oriented dialogue.
c) http://camdial.org/~mh521/dstc/downloads/handbook.pdf
d) Learning end-to-endgoal-oriented dialog
e) End-to-endmemory networks.
f) Neural responding machinefor short-text conversation
g) A neural conversational model.
h) On the properties of neural machinetranslation: Encoder-decoder approaches.

关于mem-network中的hop概念
《End-To-End Memory Networks》
![模型框架图](https://raw.githubusercontent.com/bigheary/markdown_pics/master/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202019-11-09%20%E4%B8%8B%E5%8D%8812.48.27.png)
从模型结构上看，通过多个hop结构进行stack，最后得到一个输出结果做classify，每个hop的处理完成了将输入的query(u)，memory转化成一个output(o), 并且通过一个combine(u, o) 形成下一个hop的input，经过固定次数hop最后输出。
总结：
1）. 每个hop的memory形成通过embedding的方式，output也是通过embedding方式，结合成o的过程类似attention机制；
2）. 多个hop间的embedding可以共享，也可以不共享。
3）. 结构类似后面出现的transformer（尤其是还使用了positional encoding，pe）；
4）. 和rnn的关系，好像没法完全对应上，没有step的概念，好像不适用于2seq；
4）. 应用在qa，nnlm，没详细研究，主要了解下结构及multi-hop概念；
