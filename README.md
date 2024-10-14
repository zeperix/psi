# Hướng dẫn cài đặt cho ANDROID
> Make By ZeronX DEV, https://ht4gvpn.com
## Tải xuống termux 
* [**Download Termux**](https://github.com/overkillzero/psi/raw/main/Termux.apk)
### Copy lệnh sau và dán vào termux rồi ấn Enter
```bash
termux-setup-storage && apt upgrade && pkg install git -y && git clone https://github.com/overkillzero/psi && clear && cd psi && chmod a+x tun && chmod a+x psiphon-tunnel-core && echo 'PATH="$PATH:$HOME/psi"' >> $HOME/.bashrc && source $HOME/.bashrc
```
### Tải xuống SockDroid
* [**Download SocksDroid**](https://github.com/overkillzero/psi/raw/main/SocksDroid.apk)
### Cấu hình SockDroid như sau:
- Server IP: ```127.0.0.1```
- Server Port: ```1080```
- DNS Server: ```203.113.131.6```
- DNS Port (TCP): ```53```
- Per-app Proxy: ```Bật```
- Bypass Mode: ```Bật```
- App List: điền ```com.termux```
> Các cài đặt khác để nguyên không sửa đổi

### Bật SockDroid (Công tắc ở góc trên bên phải), nếu hiện yêu cầu gì hãy chấp nhận hết
### Vào lại termux và gõ lệnh ```tun``` (Nếu báo lỗi hãy gõ lại đến khi được)
### Chờ 10 giây là đã kết nối thành công, có thể sử dụng mạng




Requirements
------------

**Linux**

    git
    golang
    redsocks

**Windows**

    golang
    proxifier

**Android (Termux)**

    git
    golang


Install
-------

**AUR**

    $ yay -S brainfuck-psiphon-pro-go-bin

**Brainfuck Psiphon Pro Go**

    $ go get -v -u -d github.com/aztecrabbit/brainfuck-psiphon-pro-go
    $ cd ~/go/src/github.com/aztecrabbit/brainfuck-psiphon-pro-go
    $ go build -ldflags "-s -w"

**Psiphon Tunnel Core**

    $ go get -v -u -d github.com/Psiphon-Labs/psiphon-tunnel-core/ConsoleClient
    $ cd ~/go/src/github.com/Psiphon-Labs/psiphon-tunnel-core/ConsoleClient
    $ go build -ldflags "-s -w" -o ~/go/src/github.com/aztecrabbit/brainfuck-psiphon-pro-go/psiphon-tunnel-core


Usage
-----

**Linux**

    $ cd ~/go/src/github.com/aztecrabbit/brainfuck-psiphon-pro-go
    $ sudo --preserve-env -s
    # ./brainfuck-psiphon-pro-go


**Android (Termux)**

    $ cd ~/go/src/github.com/aztecrabbit/brainfuck-psiphon-pro-go
    $ ./brainfuck-psiphon-pro-go

<!-- -->

    Use ProxyDroid (root), Tun2Tap, or SocksDroid to redirect all connection to this Tunnel (Socks 5 Port 3080)
    Exclude Termux!


Configurations
--------------

Run `./brainfuck-psiphon-pro-go` first to export all default settings.
Config will generated to `config.json` where `brainfuck-psiphon-pro-go` binary file are executed. or in linux
`~/.config/brainfuck-psiphon-pro-go`


### Pro Version

    ...
    "PsiphonCore": 1,
    "Psiphon": {
        "CoreName": "psiphon-tunnel-core",
        "Tunnel": 4,
        "Region": "",
        "Protocols": [
            "FRONTED-MEEK-HTTP-OSSH",
            "FRONTED-MEEK-OSSH"
        ],
        "TunnelWorkers": 8,
        "KuotaDataLimit": 0,
        "Authorizations": [
            "blablabla"
        ]
    }
    ...


### Rules

**XL Iflix or Axis Gaming (Default)**

    ...
    "Rules": {
        "akamai.net:80": [
            "video.iflix.com",
            "videocdn-2.iflix.com",
            "iflix-videocdn-p1.akamaized.net",
            "iflix-videocdn-p2.akamaized.net",
            "iflix-videocdn-p3.akamaized.net",
            "iflix-videocdn-p6.akamaized.net",
            "iflix-videocdn-p7.akamaized.net",
            "iflix-videocdn-p8.akamaized.net"
        ]
    },
    ...

**Direct**

    ...
    "Rules": {
        "*:*": [
            "*"
        ]
    },
    ...

or

    ./brainfuck-psiphon-pro-go -f "*" -w "*:*"

**Telkomsel 0P0K**

    ...
    "Rules": {
        "akamai.net:443": [
            "118.97.159.51:443",
            "118.98.95.106:443"
        ]
    },
    ...

or

    ./brainfuck-psiphon-pro-go -f 118.97.159.51:443,118.98.95.106:443 -w akamai.net:443

**Pubg Mobile (XL King)**

    ...
    "Rules": {
        "akamai.net:80": [
            "www.pubgmobile.com"
        ]
    },
    ...

**Joox (XL King)**

    ...
    "Rules": {
        "akamai.net:80": [
            "ak-quic.stream.music.joox.com.edgesuite.net",
            "ak-hk.stream.music.joox.com.edgesuite.net",
            "ak-ng.stream.music.joox.com.edgesuite.net",
            "ak-quic.app.joox.com.edgesuite.net",
            "ak-ng.app.joox.com.edgesuite.net",
            "e5121.b.akamaiedge.net"
        ]
    },
    ...

**Ruang Guru and Udemmy (XL or Axis)**

    ...
    "Rules": {
        "fastly.net:443": [
            "c.shared.global.fastly.net:443",
            "rg-video.ruangguru.com:443"
        ]
    },
    ...

or

    ./brainfuck-psiphon-pro-go -f c.shared.global.fastly.net:443,rg-video.ruangguru.com:443 -w fastly.net:443


Note
----

- Use [bugscanner](https://github.com/aztecrabbit/bugscanner) to scan bugs for brainfuck psiphon pro go
