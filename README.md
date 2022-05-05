自用Clash Rule-Set规则

#dns请自行设置

#以下为配置文件
```yaml
proxies:
- name: ss
  server: 
  port: 
  type: ss  (建议搭配中转机,延迟低速度快安全性高)
  cipher: aes-256-gcm
  password: 
  udp: true
- name: 
  server: 
  port: 
  type: trojan #此节点为trojan-go(ws自选)
  password: 
  sni: 
  skip-cert-verify: true
  udp: true
  network: tcp # OR (ws)
  #ws-opts:
   #path: 
   #headers:
     #Host:
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
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/master/Rules/Microsoft.txt"
    path: ./ruleset/Microsoft.yaml
    interval: 86400

  Apple:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/master/Rules/Apple.txt"
    path: ./ruleset/Apple.yaml
    interval: 86400

  Game:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/master/Rules/Game.txt"
    path: ./ruleset/Game.yaml
    interval: 86400

  Direct:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/master/Rules/Direct.txt"
    path: ./ruleset/Direct.yaml
    interval: 86400

  Proxy:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Slotheve/Clash-Rule-Set/master/Rules/Proxy.txt"
    path: ./ruleset/Proxy.yaml
    interval: 86400

rules:
  - RULE-SET,Microsoft,Microsoft
  - RULE-SET,Apple,Apple
  - RULE-SET,Game,Game
  - RULE-SET,Proxy,PROXY
  - RULE-SET,Direct,DIRECT
  - GEOIP,CN,DIRECT,no-resolve
  - MATCH,PROXY
  ```yaml
