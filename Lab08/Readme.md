# Реализация DHCPv4  
## Топология  
![image](https://github.com/user-attachments/assets/0b4f9033-b6bd-496d-8baa-9ced4ed4a29f)  
## Таблица адресации  
Устройство | Интерфейс | IP-адрес | Маска подсети | Шлюз по умолчанию  
--- | ---- | --- | ---- | ----- 
R1 | G0/0/0 | 10.0.0.1 | 255.255.255.252 | --- 
--- | G0/0/1 | --- | --- | ---  
--- | G0/0/1.100 | 192.168.1.1 | 255.255.255.192 | ---
--- | G0/0/1.200 | 192.168.1.65 | 255.255.255.224 | ---  
--- | G0/0/1.1000 | --- | --- | ---  
R2 | G0/0 | 10.0.0.2 | 255.255.255.252 | ---
--- | G0/0/1 | 192.168.1.97 | 255.255.255.240 | ---   
S1 |VLAN 200 | 192.168.1.66 | 255.255.255.224 | 192.168.1.65   
S2 | VLAN 1 | 192.168.1.98 | 255.255.255.240 | 192.168.1.97 
PC-A | NIC | DHCP | DHCP | DHCP 
PC-B | NIC | DHCP | DHCP | DHCP 
## Таблица VLAN  
VLAN | Имя | Назаначенный интерфейс 
--- | --- | ---- 
1 | Нет | S2: F0/18 
100 | Клиенты | S1: F0/6 
200 | Управление | S1: VLAN 200 
999 | Parking Lot | S1: F0/1-4, F0/7-24, G0/1-2 
1000 | Собственная | ---
## Задачи   
* Создание сети и настройка основных параметров устройства  
* Настройка и проверка двух серверов DHCPv4 на R1
* Настройка и проверка DHCP-ретрансляции на R2
## Создание сети и настройка основных параметров устройства  
![image](https://github.com/user-attachments/assets/0a7dadbd-e641-4ad5-a658-f14b18adb44a)  
![image](https://github.com/user-attachments/assets/187bd4d7-f103-4f7b-9f09-814a30ea793b)  
![image](https://github.com/user-attachments/assets/f3de1a2a-4578-4c48-8d2e-2b91d6ef2b26)  
![image](https://github.com/user-attachments/assets/6d0b4992-1ad4-4645-8678-e639848704b1)  
![image](https://github.com/user-attachments/assets/08cdcdbe-d9f0-4a2a-8f3d-a15220a4e7b3)   
![image](https://github.com/user-attachments/assets/a6e4c708-c667-4cfb-8e71-d6c8221537b4)  
![image](https://github.com/user-attachments/assets/1313ba93-f077-4ea3-a9b5-abb94258e824)  
![image](https://github.com/user-attachments/assets/c02d3ea6-63cf-4c36-9f4e-3903b33ef40e)   
![image](https://github.com/user-attachments/assets/1008db24-f12f-4485-82bf-7d3bebaa18d5)

![image](https://github.com/user-attachments/assets/95abe565-7447-433d-9c53-25b96381f8bd)   
![image](https://github.com/user-attachments/assets/c8adb420-776e-4b27-9d5e-75f002572745)    
![image](https://github.com/user-attachments/assets/b01389e8-0c14-4d7c-9002-afc9e0379bd7)  
![image](https://github.com/user-attachments/assets/d31e29b2-51ba-4b55-9c9f-9ae75ce86b29)    
![image](https://github.com/user-attachments/assets/5564d1f6-f73a-4d41-8ba3-750531a62854)   
![image](https://github.com/user-attachments/assets/61eb03c4-786d-43cf-847e-914eec17b59e)  
![image](https://github.com/user-attachments/assets/c0f1cea9-d7ad-4528-876b-bfb1257ad4c7)  
![image](https://github.com/user-attachments/assets/ad098c14-40b8-4a97-973e-976ff5bbfcff)
![image](https://github.com/user-attachments/assets/7c36f9eb-a4cb-40fb-80ca-2f2b891ec405)  

Почему интерфейс F0/5 указан в VLAN 1?
_Потому что он не настроен как транк_
![image](https://github.com/user-attachments/assets/57ecb344-d9f7-4266-8aad-a563275397d7)  
![image](https://github.com/user-attachments/assets/df38034a-bb4f-4cc1-95c4-b9c98549c480)
 ## Настройка и проверка двух серверов DHCPv4 на R1  
 ![image](https://github.com/user-attachments/assets/2d835488-e61b-43ed-8cfe-e035f4703b38)  
 ![image](https://github.com/user-attachments/assets/09ac57d4-9b74-4a65-b5ad-a626f37efdf6)  
 ![image](https://github.com/user-attachments/assets/43a4bb4b-8ee7-4e50-945a-b7f6d6fda0e8)  
 ![image](https://github.com/user-attachments/assets/c61be7a7-6f30-4c9b-9a3a-7b29cb872d98)
 ![image](https://github.com/user-attachments/assets/ad4b65c8-edcf-456e-81e7-02bb9241bb79)
 ![image](https://github.com/user-attachments/assets/1d749c20-c148-422b-8b92-903368a7fc1c)  
## Настройка и проверка DHCP-ретрансляции на R2
 ![image](https://github.com/user-attachments/assets/7848cff1-58e7-423f-ac08-ba2ca6a0dd10)
 ![image](https://github.com/user-attachments/assets/a2028d7c-4f06-42f5-b168-511b96e0329d)  
 ![image](https://github.com/user-attachments/assets/6adc8f5f-4e38-41e7-b419-75fc195b8ddb)  
 ![image](https://github.com/user-attachments/assets/2e4b9e98-e0a5-4edd-89cb-f970fe33aa89)  
 
