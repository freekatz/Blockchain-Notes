比特币（bitcoin）是一种加密货币（crypto-currency）

主要使用密码学中的哈希和签名

### 哈希

密码学中的哈希函数称为 cryptographic hash function，它有两个重要的性质：

1. 抗碰撞（collision resistance）或无碰撞（collision free）

   因为输入空间远远大于输出空间，根据哥侬原理，必定会发生碰撞。

   然而，没有一种好方法找到会发生碰撞的一对输入。

   可以使用蛮力（brute-force）的方法。

   H(M) = H(M^)，摘要（digest）

   计算上不可行 -> 抗碰撞

2. 单向性（hiding）

   从哈希值反推输入很难，也就是说哈希值不包含任何涉及输入的信息。

   可以使用蛮力的方法。

   结合以上两种性质，可完成数字签名（digital commitment）或者数字信封（digital equivalent of a sealed envelope ）

   可公开签名，将哈希值与输入串接。

3. 比特币还要求除了密码学性质之外的第三个性质，无法预测哈希值范围（puzzle friendly）

   挖坑时是要计算得到 随机数（nonce），norce 与其它区块的块头组合在一起计算哈希值，使之满足哈希值小于一个目标阈值：

   H(block header)<=target，block header 头部有很多域，其中一个域允许我们设置随机数 nonce。

   因此此性质使得挖坑没有捷径，进一步，此挖坑过程可以作为工作量证明（proof of work）

   然后，当验证 nonce 时很容易，只需计算一次哈希值，此性质称为（difficult to solve, but easy to verify）

比特币使用的哈希函数是 SHA-256（Secure Hash Algorithm）

### 签名

主要讲解账户管理方式

由于去中心化的特性，每个人是否开户由自己决定，开户的过程就是在本地创建一对公钥和私钥（public key, private key）的过程。

使用非对称加密算法（asymmetric encryption algorithm），公钥无需保密，加密解密都是使用接收方的密钥，私钥不公开，解决了对称加密算法（symmetric encryption algorithm）中密钥分发不方便的问题。

但是比特币是不用加密的，信息都是公开的，因此非对称密码主要用于签名。

签名与加密有所不同，签名的公钥私钥都是使用发送方的，签名用私钥，验证用公钥。

要求产生公私钥时使用好的随机源（a good source of random）

且每一次签名时都要使用好的随机源，只要有一次不好，就有可能泄露私钥。

比特币中一般是先取哈希，然后对哈希值签名。