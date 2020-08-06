[1]: [Core Concepts, Challenges, and Future Directions in Blockchain](https://doi.org/10.1145/3366370)

“【】”符号及数字表示此内容需要日后深入学习

**重点关注论文的论述思路、方法及对比**

---

## 主题：论文主要介绍了哪些内容

1.  the fundamental elements of blockchains
2.  their ability to achieve availability, consistency, and data integrity as well as their inherent limitations
3.  using Ethereum as a case study, describe the inner workings of blockchains
4.  comparing blockchains to traditional distributed systems
5.  discuss the major challenges facing blockchain
6.  summarize ongoing research and commercial offerings that seek to address these challenges.

## 结构：论文叙述结构

1.  introduce: 
    1.  Abstractly, a blockchain is a mechanism to reach agreement on the order of events among a set of entities.
    2.  Blockchain enables a fully decentralized system
    3.  provides an introduction to the inner workings of a blockchain, as well as their strengths and limitations, and then goes into more detail on Ethereum as a representative example and basis for comparison against other blockchains discussed later on in the article. 
    4.  present the challenges currently facing blockchains, which also involves a discussion of system design choices, and summarize the ongoing research efforts to address these challenges. 
    5.  provide an overview of several commercial blockchains.
    6.  focus on the most prominent and illustrative concepts and examples, while providing ample references for readers to further pursue subtopics of interest.
    7.  introduce the relevant work in academic
    8.  present the structure of this article, details as following
    
2.  略

3.  略

4.  传统分布式计算和区块链

    1.  相关概念介绍

    2.  对比：All three systems require consensus for adding new transactions. Distributed databases and permissioned blockchains require authenticated participants and thus do not need to tolerate Sybil attacks. Therefore, they can use traditional consensus protocols such as Paxos and PBFT. Public blockchains consider a much more hostile environment and therefore use consensus mechanisms that can tolerate Sybil attacks. 

        However, this comes at the cost of non-deterministic consensus, which can cause forks and lead to additional vulnerabilities [57]. Accounting for these vulner- abilities adds additional constraints on the performance, scalability, and throughput of public blockchains [33], making it the least scalable among all three systems (as discussed in Section 2.5).

    3.  Table 1

5.  其它共识协议

    1.  PoS：5.1，still allow anyone to join or leave the network and offer protection against Sybil attacks, but do not involve the energy consumption of proof of work. 

        by staking cryptocurrency as a security deposit.  node then becomes a validator, as opposed to a miner in proof-of-work systems.

        Proof-of-stake implementations typically assume that two-thirds of all staked tokens are held by honest participants, arguably a stronger assumption than the requirement in proof of work that a simple majority of participants are honest.

## 思路：论文对内容的组织和论证思路



## 方法：论文采取的论述方法



## 要点：论文介绍的重点/关键内容

1.  共识机制比较：4.2-5
2.  智能合约详细介绍：8

## 结论：论文得出了那些结论，产生哪些影响



## 对比：与其他文章在各个方面的对比和优缺点评价



## 名词表：

| English | 中文 |
| ------- | ---- |
| xxx     | xxx  |

