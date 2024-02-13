# Network device admins

## Usage

```bash
git clone git@github.com:tknv/docker-freeradius-admins.git
cd docker-freeradius-admins
docker build -t radius-admin-image -f Dockerfile .
docker run --rm --name radius-admin -t -p 1812-1813:1812-1813/udp radius-admin-image -X
```

### Test

`192.168.100.60` is where running this docker image.

```bash
> radtest awaslab symbol 192.168.100.60 1812 symbol123
Sent Access-Request Id 106 from 0.0.0.0:37059 to 192.168.100.60:1812 length 74
        User-Name = "awaslab"
        User-Password = "symbol"
        NAS-IP-Address = 127.0.1.1
        NAS-Port = 1812
        Message-Authenticator = 0x00
        Cleartext-Password = "symbol"
Received Access-Accept Id 106 from 192.168.100.60:1812 to 192.168.100.60:37059 length 86
        Symbol-Admin-Role = SuperUser
        Service-Type = Administrative-User
        Filter-Id = "Entrasys:mgmt=su:"
        Filter-Id = "Entrasys:version=1:mgmt=su:"

```

## Contribution

Please add more network vender admin attribute.

