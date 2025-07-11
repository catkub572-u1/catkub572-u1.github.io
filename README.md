``` docker-compose.yaml
version: '3.8'

services:
  tiny11-display1:
    image: dockurr/windows
    container_name: WIN อะไรไม่รู้
    environment:
      VERSION: "https://archive.org/download/tiny11-2311/tiny11%202311%20x64.iso"
      USERNAME: "user"
      PASSWORD: "1234"
      DISK_SIZE: "32G"
    ports:
      - "8006:8080"
    devices:
      - /dev/kvm
    cap_add:
      - NET_ADMIN
    restart: unless-stopped

  audio:
    image: pulseaudio/pulseaudio
    container_name: audio
    ports:
      - "8009:4713"
    restart: unless-stopped
```

ชื่อคือ USER
รหัสคือ 1234
discord : aopsqn4439

localhost:8006 = จอ / NoVNC
localhost:8007 = เสียง / audio
ต้องเทส

ถ้าใช้ใน githubcodespaces หรือดครื่องที่ไม่มี KVM
``` docker-compose.yaml
version: '3.8'

services:
  tiny11-display1:
    image: dockurr/windows
    container_name: WIN อะไรไม่รู้
    environment:
      VERSION: "https://archive.org/download/tiny11-2311/tiny11%202311%20x64.iso"
      USERNAME: "user"
      PASSWORD: "1234"
      DISK_SIZE: "32G"
    ports:
      - "8006:8080"
    devices:
      - /dev/kvm
    cap_add:
      - NET_ADMIN
    restart: unless-stopped
```
