```shell
做一个导图，并调用 part 1 的合约等（结合最后一部分的合约调用，要完全搞懂 fabric 了）

# fq

# git config socks5

商业票据教程

# 更新 nodejs 

curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
apt-get install -y nodejs
npm config set registry http://registry.npm.taobao.org
npm install npm@latest -g

# 试一试 nvm https://github.com/nvm-sh/nvm

apt-get install gcc g++ make

# 安装 yarn，也可不安

curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
     echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
apt-get update && apt-get install yarn

# 建议全局，要加 --unsafe-perm
npm install -g fabric-network --unsafe-perm
# 非全局
# npm install fabric-network
---

# 修改重新部署 fabric-samples

cd ~/Project/fabric-samples/commercial-paper
dos2unix ./*
chmod +x ./*

# 修改脚本，bash，并删去 down

nano network-starter.sh
nano network-clean.sh
# 如果发生错误，hosts 改成
bash network-starter.sh
# 查看所有 fabric 节点

docker ps

# 所有这些容器构成了被称作 net_test 的 docker 网络。使用 docker network 命令查看该网络信息

docker network inspect net_test

---

cd ~/Project/fabric-samples/commercial-paper/organization/magnetocorp

# 观察 net_test 网络状态，无输出并不是卡住了，此终端此时用于监测 net_test 状态

bash ./configuration/cli/monitordocker.sh net_test 1998

# 打开另一个终端 + 远程调试

cd ~/Project/fabric-samples/commercial-paper/organization/magnetocorp
source magnetocorp.sh
peer lifecycle chaincode package cp.tar.gz --lang node --path ./contract --label cp_0
peer lifecycle chaincode install cp.tar.gz
peer lifecycle chaincode queryinstalled
export PACKAGE_ID=cp_0:ffda93e26b183e231b7e9d5051e1ee7ca47fbf24f00a8376ec54120b1a2a335c
peer lifecycle chaincode approveformyorg --orderer localhost:7050 --ordererTLSHostnameOverride orderer.example.com --channelID mychannel --name papercontract -v 0 --package-id $PACKAGE_ID --sequence 1 --tls --cafile $ORDERER_CA

# 安装另一个公司的链码
cd ~/Project/fabric-samples/commercial-paper/organization/digibank/
peer lifecycle chaincode package cp.tar.gz --lang node --path ./contract --label cp_0
peer lifecycle chaincode install cp.tar.gz
peer lifecycle chaincode queryinstalled
peer lifecycle chaincode approveformyorg --orderer localhost:7050 --ordererTLSHostnameOverride orderer.example.com --channelID mychannel --name papercontract -v 0 --package-id $PACKAGE_ID --sequence 1 --tls --cafile $ORDERER_CA

peer lifecycle chaincode commit -o localhost:7050 --ordererTLSHostnameOverride orderer.example.com --peerAddresses localhost:7051 --tlsRootCertFiles ${PEER0_ORG1_CA} --peerAddresses localhost:9051 --tlsRootCertFiles ${PEER0_ORG2_CA} --channelID mychannel --name papercontract -v 0 --sequence 1 --tls --cafile $ORDERER_CA --waitForEvent
docker ps
cd ~/Project/fabric-samples/commercial-paper/organization/magnetocorp/application/
```

