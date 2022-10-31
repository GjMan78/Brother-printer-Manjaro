# Brother-printer-Manjaro
How to install a wireless brother printer on Manjaro Linux

pamac install manjaro-printer

sudo gpasswd -a yourusername sys

sudo systemctl enable --now cups.service

sudo systemctl enable --now cups.socket

sudo systemctl enable --now cups.path

pamac install avahi
sudo systemctl enable --now avahi-daemon.service

Install printer firmware from AUR, in my case:

pamac build brother-dcpj1200w

Restart cups

sudo systemctl restart cups.service

Finally add printer 

lpadmin -p DCPJ1200W -E -v ipp://192.168.1.2/ipp/print -m everywhere 

Scanner

pamac build brscan4
