# cloudflared-zero-trust

# Beli domain
- Pertama kita harus memiliki minimal 1 domain, yang nanti akan digunakan untuk menghubungkan antara server lokal agar bisa diakses dari public, disni saya membeli domain dari anymhost.id seharga 20 rb pertahun

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/30437a0b-166d-475c-acae-74899fcfbcbe)

- setelah kalian membeli domain pada anymhost.id maka akan ada email untuk manage domain kalian, 
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/38801a4b-984c-4478-9666-520d8e7b206a)

- tampilannya seperti ini,
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/a8732348-9b17-482f-b4d6-bea31595465b)

- kemudian buat account cloudflare (kita pakai cloudflare versi gratis), disini kalian bisa login pakai akun email
- jika sudah memiliki accountnya kalian bisa masukk pada bagian select product, https://dash.cloudflare.com/d53b4599f68ada98c45ffbfa4534d7a4/select-product untuk id pada link tidak akan sama kalian bisa tambahkan /select-product pada bagian akhirnya

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/91d29143-965f-4d82-b0b0-5066b2743899)

- disini kita akan mendaftarkan domain yang suda kita beli sebelumnya
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/8cd7c173-f51b-46f8-8058-19508de43771)

- continue, disini kita diminta untuk memilih langganan. tidak usah ditanya lagi, tentunya kita memilih yang gratisssss dong
  
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/dba8b0d7-526a-4bf0-b251-3fb31789d8eb)

- kemudian kita diminta untuk review pada management domain, disini kita hapus semua aja gpp sampai kosong ya

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/135b28a3-8a60-464c-89c3-b3c85a656f2e)

- kemudian akan ada intruksi pada cloudflare untuk mengganti nameserver pada domain kita,

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/9f3c4f06-da99-4ff5-be27-92add4972073)

- kemudian kita pindah pada ke website  [link](https://clients.anymhost.id/clientarea.php?action=domains), kita dapat ubah nameserver pada management nameserver
  
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/fd899d11-9c3f-4769-88fe-28301487511b)

- sesuaikan nameserver, perubahan paling lama sampai 24 jam untuk updatenya
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/14aa6af2-d75f-48c4-904b-d9dce0ade328)

- jika sudah edit nameserver pada domain selanjutnya pindah ke cloudserver lagi, dan pilih *Done, check nameserver*
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/668731fa-9420-4a92-ad26-b0f23185820e)

- selanjutnya tahap setup domain improve scurity bisa kalian samakan saja
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/30886261-626c-45f4-9db5-ea946005510a)

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/3ad4c859-242f-4afd-aeec-04115d9989fd)

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/1e816e23-c6ba-475b-a87f-b3f7037b5843)

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/50bf506a-d335-4c3d-9332-5f142aa49cf0)

- Disini kita akan menunggu update registrasi, paling lama 24 jam
- 
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/c672ee97-4713-4573-8075-bfd1ceed37dd)

- nanti akan ada email seperti dibawah ini,
  
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/f0391935-b8b3-4616-95f6-c7fe2492a73f)


- jika sudah maka active seperti ini
  
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/3bfe9398-db58-44b1-a5fc-aab636832fb9)

- selanjutnya kita akan membuat tunnel nya, nanti tunnel nya kita gunakan online kan server-code
- - install server-code
```
curl -fOL https://github.com/coder/code-server/releases/download/v$VERSION/code-server_${VERSION}_amd64.deb
sudo dpkg -i code-server_${VERSION}_amd64.deb
sudo systemctl enable --now code-server@$USER
```

- - edit config.yml server-code

```
nano .config/code-server/config.yaml
```

- config.yml
```
bind-addr: <ip server>:8080
auth: password
password: P@ssw0rd <bisa dirubah>
cert: false
```

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/4c49a31f-00be-404f-9a2e-1ff907ac227a)

  - restart service server-code,
```
systemctl restart code-server@root.service
systemctl status code-server@root.service
```

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/27043167-8fe0-4336-8c66-ffd56559590c)

  - verify code-server
    
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/3d70ba6a-a2ef-4334-9707-ab2b7fd5e2aa)

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/7537ef5c-1c37-4e1d-80ae-bc7df271d564)

  - create tunnel
    
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/24c0bb68-3199-4536-b0a6-6d47a358423b)

  - buat akun zero trust, disini kita perlu karu visa ataupun paypal untuk pembayaran luar negeri walaupub gratis kita perlu kartu visa

![Screenshot_38](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/6bc2de76-af42-406a-838e-4ec9a3657e83)

  - buat tunnel access > tunnel > add a tunnel > name tunnel

    set name tunnel
    
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/7f079f4e-3fb7-4e22-af84-c6c0c7935bf1)

install tunnel in server ubuntu

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/dfac2055-54eb-4c0e-bb99-676ec2f2e742)

![Screenshot_40](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/7e1b4875-683a-4938-8b12-229afb27c0dd)

![Screenshot_41](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/10abebe7-37a0-40e9-bde8-85c223db7b20)

jika sebelumnya sudah install maka kalian pernah menamahkan token, kalian bisa jalankan ini dulu
```
cloudflared service uninstall
```

  - maka pada connector otomatis akan muncul connector ID server tadi

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/cf1cc7e8-1c2c-4e60-b1d7-2cb3ee90ab24)

  - isikan seperti ini untuk public hostname

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/d0be5b41-5979-423f-899b-d4f0e28dc2cf)

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/aacca405-6c20-4bb9-a655-c45d77ecc2fa)

  - Agar bisa diakses kita harus menambahkan cname pada domain kita

![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/d416916a-c108-4d39-9bc7-4ba0ba806a05)
  
  - verify access
  - 
![image](https://github.com/galihtw04/cloudflared-zero-trust/assets/96242740/da8c3b3e-48e3-4cd2-8d7f-712385162dd0)
