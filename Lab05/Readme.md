# Доступ к сетевым устройствам по протоколу SSH  

## Топология  
![image](https://github.com/user-attachments/assets/640eef62-d8f4-4dba-96ce-90cb1c4e3fc0)  

Устройство | Интерфейс | IP-адрес | Маска подсети | Шлюз по умолчанию  
----- | ----- | ----- | ----- | ------  
R1 | G0/0/1 | 192.168.1.1 | 255.255.255.0 |  
S1 | VLAN1 | 192.168.1.11 | 255.255.255.0 | 192.168.1.1 
PC-A | NIC | 192.168.1.3 | 255.255.255.0 | 192.168.1.1  

## Задачи 
* Настройка основных параметров устройств
* Настройка маршрутизатора для доступа по протоколу SSH
* Настройка коммутатора для доступа по протоколу SSH
* SSH через интерфейс командной строки (CLI) коммутатора

Производим настройку основных параметров устройств 

![image](https://github.com/user-attachments/assets/c442a26d-a3a5-47d5-860d-2577bff00396)  
![image](https://github.com/user-attachments/assets/c810ae77-719a-4654-926a-8ba5231fed0a)  
![image](https://github.com/user-attachments/assets/0b8dd558-fe7a-497a-a78c-50fbaf6d7e32)  

![image](https://github.com/user-attachments/assets/6bfbfd59-80f6-4ebe-8033-f32889109504)  
![image](https://github.com/user-attachments/assets/0ecd7d79-05ef-4417-8b89-fc3f5c309688)  
![image](https://github.com/user-attachments/assets/46dd2f5a-9fc0-49ff-928d-97feb1e2b255)  
![image](https://github.com/user-attachments/assets/31ea608c-7959-4ea8-bf5b-a3f33e088dbd)  
![image](https://github.com/user-attachments/assets/edd6e23f-0909-4e93-9a5a-6bf70421272c)  

![image](https://github.com/user-attachments/assets/8f80b6f1-1400-490d-98fd-94577bda49f9)  
![image](https://github.com/user-attachments/assets/82dfe972-2735-4129-a58d-74fc360287f5)

Производим настройку параметров маршрутизатора для доступа по протоколу SSH  

![image](https://github.com/user-attachments/assets/14394aa9-7217-4d7a-9acd-127e58fe7911)  
![image](https://github.com/user-attachments/assets/8313cf63-9e8a-4a21-b6c5-01373e3145dc)

Производим настройку параметров коммутатора для доступа по протоколу SSH   

![image](https://github.com/user-attachments/assets/db197db4-6a46-4d1f-bfb2-62b8f9fc8985)  
![image](https://github.com/user-attachments/assets/98dba651-f230-4710-9514-be835465d907)

![image](https://github.com/user-attachments/assets/58286830-e698-46df-b80f-45619f2c47f8)

Производим настройку протокола SSH с использованием интерфейса командной строки (CLI) коммутатора  

![image](https://github.com/user-attachments/assets/7182e44f-bc37-4ea2-a242-305b5c06b5af)

Какие версии протокола SSH поддерживаются при использовании интерфейса командной строки?  
_Cisco по умолчанию поддерживаются обе версии протокола_  
Как предоставить доступ к сетевому устройству нескольким пользователям, у каждого из которых есть собственное имя пользователя?  
_Использовать локальную базу пользователей и механизм аутентификации AAA_
