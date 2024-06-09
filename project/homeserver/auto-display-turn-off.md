```sh
$ sudo vi /etc/systemd/system/enable-console-blanking.service
```
```service
[Unit]
Description=Enable virtual console blanking

[Service]
Type=oneshot
Environment=TERM=linux
StandardOutput=tty
TTYPath=/dev/console
ExecStart=/usr/bin/setterm -blank 1

[Install]
WantedBy=multi-user.target
```
```sh
$ sudo chmod 664 /etc/systemd/system/enable-console-blanking.service
$ sudo systemctl enable enable-console-blanking.service
```
```sh
$ sudo reboot
```