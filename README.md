# volodyazetkin
а теперь сюда)))
https://seraphim.gitbook.io/volodyazetkin2024gitbook
Включаем IP Forwarding в Linux
По умолчанию в большинстве дистрибутивов IP Forwarding выключен, но форвардинг может понадобится если на сервере будет подниматься VPN или например это будет роутер.

Проверить включен ли IP Forwarding можно так:

Shell

0
1
2
3
4
 
sysctl net.ipv4.ip_forward
cat /proc/sys/net/ipv4/ip_forward
 
 
Включить можно так (действовать будет до перезагрузки):

Shell

0
1
2
3
 
sysctl -w net.ipv4.ip_forward=1
 
 
 или

Shell

0
1
2
3
 
echo 1 > /proc/sys/net/ipv4/ip_forward
 
 
Постоянное включение:

Shell

0
1
2
3
4
 
# grep forward /etc/sysctl.conf
net.ipv4.ip_forward = 1
 
 
После правок необходимо перезапустить сеть. например /etc/init.d/networking restart