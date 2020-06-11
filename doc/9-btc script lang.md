### 交易实例

![tx-outline](res/9-btc_script_lang/tx_outline.png)

一个输入，五个输出。

已收到 1 个确认。

中间的 9.43... 可链接到这个输入的输出来源，详细如下：

![tx_detail](res/9-btc_script_lang/tx_detail.png)

比特币的脚本语言实质上就是一系列只使用了栈，输出脚本与输入一一对应。

实质上的脚本就是按照传入的参数（主要是哈希和信息）选择不同的函数和不同的函数组合方式来对传入的参数进行验证。

也就是说，脚本就是各种函数和这些函数的组合，以及组合函数们的执行流程，再无其他。

如果，学习的重点在区块链，那么，对于具体的函数及组合详细介绍个人认为可不做深入了解。

### 交易内容（图源为视频，与上面的不对应）

交易结构：

![tx-struct](res/9-btc_script_lang/tx-struct.png)

其中的 vin，vout 指的是输入输出部分。

![tx_vin](res/9-btc_script_lang/tx_vin.png)

txid（来源交易 id 和 hash） 和 vout(来源交易的第几个输出) 给出输入的币的来源。

asm 是输入脚本的内容，hex 则是对应的哈希。

vin 是一个数组，所以可能有多个。

![tx-vout](res/9-btc_script_lang/tx_vout.png)

regSigs 指的是输出需要多少签名才可以兑现。

type 是输出类型。

### 输入和输出脚本的几种形式（不做深入了解）

P2PK

P2PKH

P2SH

多重签名

P2SH 多重签名

Proof of Burn

