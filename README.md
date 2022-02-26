自用Clash Rule-Set规则

#dns请自行设置

#以下为配置文件
```yaml
port: 7890
socks-port: 7891
allow-lan: true
mode: Rule
log-level: info
external-controller: :9090
fallback-filter:
  geoip: true
proxies:
- name: 
  server: 
  port: 
  type: trojan #此节点为trojan-go
  password: 
  network: ws
  sni: 
  skip-cert-verify: true
  udp: true
  ws-opts:
   path: 
   headers:
     Host:
- name: "vmess"
    type: vmess
    server: 
    port: 
    uuid: 
    alterId: 32
    cipher: auto
    udp: true
    tls: true
    skip-cert-verify: true
    servername: 
    network: ws
    ws-opts:
      path: 
      headers:
        Host: 
proxy-groups:
  - name: PROXY
    type: select
    proxies:
      - 
      - DIRECT

rule-providers:
  Microsoft:
    type: http
    behavior: domain
    url: "https://gitee.com/tangjihan/Clash-Rule-Set/raw/master/Rules/Microsoft.txt"
    path: ./ruleset/Microsoft.yaml
    interval: 86400

  Apple:
    type: http
    behavior: domain
    url: "https://gitee.com/tangjihan/Clash-Rule-Set/raw/master/Rules/Apple.txt"
    path: ./ruleset/Apple.yaml
    interval: 86400

  Game:
    type: http
    behavior: domain
    url: "https://gitee.com/tangjihan/Clash-Rule-Set/raw/master/Rules/Game.txt"
    path: ./ruleset/Game.yaml
    interval: 86400
    
  Bilibili:
    type: http
    behavior: domain
    url: "https://gitee.com/tangjihan/Clash-Rule-Set/raw/master/Rules/Bilibili.txt"
    path: ./ruleset/Bilibili.yaml
    interval: 86400

  Direct:
    type: http
    behavior: domain
    url: "https://gitee.com/tangjihan/Clash-Rule-Set/raw/master/Rules/Direct.txt"
    path: ./ruleset/Direct.yaml
    interval: 86400

  CNIP:
    type: http
    behavior: ipcidr
    url: "https://gitee.com/tangjihan/Clash-Rule-Set/raw/master/Rules/CNIP.txt"
    path: ./ruleset/CNIP.yaml
    interval: 86400

  Process:
    type: http
    behavior: classical
    url: "https://gitee.com/tangjihan/Clash-Rule-Set/raw/master/Rules/Process.txt"
    path: ./ruleset/Process.yaml
    interval: 86400

  Proxy:
    type: http
    behavior: domain
    url: "https://gitee.com/tangjihan/Clash-Rule-Set/raw/master/Rules/Proxy.txt"
    path: ./ruleset/Proxy.yaml
    interval: 86400
    
  TGIP:
    type: http
    behavior: ipcidr
    url: "https://gitee.com/tangjihan/Clash-Rule-Set/raw/master/Rules/TGIP.txt"
    path: ./ruleset/TGIP.yaml
    interval: 86400

rules:
  - RULE-SET,Microsoft,Microsoft
  - RULE-SET,Apple,Apple
  - RULE-SET,Game,Game
  - RULE-SET,Bilibili,Bilibili
  - RULE-SET,Proxy,PROXY
  - RULE-SET,Process,DIRECT
  - RULE-SET,CNIP,DIRECT
  - RULE-SET,Direct,DIRECT
  - GEOIP,CN,DIRECT
  - MATCH,PROXY
  ```yaml
