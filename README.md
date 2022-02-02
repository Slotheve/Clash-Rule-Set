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
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/master/Rules/Apple.txt"
    path: ./ruleset/Apple.yaml
    interval: 86400

  Game:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/master/Rules/Game.txt"
    path: ./ruleset/Game.yaml
    interval: 86400

  Direct:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/master/Rules/Direct.txt"
    path: ./ruleset/Direct.yaml
    interval: 86400

  Direct-IP:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/master/Rules/Direct-IP.txt"
    path: ./ruleset/Direct-IP.yaml
    interval: 86400

  Process:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/master/Rules/Process.txt"
    path: ./ruleset/Process.yaml
    interval: 86400

```
```yaml
rule-providers:
  Apple:
    type: http
    behavior: classical
    url: "https://cdn.jsdelivr.net/gh/Slotheve/Clash-Rule-Set@master/Rules/Apple.txt"
    path: ./ruleset/Apple.yaml
    interval: 86400

  Game:
    type: http
    behavior: classical
    url: "https://cdn.jsdelivr.net/gh/Slotheve/Clash-Rule-Set@master/Rules/Game.txt"
    path: ./ruleset/Game.yaml
    interval: 86400

  Direct:
    type: http
    behavior: classical
    url: "https://cdn.jsdelivr.net/gh/Slotheve/Clash-Rule-Set@master/Rules/Direct.txt"
    path: ./ruleset/Direct.yaml
    interval: 86400

  Direct-IP:
    type: http
    behavior: classical
    url: "https://cdn.jsdelivr.net/gh/Slotheve/Clash-Rule-Set@master/Rules/Direct-IP.txt"
    path: ./ruleset/Direct-IP.yaml
    interval: 86400

  Process:
    type: http
    behavior: classical
    url: "https://cdn.jsdelivr.net/gh/Slotheve/Clash-Rule-Set@master/Rules/Process.txt"
    path: ./ruleset/Process.yaml
    interval: 86400
  
```


##rules设置

###请按需自行更改

```yaml
rules:
  - RULE-SET,Apple,Apple
  - RULE-SET,Game,GAME
  - RULE-SET,Process,DIRECT
  - RULE-SET,Direct-IP,DIRECT
  - RULE-SET,Direct,DIRECT
  - GEOIP,CN,DIRECT
  - MATCH,PROXY
```
