本程序用于sana挖矿，支持没有sgx和tee功能的电脑挖矿，产量和tee模式基本相同，稍有差别可能是因为设备配置高低问题

##使用方法
首先要会sana正常挖矿流程 rpc,配置ant.yaml等等

##a.程序方式

在程序目录中运行
```
sudo ./sanatee start --verbosity 5 --full-node --config /root/ant.yaml --debug-api-enable
```


#b.docker方式
1.先要注册
  ./sanatee start --data-dir=你的节点目录 --password=你的密码
  获取到ethereum address 给我，我给你授权码和机器码
  会在你的keys目录同级生成一个mykeys目录，里面有两个文件device.key和hahano.key,这些文件和你的key一起保存，这样下次就可以直接使用

2.使用docker导入功能导入docker 包
docker load -i ./sanatee0.1.3.tar

3.使用docker 重新建立容器


docker run -d --restart=always -p 1763:1633 -p 1764:1634 -p 1765:1635 -v /root/ant.yaml:/root/ant.yaml -v /data/013:/home/ant  --name sana-013 sana/tee:v0.1.3.1019 start --verbosity 5 --full-node --config /root/ant.yaml --debug-api-enable

