# aliddns-ipv6
自动解析IPv6到域名，以群晖系统为例


# 【1】修改以下4个的值
aliddnsipv6_ak="xxxxgn7a"
aliddnsipv6_sk="xxxiUSOl"
aliddnsipv6_name1='dsm3617'
aliddnsipv6_domain='xxx.com'


# 【2】ssh登录群晖,ip addr查询【网络接口名称"ovs_eth0"】,【关键词"inet6.*global"】以及【print $2】、【print $1】；
# 可以先自己在ssh里试着用命令运行【ip addr show ovs_eth0 | grep "2409.*global"】该关键词是否能正确过滤出你想要的结果；
# 该*.sh文件 推荐使用bash运行。
# ipv6s=`ip addr show ovs_eth0 | grep "inet6.*global" | awk '{print $2}' | awk -F"/" '{print $1}'` || die "$ipv6"
ipv6s=`ip addr show ovs_eth0 | grep "2409.*global" | awk '{print $2}' | awk -F"/" '{print $1}'` || die "$ipv6"

