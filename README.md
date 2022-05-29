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

# [SAMPLE PROXIES] - [May 29 2022 | 02:09:58]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1014
   - **SOCKS5** -> 301
   - **HTTP** -> 661
   - **HTTPS** -> 561

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 2001
   - **Unique Online Proxies** -> 2001
   - **Unique Online/Offline Proxies (Archive)** -> 4482

## [SOCKS4 (1014/2001)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.20.137.82:32241
1.20.184.75:4153
1.32.57.85:5678
1.55.241.4:4145
1.186.40.157:39651
1.186.85.74:5678
1.255.226.232:26680
3.120.173.144:8080
3.131.207.170:13343
3.141.13.98:5678
3.211.17.212:80
5.44.254.40:4145
5.58.47.25:3629
5.139.58.214:4145
5.160.81.157:4145
5.161.93.53:1080
5.172.188.90:5678
5.201.178.102:5678
8.40.133.10:1099
8.42.68.49:39593
8.42.68.85:39593
8.42.68.97:39593
8.136.192.43:80
8.210.210.94:27832
8.218.69.97:8000
8.218.109.21:443
12.11.59.114:1080
12.151.56.30:80
12.158.87.26:39593
13.58.88.184:5678
```

## [SOCKS5 (301/2001)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
3.19.179.179:8000
3.120.173.144:8080
3.131.207.170:13343
3.211.17.212:80
5.161.86.206:1080
5.161.93.53:1080
5.161.100.145:1080
5.189.229.42:1080
8.136.192.43:80
8.218.69.97:8000
8.218.109.21:443
12.151.56.30:80
18.206.33.119:8888
20.222.136.61:8000
20.230.193.232:80
20.239.2.157:80
23.94.30.107:1088
24.249.199.4:4145
24.249.199.12:4145
27.116.51.119:6667
27.116.51.186:6667
27.128.196.205:7302
27.128.206.18:7302
31.128.248.1:1080
31.128.248.2:1080
35.244.6.175:1080
36.7.108.56:9091
36.35.240.26:7302
37.18.73.60:5566
37.131.202.95:33427
```

## [HTTP (661/2001)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.20.209.28:8080
1.186.85.38:1111
2.188.164.194:8080
3.19.179.179:8000
3.20.236.208:49205
3.215.177.148:49205
5.16.0.77:1256
5.16.0.97:1256
5.59.136.230:8080
5.131.243.10:8080
5.135.176.161:10000
5.167.141.239:3128
8.208.91.118:8888
12.31.246.5:8080
14.1.102.41:3127
14.160.29.90:8080
14.207.19.36:8080
14.241.225.134:443
18.222.17.49:49205
20.222.136.61:8000
24.72.171.214:8080
24.106.221.230:53281
24.172.34.114:49920
27.111.45.25:55443
27.116.51.119:6667
27.131.179.197:10443
27.255.58.74:8080
34.229.130.62:49205
34.230.89.25:49205
35.214.170.66:3128
```

## [HTTPS (561/2001)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.186.85.38:1111
2.188.164.194:8080
3.20.236.208:49205
3.215.177.148:49205
5.16.0.174:8080
5.35.82.110:32132
5.135.176.161:10000
5.149.219.201:8080
5.167.141.239:3128
14.1.102.41:3127
14.170.154.10:8080
14.192.2.161:83
18.222.17.49:49205
20.113.24.12:8080
24.106.221.230:53281
24.172.34.114:49920
27.72.88.64:8080
27.116.51.119:6667
27.131.179.197:10443
27.147.209.215:8080
34.229.130.62:49205
34.230.89.25:49205
36.37.160.242:8080
36.66.43.65:8080
36.66.172.121:39810
36.67.152.213:11111
36.67.253.59:31178
36.91.45.10:51672
36.91.68.150:8080
36.91.133.49:10000
```

## [ARCHIVE (2001/4482)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.170.50:80
1.4.214.148:5678
1.9.167.35:60489
1.9.167.36:60489
1.10.133.211:4145
1.20.96.30:4153
1.20.96.164:4153
1.20.137.82:32241
1.20.184.75:4153
1.20.209.28:8080
1.20.220.79:4145
1.32.57.85:5678
1.55.241.4:4145
1.179.130.201:4153
1.179.144.41:8080
1.179.148.9:36476
1.179.151.165:31948
1.179.186.70:1080
1.186.40.9:39651
1.186.40.157:39651
1.186.85.2:1111
1.186.85.38:1111
1.186.85.74:5678
1.186.213.67:5678
1.212.157.115:4145
1.255.226.232:26680
2.57.8.76:4153
```



Thx Co Pure Gs - Sort Meister! 💟