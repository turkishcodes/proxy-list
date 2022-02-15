<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/jetkai/proxy-list?style=flat&logo=github
[contributors-url]: https://github.com/jetkai/proxy-list/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/jetkai/proxy-list?style=flat&logo=github
[forks-url]: https://github.com/jetkai/proxy-list/network/members
[stars-shield]: https://img.shields.io/github/stars/jetkai/proxy-list?style=flat&logo=github
[stars-url]: https://github.com/jetkai/proxy-list/stargazers
[issues-shield]: https://img.shields.io/github/issues/jetkai/proxy-list?style=flat&logo=github
[issues-url]: https://github.com/jetkai/proxy-list/issues
[license-shield]: https://img.shields.io/github/license/jetkai/proxy-list?style=flat&logo=github
[license-url]: https://github.com/jetkai/proxy-list/blob/main/LICENSE
[commit-shield]: https://img.shields.io/github/last-commit/jetkai/proxy-list?style=flat&logo=github
[commit-url]: https://github.com/jetkai/proxy-list/commits/main
[commit-activity]: https://img.shields.io/github/commit-activity/w/jetkai/proxy-list?style=flat&logo=github
[commit-activity-url]: https://github.com/jetkai/proxy-list/commits/main

# 🎁 SOCKS4/5 & HTTP/S PROXIES // ONLINE & READY

[![Commits][commit-shield]][commit-url]
[![Commits][commit-activity]][commit-activity-url]
[![Stargazers][stars-shield]][stars-url]
[![Forks][forks-shield]][forks-url]
[![Issues][issues-shield]][issues-url]

## 📰About This Project & The Proxies:
This repository contains a free list of tested SOCKS4/5 & HTTP/S proxies in -> **JSON**, **TXT**, **CSV**, **XML** & **YAML** format. No authentication is required when connecting to these proxies.

## 👩‍💻Proxy Testing:

These proxies are tested ~12x/day (every 2 hours) against EU/US hosting providers - **see below**, they have been verified to write & read data <**AT THE TIME OF TESTING**>.

**Hosting Provider**|**Country**|**Continent**
:-----:|:-----:|:-----:
OVH|France|EU
Amazon Web Services|United States|NA
Oracle Cloud|United Kingdom|EU
Microsoft Azure|Hong Kong|AS

[Source Code](https://github.com/jetkai/ProxyBuilder/blob/main/src/main/kotlin/spb/net/proxy/ProxyTester.kt)
```kotlin
    //SOCKS example (HTTP/S) is also supported
    private fun useSocksProxy(serverAddress: String?, serverPort: Int): ClientSocket? {
        val proxy = Proxy(Proxy.Type.SOCKS, InetSocketAddress(proxyAddress, proxyPort))
        val socket = Socket(proxy)
        if(socks4)
            forceSocks4(socket)
        try {
            socket.soTimeout = Constants.CONNECTION_TIMEOUT //3000ms
            socket.tcpNoDelay = true
            socket.connect(InetSocketAddress(serverAddress, serverPort), Constants.CONNECTION_TIMEOUT)
        } catch (e : IOException) {
            socket.close()
        }
        if(socket.isClosed)
            return null
        return ClientSocket().init(socket) //Read/Write Data Function
    }
```

## 📝Proxy Formatting:

These proxies are scraped from various sources & I compile this data using my [ProxyBuilder](https://github.com/jetkai/ProxyBuilder) application. Proxies are sorted from lowest to highest 0-255 & duplicated proxies are removed — the only exception is if an IP has a different port open, which is also a working proxy tunnel <**Less than 1% of the total proxies at the time of testing**>.

```IP:Port -> 1.0.132.249:4153```

## ✔Compatability:

Proxies work for any application that can establish a socket connection, such as... An application that has proxy support (FireFox, Chrome), or as an example, these Java Apps -> [JaySyiPker](https://github.com/JayArrowz/JaySyiPker), [Bruteforce-RSPS](https://github.com/jetkai/Bruteforce-RSPS) & [718 Cheat Client (Final)](https://github.com/jetkai/718-Cheat-Client-Final).

## 🔗ProxyList Links (Direct URL):

- _Online Proxies:_
    - **JSON** -> [proxies.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/json/proxies.json)
    - **TXT** -> [proxies.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies.txt)
    - **CSV** -> [proxies.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/csv/proxies.csv)
    - **XML** -> [proxies.xml](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/xml/proxies.xml)
    - **YAML** -> [proxies.yaml](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/yaml/proxies.yaml)
- _Online/Offline Proxies (Archive):_
  - **JSON** -> [working-proxies-history.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history.json)
  - **TXT** -> [working-proxies-history.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
  - **CSV** -> [working-proxies-history.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history.csv)
  - **XML** -> [working-proxies-history.xml](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/working-proxies-history.xml)
  - **YAML** -> [working-proxies-history.yaml](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/working-proxies-history.yaml)

## 🌍Geolocation & Graphs (Weekly):
Analytics are updated on a weekly basis and contains raw data, tables & graphs. 

You can view/download this data below.

**Query**|**Result**
:-----:|:-----:
Most Proxies By Country|Brazil (6749)
Most Detected Proxies By Country|Brazil (4680)
Most Proxies By Provider|Bharat Sanchar Nigam Ltd (2455)
Most Proxies By Port|5678 (33668)
Most Proxies By Protocol|SOCKS4 (44037)
Most Proxies By Continent|Asia (27864)

**Data Type**|**Link**
:-----:|:-----:
Graphs, Tables & Data (Excel) | [(analysis.xlsx)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xlsx/analysis.xlsx)
Raw Data (JSON) | [(archive-geo.json)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history-geo-beautify.json)
Raw Data (CSV) | [(archive-geo.csv)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history-geo.csv)
Raw Data (XML) | [(archive-geo.xml)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/working-proxies-history-geo.xml)
Raw Data (YAML) | [(archive-geo.yaml)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/working-proxies-history-geo.yaml)

![image](https://user-images.githubusercontent.com/26250917/135766207-17d4c531-2738-4209-808e-82c04b871331.png)


## Next Updates:

Further updates will be made to this project throughout the year, the next update I am working on will keep a record of proxy up-time, location, isp & speed.

---

# [SAMPLE PROXIES] - [February 15 2022 | 09:29:04]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 2719
   - **SOCKS5** -> 870
   - **HTTP** -> 1625
   - **HTTPS** -> 1218

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 6432
   - **Unique Online Proxies** -> 5707
   - **Unique Online/Offline Proxies (Archive)** -> 52053

## [SOCKS4 (2719/5707)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.0.157.49:4145
1.1.247.94:4145
1.2.194.103:3629
1.2.203.39:5678
1.4.214.148:5678
1.10.133.149:4145
1.10.141.220:37718
1.10.177.136:5678
1.20.95.95:5678
1.20.168.45:5678
1.20.235.153:5678
1.32.57.85:5678
1.53.137.84:4145
1.83.154.35:4145
1.179.130.201:4153
1.179.145.101:33109
1.179.151.165:31948
1.179.173.114:4153
1.179.186.69:1080
1.179.202.33:5678
1.186.40.9:39651
1.186.82.4:5678
1.234.44.179:37098
2.136.195.109:5678
2.139.162.80:4145
2.180.24.135:4153
2.183.8.145:4153
3.141.13.98:5678
3.144.165.41:5555
```

## [SOCKS5 (870/5707)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.13.165.87:8080
1.13.165.87:1080
1.15.182.239:7890
1.71.170.146:7302
3.22.167.115:48540
3.113.19.41:48540
3.144.99.13:38800
5.128.61.28:1080
5.128.73.5:1080
5.130.185.39:1080
5.136.140.95:1080
5.149.149.82:1080
5.188.181.170:3080
5.189.140.8:10439
8.44.216.242:13333
8.210.48.101:17380
8.218.44.70:54256
8.218.90.206:11536
13.231.43.108:48540
13.231.137.2:48540
13.231.180.246:48540
14.118.134.170:7302
14.136.204.35:1088
15.164.219.8:8118
20.114.87.37:1080
20.205.204.28:1080
23.94.149.131:53335
24.103.162.189:31337
24.249.199.4:4145
24.249.199.12:4145
```

## [HTTP (1625/5707)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.189.58:8080
1.1.220.100:8080
1.4.198.67:8081
1.13.165.87:8080
1.20.217.221:8080
1.117.231.98:8080
1.162.42.70:8080
1.179.136.98:8080
1.179.144.41:8080
1.179.148.9:55636
1.180.156.226:65001
1.186.40.35:1111
1.186.245.226:80
1.186.245.226:1111
3.20.236.208:49205
3.65.31.65:3128
5.9.103.181:8088
5.16.0.97:1256
5.16.7.213:1256
5.104.174.199:23500
5.131.243.252:8080
5.134.221.222:8080
5.149.219.201:8080
5.160.101.163:3128
8.208.91.118:8008
8.208.91.118:8081
8.208.91.118:8080
8.208.91.118:8800
8.210.48.101:17380
8.214.41.50:80
```

## [HTTPS (1218/5707)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.13.165.87:8080
1.180.156.226:65001
3.20.236.208:49205
3.215.177.148:49205
5.20.91.12:60792
5.104.174.199:23500
8.208.91.118:8000
8.208.91.118:80
8.208.91.118:8080
8.208.91.118:8081
8.214.41.50:80
13.59.34.132:443
14.1.102.53:8080
14.139.184.130:3128
14.143.168.230:8080
14.160.26.153:8080
14.160.32.23:8080
14.177.235.17:8080
14.207.59.105:8080
14.207.122.184:8080
15.235.132.138:8080
18.216.72.10:49205
18.222.17.49:49205
24.123.196.28:38200
27.72.149.205:8080
27.72.244.228:8080
27.116.51.119:6666
27.123.4.106:8181
27.150.27.133:10080
31.3.169.53:8081
```

## [ARCHIVE (5707/52053)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.42:4145
1.0.136.161:4145
1.0.136.168:4145
1.0.136.201:4145
1.0.136.222:4145
1.0.141.90:4145
1.0.145.246:4145
1.0.147.198:4145
1.0.148.132:4145
1.0.152.157:4145
1.0.154.141:4145
1.0.157.49:4145
1.0.161.151:4153
1.0.162.24:4145
1.0.162.181:4145
1.0.163.17:4145
1.0.163.85:4145
1.0.163.172:8081
1.0.170.50:8080
1.0.170.50:80
1.0.173.104:4145
1.0.174.87:4145
1.0.190.19:4145
1.0.191.138:4153
1.0.205.87:8080
1.0.209.187:8080
1.0.212.247:4145
```



Thx Co Pure Gs - Sort Meister! 💟