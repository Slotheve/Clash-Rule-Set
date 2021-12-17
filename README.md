#自用Clash Rule-Set规则


##proxy-group设置

```yaml
proxy-groups:
  - name: PROXY
    type: select
    proxies:
      -

  - name: Apple
    type: select
    proxies:
      - DIRECT
      - PROXY

  - name: GAME
    type: select
    proxies:
      - DIRECT
      - PROXY
```


##rule-providers设置

###白名单

```yaml
rule-providers:
  Apple:
    type: http
    behavior: classical
    url: "https://cdn.jsdelivr.net/gh/Slotheve/Clash-Rule-Set@release/Apple.txt"
    path: ./ruleset/Apple.yaml
    interval: 86400

  Proxy:
    type: http
    behavior: classical
    url: "https://cdn.jsdelivr.net/gh/Slotheve/Clash-Rule-Set@release/Proxy.txt"
    path: ./ruleset/Proxy.yaml
    interval: 86400

  Game:
    type: http
    behavior: classical
    url: "https://cdn.jsdelivr.net/gh/Slotheve/Clash-Rule-Set@release/Game.txt"
    path: ./ruleset/Game.yaml
    interval: 86400

  Direct:
    type: http
    behavior: classical
    url: "https://cdn.jsdelivr.net/gh/Slotheve/Clash-Rule-Set@release/Direct.txt"
    path: ./ruleset/Direct.yaml
    interval: 86400

  CNIP:
    type: http
    behavior: ipcidr
    url: "https://cdn.jsdelivr.net/gh/Slotheve/Clash-Rule-Set@release/CNIP.txt"
    path: ./ruleset/CNIP.yaml
    interval: 86400

  Apps:
    type: http
    behavior: classical
    url: "https://cdn.jsdelivr.net/gh/Slotheve/Clash-Rule-Set@release/Apps.txt"
    path: ./ruleset/Apps.yaml
    interval: 86400

```
```yaml
rule-providers:
  Apple:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/release/Apple.txt"
    path: ./ruleset/Apple.yaml
    interval: 86400

  Proxy:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/release/Proxy.txt"
    path: ./ruleset/Proxy.yaml
    interval: 86400

  Game:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/release/Game.txt"
    path: ./ruleset/Game.yaml
    interval: 86400

  Direct:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/release/Direct.txt"
    path: ./ruleset/Direct.yaml
    interval: 86400

  CNIP:
    type: http
    behavior: ipcidr
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/release/CNIP.txt"
    path: ./ruleset/CNIP.yaml
    interval: 86400

  Apps:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/release/Apps.txt"
    path: ./ruleset/Apps.yaml
    interval: 86400
  
```


##rules设置

###请按需自行更改

```yaml
rules:
  - RULE-SET,Apple,Apple
  - RULE-SET,Game,GAME
  - RULE-SET,Proxy,PROXY
  - RULE-SET,Apps,DIRECT
  - RULE-SET,Direct,DIRECT
  - RULE-SET,CNIP,DIRECT
  - GEOIP,CN,DIRECT
  - MATCH,PROXY
```
