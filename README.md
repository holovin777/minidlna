# minidlna
Cheat sheet instal MiniDLNA server

```bash
sudo pacman -S minidlna
sudo vim /etc/minidlna.conf
```
```python
#network_interface=eth0                         # Self-discovers if commented (at times necessary to set)
media_dir=A,/home/user/Music                    # Mounted Media_Collection drive directories
media_dir=P,/home/user/Pictures                 # Use A, P, and V to restrict media 'type' in directory
media_dir=V,/home/user/Videos
friendly_name=Media Server                      # Optional
inotify=yes                                     # 'no' for less resources, restart required for new media
presentation_url=http://192.168.1.XX
```
```bash
sudo mkdir /etc/systemd/system/minidlna.service.d
sudo vim /etc/systemd/system/minidlna.service.d/override.conf
```
```python
[Service]
ProtectHome=read-only
```
```bash
sudo systemctl daemon-reload
sudo systemctl start minidlna.service
```
Connect with DLNA client
