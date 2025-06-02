# Внедрение маршрутизации между виртуальными локальными сетями  
## Топология  
![image](https://github.com/user-attachments/assets/743c7b61-edda-4bef-8f21-c8c93f3b9bb6)
Устройство | Интерфейс | IP-адрес | Маска подсети | Шлюз по умолчанию 
------ | ----- | ----- | ------ | ------ 
R1 | G0/0/1.10 | 192.168.10.1 | 255.255.255.0 |  
---   | G0/0/1.20 | 192.168.20.1 | 255.255.255.0 |  
---   | G0/0/1.30 | 192.168.30.1 | 255.255.255.0 |  
---   | G0/0/01.1000 | ---- | ---- |  
S1 | VLAN 10 | 192.168.10.11 | 255.255.255.0 | 192.168.10.1  
S2 | VLAN 20 | 192.168.10.12 | 255.255.255.0 | 192.168.10.1  
PC-A | NIC | 192.168.20.3 | 255.255.255.0 | 192.168.20.1  
PC-B | NIC | 192.168.30.3 | 255.255.255.0 |192.168.30.1  

## Таблица VLAN  
VLAN | ИМЯ | Назначенный интерфейс   
---- | ---- | -----  
10 | Управление | S1: VLAN10
--- | ---- | S2: VLAN 10  
20 | Sales | S1: F0/6  
30 | Operations | S2: F0/18  
999 | Parking_Lot | С1: F0/2-4, F0/7-24, G0/1-2
---- | ----- |  С2: F0/2-17, F0/19-24, G0/1-2  
1000 | Собственная | ---
   
# Задачи  
* Создание сети и настройка основных параметров устройства
* Создание сетей VLAN и назначение портов коммутатора
* Настройка транка 802.1Q между коммутаторами
* Настройка маршрутизации между сетями VLAN
* Проверка, что маршрутизация между VLAN работает  

![image](https://github.com/user-attachments/assets/08d7d433-db50-4a8a-9b50-a1eedd637a02)  
![image](https://github.com/user-attachments/assets/b6012c73-4c31-437c-9760-80c39cb4a4c4)  
![image](https://github.com/user-attachments/assets/7fd572f7-5c0e-4de8-a7ab-dcecbccaa38a)  
![image](https://github.com/user-attachments/assets/f450a584-5e5b-4cda-97a7-147c9274a4f5)  
![image](https://github.com/user-attachments/assets/15dfcbe5-49b7-433a-a007-d474e5fd9e1b)

![image](https://github.com/user-attachments/assets/b2134b74-8542-4a8a-96c5-444dd056f3b2)
     
![image](https://github.com/user-attachments/assets/af9c93bf-c7b5-4f77-8d59-3c94cb191e85)  
![image](https://github.com/user-attachments/assets/7da35d7a-d877-4f18-a0e4-f1433966daf1)
 
![image](https://github.com/user-attachments/assets/e296100e-fdb8-4929-96e8-7e0718ad6274)

![image](https://github.com/user-attachments/assets/29bd68f3-5713-4e43-80c4-a1fb9a987ec6)  
![image](https://github.com/user-attachments/assets/e5664e98-b631-4ee3-ab99-05d631790d62)  
![image](https://github.com/user-attachments/assets/0a4c78b6-c366-4389-96d9-4e279e1d768d)  
![image](https://github.com/user-attachments/assets/c5dcd00d-1e11-45b2-8135-928de3ba9262)  

![image](https://github.com/user-attachments/assets/f47cdb9b-ecd8-4057-9722-6078463d328c)  
![image](https://github.com/user-attachments/assets/ef2b76c3-89f0-4a67-aba3-b5109553f83c)  
![image](https://github.com/user-attachments/assets/0c683afb-a66f-48c4-925c-918c431123fd)  

![image](https://github.com/user-attachments/assets/28f36863-027f-4eb8-a07d-cfcc8ed182d9)  
![image](https://github.com/user-attachments/assets/62e7ca1e-5446-4f9e-8bd7-fe8e24e7da34)  
![image](https://github.com/user-attachments/assets/37a1ad7d-4085-4f8b-8ceb-af08ab102a1c)  
![image](https://github.com/user-attachments/assets/8ce98b7f-6d74-4944-bcd0-96e0ae24a07f)  
![image](https://github.com/user-attachments/assets/5e864483-564d-4e12-933e-39506ff6100f)  
![image](https://github.com/user-attachments/assets/2fc3b486-c898-48ea-959f-161fddd64664)  
![image](https://github.com/user-attachments/assets/cf864e44-33d8-480c-980b-1289fd182d20)  
![image](https://github.com/user-attachments/assets/e424945c-ac38-45b5-8379-0be79b7388f2)

Что произойдет, если G0/0/1 на R1 будет отключен?  
_Не будет сетевой связнности, так как хосты находятся в разных подсетях, а маршрутизация осуществляеться через роутер_  

![image](https://github.com/user-attachments/assets/b6e9809d-e0fc-4878-95f8-169a6d76e5e5)  

![image](https://github.com/user-attachments/assets/0bf5aed1-a0d4-4079-b367-c77de654c42e)  
![image](https://github.com/user-attachments/assets/59cb7f63-44a2-44e9-897f-c54357e8fc45)  

Какие промежуточные IP-адреса отображаются в результатах?   
_R1, PC-A_
