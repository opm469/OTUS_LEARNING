# Настройки протокола OSPFv2 для одной области  
## Топология  
![image](https://github.com/user-attachments/assets/88f6ee1d-8d41-427e-9f47-91c1fa50215a)  
## Таблица адресации  
Устройство | Интерфейс | IP-адрес | Маска подсети  
--- | ---  | ---- | ---- 
R1 | G0/0/1 | 10.53.0.1 | 255.255.255.0  
--- |Loopback1 | 172.16.1.1 | 255.255.255.0  
R2 | G0/0/1 | 10.53.0.2 | 255.255.255.0
---|  Loopback1 | 192.168.1.1 |255.255.255.0  
* Создание сети и настройка основных параметров устройства
* Настройка и проверка базовой работы протокола  OSPFv2 для одной области
* Оптимизация и проверка конфигурации OSPFv2 для одной области
 
Базовая настройка маршрутизаторов  
![image](https://github.com/user-attachments/assets/fb251518-0688-4fed-88d8-c98aaaa00c46)  
![image](https://github.com/user-attachments/assets/f756ef90-5c42-49e1-a51c-9e3b452073b1)  
Настройка базовых параметров коммутаторов  
![image](https://github.com/user-attachments/assets/6d79f9e2-de68-4393-a2ff-f08bfbbf1a58)  
![image](https://github.com/user-attachments/assets/1d16c288-10ee-4b8c-89d2-7e213d924a92)  

Настройка адреса интрефейса и базового OSPFv2 на маршрутизаторах  
R1  
![image](https://github.com/user-attachments/assets/567a7e5c-8da4-4047-bf1b-0ddfbb3bfd68)  
![image](https://github.com/user-attachments/assets/88431415-423c-4c5f-af22-2a67ed7a8a80)  
![image](https://github.com/user-attachments/assets/40ad4bc7-615a-4811-bc4a-1d597dad1f48)   
![image](https://github.com/user-attachments/assets/d32946e7-e240-490a-936e-7a2b74f12388)  
R2  
![image](https://github.com/user-attachments/assets/debad655-597a-47ee-93ab-3673641da038)  
![image](https://github.com/user-attachments/assets/cf841974-9a9e-4c54-84a8-06917a79eca5)  
![image](https://github.com/user-attachments/assets/6f6c9e04-48fc-4e25-9e10-213178a6639e)  

Какой маршрутизатор является DR?  
![image](https://github.com/user-attachments/assets/aa754282-5f0c-4ce8-9cfa-94ca10728105)  
_R1_   

Какой маршрутизатор является BDR?  
![image](https://github.com/user-attachments/assets/9382546d-1b11-450c-9dee-09651dd64b10)  
_R2_    

Каковы критерии отбора?  
_По приоритету, здесь по умолчанию 1_  
_При равенстве приоритетов выбираеться маршрутизатор с наибольшим Router ID_   

На R1 выполняем команду show ip route ospf, чтобы убедиться, что сеть R2 Loopback1 присутствует в таблице маршрутизации  
![image](https://github.com/user-attachments/assets/afc1b28a-6230-4556-bcf1-e7f75c4feebf)

Оптимизация и проверка конфигурации OSPFv2  
![image](https://github.com/user-attachments/assets/82b89f14-c2ef-44b0-b553-4d31bc6568e4)  
![image](https://github.com/user-attachments/assets/7c015c28-6b2c-42a3-ada2-a4fd344ee14e)  
![image](https://github.com/user-attachments/assets/0afb4613-f865-4809-94fb-d1f540fee8c4)  
![image](https://github.com/user-attachments/assets/4a01e851-2273-40dc-abec-3c90a6cdb2cc)  
![image](https://github.com/user-attachments/assets/7d37ebbc-60d0-4872-a697-d4c26f215c82)  
![image](https://github.com/user-attachments/assets/6109fa1b-84f4-46f1-8bf5-0bee8d8d5794)  
![image](https://github.com/user-attachments/assets/071b25f6-f0d1-4a78-a5e4-eecfd398c33d)  
![image](https://github.com/user-attachments/assets/fd555009-c085-421e-a690-0a8aeafa4a8f)  
![image](https://github.com/user-attachments/assets/da0eb5e5-8a9b-495b-b2c6-7df44c1d20f7)  

Почему стоимость OSPF для маршрута по умолчанию отличается от стоимости OSPF в R1 для сети 192.168.1.0/24?    
_Стоимоть lookback по умолчанию равно 1, E2 - OSPF external type, внешний тип, получаеться что значение по умолчанию сохраняеться на все сети OSPF. А сеть 192.168.1.0.24 это внутренний  и его метрика может суммироваться_
