# eureka-server-cluster
Eureka Server Cluster

# deploy cluster
3台eureka server组成高可用注册中心

## node1
    vim /etc/hosts
### 增加
    node2-ip eureka-cluster-node2
    node3-ip eureka-cluster-node3
### 启动
    java -jar eureka-server-cluster.jar --spring.profiles.active=node1

## node2
    vim /etc/hosts
### 增加
    node1-ip eureka-cluster-node1
    node3-ip eureka-cluster-node3
### 启动
    java -jar eureka-server-cluster.jar --spring.profiles.active=node2

## node3
    vim /etc/hosts
### 增加
    node1-ip eureka-cluster-node1
    node3-ip eureka-cluster-node2
### 启动
    java -jar eureka-server-cluster.jar --spring.profiles.active=node3
