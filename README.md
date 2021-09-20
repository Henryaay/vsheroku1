# heroku-vless
## Deploy VLESS server to heroku
## 请使用者保持低调，免费的资源已所剩无几
## https://dashboard.heroku.com/new?template=https://github.com/xxx/vless-heroku.git Fork本项目之后将xxx改成自己的名字，非常重要，切记！！！！
## 禁止在任何网站宣传本项目！！！！
## 带有删除线的部分表示不适用或已经废弃

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/Henryaay/vsheroku1.git)

# VLESS Client Setup

| Connection Variables | Values |
| -------------------- | ------ |
| `Address` | yourAppName.herokuapp.com </br> Cloudflare Reverse Proxy IP |
| `SNI` | none |
| `AllowInsecure` | false |
| `Port` | 443 |
| `Host` | yourAppName.herokuapp.com </br> Cloudflare Reverse Proxy Domain Name |
| `Path` | /$ID-vless |
| `id` | Generate using UUID generator or V2RayN/V2RayNG client generate </br> [uuidgenerator](https://www.uuidgenerator.net/) |
| `Flow` | none |
| `encryption` | none |
| `Transport` | ws |
| `Tls` | Tls must open, otherwise your network was insecure! |

# Cloudflare Reverse Proxy Code (Choose one from both examples)

example 1
```
addEventListener(
  "fetch", event => {
    let url = new URL(event.request.url);
    url.host = "appname.herokuapp.com";
    let request = new Request(url, event.request);
    event.respondWith(
      fetch(request)
    )
  }
)
```

example 2 (recommend)
```
const SingleDay = 'appname.herokuapp.com'
const DoubleDay = 'appname.herokuapp.com'
addEventListener(
    "fetch",event => {
    
        let nd = new Date();
        if (nd.getDate()%2) {
            host = SingleDay
        } else {
            host = DoubleDay
        }
        
        let url=new URL(event.request.url);
        url.hostname=host;
        let request=new Request(url,event.request);
        event. respondWith(
            fetch(request)
        )
    }
)
```

# Caddyindexpage (Welcome to Pull Requests)
Select the link address you like and copy it as the variable CADDYIndexPage variable value
| Number | Address |
| ------ | ------- |
| 1(default) | [Welcome to caddy page](https://raw.githubusercontent.com/caddyserver/dist/master/welcome/index.html) |
| 2 | [3DCEList Periodic Table of Elements](https://github.com/wulabing/3DCEList/archive/master.zip) |
| 3 | [Spotify-Landing-Page-Redesign](https://github.com/WebDevSimplified/Spotify-Landing-Page-Redesign/archive/master.zip) |
| 4 | [dev-landing-page](https://github.com/flexdinesh/dev-landing-page/archive/master.zip) |
| 5 | [free-for-dev](https://github.com/ripienaar/free-for-dev/archive/master.zip) |
| 6 | [tailwindtoolbox-Landing-Page](https://github.com/tailwindtoolbox/Landing-Page/archive/master.zip) |
| 7 | [sandhikagalih/simple-landing-page](https://github.com/sandhikagalih/simple-landing-page/archive/master.zip) |
| 8 | [StartBootstrap/startbootstrap-new-age](https://github.com/StartBootstrap/startbootstrap-new-age/archive/master.zip) |
| 9 | [mikutap A fun page with music](https://github.com/AYJCSGM/mikutap/archive/master.zip) [demo](https://aidn.jp/mikutap) |
| 10 | [WebGL Fluid simulation](https://github.com/PavelDoGreat/WebGL-Fluid-Simulation/archive/master.zip) [demo](https://paveldogreat.github.io/WebGL-Fluid-Simulation/) |
| 11 | [loruki-website](https://github.com/bradtraversy/loruki-website/archive/master.zip) |
| 12 | [bongo.cat A musical cat](https://github.com/Externalizable/bongo.cat/archive/master.zip) [demo](https://bongo.cat/) |

# New Features

Xray已经2个月没更新，回退到V2ray. (2021.8.18)

# 重要信息

新用户只需要修改id和Caddy主页配置即可

不熟悉caddy配置的不要修改caddy配置

严禁滥用，因滥用出现的所有问题本人概不负责，且用且珍惜！

本项目不宜做为长期翻墙使用。

出于安全考量，请使用cdn，不要使用自定义域名，以实现VLESS+WS+TLS。

禁止在任何网站宣传本项目！！！！

