# openwrt-adfree
Скрипт генерации hosts.txt на роутерах с OpenWRT для блокировки рекламы. Этот способ позволяет избавиться от рекламы на **ВСЕХ** устройствах без установки дополнительных плагинов.

В консоле на роутере:
```sh
root@OpenWrt:~# scp openwrt-adfree root@192.168.1.1:~
root@OpenWrt:~# echo '0 4 * * * /root/openwrt-adfree' >> /etc/crontabs/root
root@OpenWrt:~# /etc/init.d/cron enable
```

В файле **/etc/config/dhcp** добавить строку:
```
config dnsmasq
    ...
    list addnhosts '/tmp/openwrt-adfree'
```

Наслаждаемся!
