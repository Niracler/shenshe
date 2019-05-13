# shenshe
一个极其简单的琉璃神社的爬虫


### 效果

![](images/header.png)

### 安装依赖包

```sh
pip install --upgrade pip

pip install -r requirements.txt
```

### 用例

```sh
cd shenshe/

scrapy crawl Shenshe
```

### centos7 关闭防火墙

关闭
```bash
$systemctl stop firewalld.service
```

禁止开机启动
```bash
$systemctl disable firewalld.service
```

### 使用虚拟环境

```bash
source venv/bin/activate
```

### 对 docker 节点打标签

```bash
$docker node update --label-add spider-role=crawler node1
```

### 添加hosts

```bash
$echo "172.28.7.40 inner.registry" >> /etc/hosts
```

```bash
tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": [
  "https://kfwkfulq.mirror.aliyuncs.com",
  "https://2lqq34jg.mirror.aliyuncs.com",
  "https://pee6w651.mirror.aliyuncs.com"
  ],
  "insecure-registries" : ["127.0.0.0/8","192.168.0.0/16","172.16.0.0/12","10.0.0.0/8"]
}
EOF
```

```bash
systemctl restart docker
```

## 参考文章

- [使用 Docker Swarm 搭建分布式爬虫集群](https://www.kingname.info/2018/10/13/use-docker-swarm/)
- [分布式网络数据抓取系统设计与实现](https://www.jianshu.com/p/fb028ad74798)
- [分布式爬虫的部署之Scrapyd分布式部署](https://juejin.im/post/5b0e1a8ff265da092100709f)
- [scrapy-redis](https://github.com/rmax/scrapy-redis)
- [小白进阶之Scrapy第三篇（基于Scrapy-Redis的分布式以及cookies池）](https://cuiqingcai.com/4048.html)
- [如何简单高效地部署和监控分布式爬虫项目](https://juejin.im/post/5bebc5fd6fb9a04a053f3a0e)