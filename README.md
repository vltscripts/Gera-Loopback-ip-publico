# Gera-Loopback-ip-publico
 Este script cria de forma automatica as loopback para ips publicos, nomeadas de "Loopback-0" a "Loopback-254". Em seguida, atribui endereços IP a essas interfaces na faixa de "111.111.111.0" a "111.111.111.254".   /interface bridge  :for i from=0 to=254 do={ add protocol-mode=none name=("Loopback-" . $i . "") } :delay 2s;  /ip address  :for i from=0 to=254 do={ add interface=("Loopback-" . $i . "") address=("111.111.111." . $i ."") }  Se for blocos menores é só modificar por exemplo " from=0 to=64 " dos scritps do que gera as /interface bridge e a do /ip address e colocar o Ip Publico em  address=("111.111.111." . $i ."").
