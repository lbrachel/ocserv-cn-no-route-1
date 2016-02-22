# ocserv-cn-no-route

## �a���^��

1���������¹���IP�б�chnroute.txt

```
wget -N http://ftp.afrinic.net/pub/stats/afrinic/delegated-afrinic-extended-latest
wget -N http://ftp.apnic.net/apnic/stats/apnic/delegated-apnic-extended-latest
wget -N http://ftp.arin.net/pub/stats/arin/delegated-arin-extended-latest
wget -N http://ftp.lacnic.net/pub/stats/lacnic/delegated-lacnic-extended-latest
wget -N http://ftp.ripe.net/pub/stats/ripencc/delegated-ripencc-extended-latest
cat delegated-afrinic-extended-latest delegated-apnic-extended-latest delegated-arin-extended-latest delegated-lacnic-extended-latest delegated-ripencc-extended-latest>>delegated-all-latest
cat delegated-all-latest | grep ipv4 | grep CN | awk -F\| '{ printf("%s/%d\n", $4, 32-log($5)/log(2)) }' >chnroute.txt
```

2���ϲ�chnroute.txt(336902912 IPs)������chnroute_merged.txt(336902912 IPs)

3��������/12�����ϸĳ�/11�����ϲ�������11_143.txt(713031680 IPs)

4�����ɲ�������IP��cn-no-route1.txt(712965888 IPs)

�޳�11_143.txt�б���IP��192.168.0.0/16��203.0.113.0/24

5�����ӱ���IP���ϲ�������cn-no-route2.txt(1305674752 IPs)

192.168.0.0/24�赥�У�����Windows�ͻ���192.168.x.x�����޷����ա�

## ע�����

1��0.10.5 ��֮ǰ�汾ocserv��Ҫ�޸�src/vpn.h��֧�ֳ���96��(ocservĬ��ֵ)��������200��(Cisco AnyConnect���ֵ)��·�ɱ�:

```
#define MAX_CONFIG_ENTRIES 96
```

96��Ϊ200����

0.10.6 ��֮��汾ocserv����Ҫ�޸ģ��ο�[https://gitlab.com/ocserv/ocserv/issues/17](https://gitlab.com/ocserv/ocserv/issues/17)

2������[Cisco�ٷ��ĵ�](http://www.cisco.com/c/en/us/products/collateral/security/ios-sslvpn/prod_white_paper0900aecd80512071.html)��no-route��route����ͬʱʹ�á�

```
You can specify either split-include or split-exclude, but you cannot specify both options.
```

## Q&A

Ϊʲôѡ������/12�����ϸĳ�/11�������ǽ�����/13�����ϸĳ�/12������/11�����ϸĳ�/10��

* ������/13�����ϸĳ�/12���t��������IP��·�ɱ���261�l(580911104 IPs)�����^�˿͑������Ƶ����200�l��
* ������/12�����ϸĳ�/11���t��������IP��·�ɱ���143�l(713031680 IPs)��
* ������/11�����ϸĳ�/10���t��������IP��·�ɱ���69�l(847249408 IPs)��IP�����Mһ���U���`���Mһ���U��

## [����IP](http://en.wikipedia.org/wiki/Reserved_IP_addresses) (592708864 IPs)
```
0.0.0.0/8
10.0.0.0/8
100.64.0.0/10
127.0.0.0/8
169.254.0.0/16
172.16.0.0/12
192.0.0.0/24
192.0.2.0/24
192.88.99.0/24
192.168.0.0/16
198.18.0.0/15
198.51.100.0/24
203.0.113.0/24
224.0.0.0/4
240.0.0.0/4
255.255.255.255/32
```

##ԭ����������
```
52.80.0.0/14
54.222.0.0/15
91.234.36.0/24
137.59.88.0/22
152.104.128.0/17
159.226.0.0/16
161.207.0.0/16
162.105.0.0/16
166.111.0.0/16
168.160.0.0/16
170.179.0.0/16
47.92.0.0/14
47.96.0.0/11
192.124.154.0/24
192.188.170.0/24
40.72.0.0/15
40.125.128.0/17
40.126.64.0/18
167.139.0.0/16
167.189.0.0/16
167.220.244.0/22
144.0.0.0/16
144.7.0.0/16
144.12.0.0/16
144.52.0.0/16
144.123.0.0/16
144.255.0.0/16
211.64.0.0/13
211.80.0.0/12
211.96.0.0/13
211.136.0.0/13
211.144.0.0/12
211.160.0.0/13
157.0.0.0/16
157.18.0.0/16
157.61.0.0/16
157.122.0.0/16
157.148.0.0/16
157.156.0.0/16
157.255.0.0/16
```