# Настройка DHCPv6   
## Топология  
![image](https://github.com/user-attachments/assets/c2dbd9bc-53fd-4688-b67f-1c26a8c2202d)  
## Таблица адресации  
Устройство | Интерфейс | IPv6-адрес  
--- | --- | ---- 
R1 | G0/0/0 | 2001:db8:acad:2::1/64  
 --- |  | fe80::1
--- | G0/0/1 | 2001:db8:acad:1::1/64
--- |   | fe80::1
R2 | G0/0/0 | 2001:db8:acad:2::2/64
--- |  | fe80::2
--- | G0/0/1 | 2001:db8:acad:3::1/64 
--- |   | fe80::2
PC-A | NIC | DHCP 
PC-B | NIC | DHCP 
* Создание сети и настройка основных параметров устройства
* Проверка назначения адреса SLAAC от R1
* Настройка и проверка сервера DHCPv6 без гражданства на R1
* Настройка и проверка состояния DHCPv6 сервера на R1
* Настройка и проверка DHCPv6 Relay на R2
## Создание сети и настройка основных параметров устройства
![image](https://github.com/user-attachments/assets/ddb1d63c-a635-4b66-ac03-c824a5af403e)  
![image](https://github.com/user-attachments/assets/87de9e75-d5e9-45ee-8101-0f7b74575ebc)  
![image](https://github.com/user-attachments/assets/f2f50fc0-d3b6-41b8-bbc3-b141d31687e5)  
![image](https://github.com/user-attachments/assets/b2269e2b-d428-45b4-b9e0-20bb23cf84fa)  
![image](https://github.com/user-attachments/assets/d0c48cb9-4fb2-4b2d-8462-0a81561a2fab)
![image](https://github.com/user-attachments/assets/60d69a6d-2d87-4fcb-9736-2c81a46b4981)
![image](https://github.com/user-attachments/assets/6f676370-0999-4ab1-a2e9-fb0a62dd71d8)  
Откуда взялась часть адреса с идентификатором хоста?  
_Из его MAC-адреса_
## Проверка назначения адреса SLAAC от R1  
![image](https://github.com/user-attachments/assets/b8bb91bc-716c-4157-aaa0-372737afc3cf)  
![image](https://github.com/user-attachments/assets/beb2e3c5-8d26-4008-a305-37f804f2abc0)  
## Настройка и проверка сервера DHCPv6 на R1  
![image](https://github.com/user-attachments/assets/eabe7a6b-e4f7-4f1b-b98e-f831f4b52a10)
![image](https://github.com/user-attachments/assets/4a679a89-1115-4ff8-b12d-7d4911944c34)  
## Настройка сервера DHCPv6 с сохранением состояния на R1  
![image](https://github.com/user-attachments/assets/55d7cbce-b74c-4dd8-89e3-b7d23c971313)  
## Настройка и проверка ретрансляции DHCPv6 на R2
![image](https://github.com/user-attachments/assets/136e94b6-4033-4440-a81c-f776a464f0a9)
![image](https://github.com/user-attachments/assets/0a70745b-4e4d-414d-84d3-92f6168dc360)   
![image](https://github.com/user-attachments/assets/92494ce6-ec2f-487a-82ef-90dfcbc5b88d)
