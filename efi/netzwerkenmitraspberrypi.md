## Netzwerken mit RaspberryPi

### Vorbereitendes

`sudo apt-get update`<br>
`sudo apt-get upgrade`<br>
`sudo apt-get install hostapd`<br>
`sudo apt-get install dnsmasq`<br>
`sudo systemctl stop hostapd`<br>
`sudo systemctl stop dnsmasq`<br>

### Hostapd Konfiguration

`sudo nano /etc/hostapd/hostapd.conf`
<br>
````
interface=wlan0
driver=nl80211
ssid=PiX
hw_mode=g
channel=6
wmm_enabled=0
macaddr_acl=0
auth_algs=1
ignore_broadcast_ssid=0
wpa=2
wpa_passphrase=QWERTZUIOP
wpa_key_mgmt=WPA-PSK
wpa_pairwise=TKIP
rsn_pairwise=CCMP
````

`sudo nano /etc/default/hostapd`
<br>
Change `#DAEMON_CONF=""` to `DAEMON_CONF="/etc/hostapd/hostapd.conf"`

Activate hostapd:<br>
`sudo systemctl unmask hostapd`<br>
`sudo systemctl enable hostapd`<br>
`sudo systemctl start hostapd`<br>

### IP-Forwarding einschalten

`sudo nano /etc/sysctl.conf`
<br>
`#`vor `#net.ipv4.ip_forward=1` entfernen<br>
`sudo reboot`

### Statische IP-Adressen definieren

`sudo nano /etc/dhcpcd.conf`
<br>
Zuunterst folgende Zeilen hinzufügen (x mit Gruppennummer ersetzen):

````
interface wlan0
 static ip_address=192.168.x.1/24
 nohookup wpa_supplicant

interface eth0
 static ip_address=192.168.10.x
````

`sudo service dhcpcd restart`

### DHCP konfigurieren

`sudo systemctl stop dnsmasq`<br>
`sudo mv /etc/dnsmasq.conf /etc/dnsmasq.conf.orig`<br>
`sudo nano /etc/dnsmasq.conf`<br>
Folgende Zeilen hinzufügen (x mit Gruppennummer ersetzen):
````
interface=wlan0
 dhcp-range=192.168.x.2,192.168.x.30,255.255.255.0,24h
````

`sudo systemctl start dnsmasq`

### NAT & Masquerade

`sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE`

### Routing-Tabelle

`ip route show`
`sudo ip route add 192.168.2.0/24 via 192.168.10.2`