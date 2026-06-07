# Commands Used – CSO7018 Lab Assessment

## Lab validation

```bash
ip a
ping -c 4 192.168.56.103
sudo systemctl status ssh
sudo systemctl status apache2
```

## Service discovery

```bash
nmap -sV 192.168.56.103
ss -tulnp | grep -E ':22 |:80 '
```

## SSH testing

```bash
ssh student@192.168.56.103
ssh testuser@192.168.56.103
hydra -l testuser -P passwords.txt ssh://192.168.56.103 -t 1
journalctl -u ssh --no-pager | tail -30
```

## Apache enumeration

```bash
curl -I http://192.168.56.103
nikto -h http://192.168.56.103
dirb http://192.168.56.103
sudo tail -n 50 /var/log/apache2/access.log
sudo tail -n 50 /var/log/apache2/error.log
```

## Apache hardening

```bash
sudo cp /etc/apache2/conf-available/security.conf /etc/apache2/conf-available/security.conf.bak
sudo nano /etc/apache2/conf-available/security.conf
sudo a2enmod headers
sudo nano /etc/apache2/conf-available/custom-security.conf
sudo a2enconf custom-security
sudo apache2ctl configtest
sudo systemctl restart apache2
curl -I http://192.168.56.103
nikto -h http://192.168.56.103
```

## Fail2Ban and SSH mitigation

```bash
sudo passwd testuser
sudo chage -l testuser
sudo apt install fail2ban -y
sudo systemctl enable --now fail2ban
sudo systemctl status fail2ban
sudo fail2ban-client status
sudo fail2ban-client status sshd
hydra -l testuser -P passwords.txt ssh://192.168.56.103 -t 1
```
