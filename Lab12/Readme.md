# Настройка и проверка расширенных списков контроля доступа.  
## Тополония  
<img width="1006" height="362" alt="image" src="https://github.com/user-attachments/assets/c5dcd3b5-0702-4d1b-a874-83a0bd60e374" />    

##  Таблица адресации  

Устройство | Интерфейс | IP-адрес | Маска подсети | Шлюз по умолчанию  
--- | --- | --- | --- | ---    
R1 | G0/0/1 | --   | --  |  --    
--- | G0/0/1.20 | 10.20.0.1 | 255.255.255.0 |  ---    
--- | G0/0/1.30 | 10.30.0.1 | 255.255.255.0 | ---  
--- | G0/0/1.40 | 10.40.0.1 | 255.255.255.0 | ---  
--- | G0/0/1.1000 | --- | --- | ----  
--- | Loopback1 | 172.16.1.1 | 255.255.255.0 | ---  
R2 | G0/0/1 | 10.20.0.4 | 255.255.255.0 | ---  
S1 | VLAN20 | 10.20.0.2 | 255.255.255.0 | 10.20.0.1   
S2 | VLAN20 | 10.20.0.3 | 255.255.255.0 | 10.20.0.1  
PC-A | NIC | 10.30.0.10 | 255.255.255.0 | 10.30.0.1  
PC-B | NIC | 10.40.0.10 | 255.255.255.0 | 10.40.0.1  
## Таблица VLAN  

VLAN | Имя | Название инетрфейса   
--- | --- | ----   
20 | Management | S2: F0/5  
30 | Operations | S1: F0/18   
999 | ParkingLot | S1: F0/2-4, F0/7-24, G0/1-2  
--- | ---- | S2: F0/2-4, F0/6-17, G0/1-2  
1000 | Native |   

## Задачи
* Создание сети и настройка основных параметров устройства
* Настройка и проверка списков расширенного контроля доступа

Базовая настройка маршрутизатора  
<img width="495" height="720" alt="image" src="https://github.com/user-attachments/assets/e692d2cb-b88b-4811-94c9-e47db0bee131" />  
Базовая настройка коммутатора  
<img width="499" height="694" alt="image" src="https://github.com/user-attachments/assets/fc209d25-ed8e-4834-af63-49a790911f1c" />  

Настройка сетей VLAN на коммутаторах  
<img width="293" height="449" alt="image" src="https://github.com/user-attachments/assets/40132f6a-881d-420e-9eb0-ad0e24679c83" />  
<img width="675" height="832" alt="image" src="https://github.com/user-attachments/assets/7c7cdc8b-f0a8-4109-9e97-fe9cdb95a2f6" />  
<img width="660" height="320" alt="image" src="https://github.com/user-attachments/assets/b268ff65-5b7e-4fc6-a60d-2e4f4b0fea65" />  

Настройка транка (магистрального канала)  
<img width="626" height="425" alt="image" src="https://github.com/user-attachments/assets/619e0935-5118-43a8-8fb6-4c936faf90ac" />  
<img width="476" height="267" alt="image" src="https://github.com/user-attachments/assets/fe5f3139-f8bb-4f17-873f-246fa9b7ef78" />  
<img width="560" height="669" alt="image" src="https://github.com/user-attachments/assets/4938d50c-40f8-4ce3-9e38-9118b294b198" />  

Настройка маршрутизации между сетями VLAN на R1  
<img width="643" height="707" alt="image" src="https://github.com/user-attachments/assets/72d6118b-10dc-4135-a4d5-7233e7de8c38" />  
<img width="667" height="207" alt="image" src="https://github.com/user-attachments/assets/c66e7e1c-80ae-43ff-97aa-45635c105d02" />  
<img width="732" height="216" alt="image" src="https://github.com/user-attachments/assets/2fb63091-2baf-40b1-ab34-ee535d5a4a4b" />  
<img width="397" height="48" alt="image" src="https://github.com/user-attachments/assets/4c483187-8059-4b90-bc74-b17d4c58eb5d" />  

Настройка удаленного доступа  
<img width="699" height="801" alt="image" src="https://github.com/user-attachments/assets/24d5ac46-af4c-4b9d-978b-043d46d32e45" />  
<img width="625" height="514" alt="image" src="https://github.com/user-attachments/assets/661eac88-9d14-4362-929e-ba2d667c3c5e" />  

Эхо запрос/ответ  
<img width="490" height="449" alt="image" src="https://github.com/user-attachments/assets/b592132e-63a5-49ea-b5ff-81b5411cb3fc" />  
<img width="502" height="668" alt="image" src="https://github.com/user-attachments/assets/3160b379-ccad-4005-9fe1-1a5bac3c833b" />  
<img width="703" height="414" alt="image" src="https://github.com/user-attachments/assets/2db15b58-49fc-4f81-8510-4da630e57188" />   
<img width="515" height="192" alt="image" src="https://github.com/user-attachments/assets/d75630df-7a3a-4736-97b3-cc8acaa601e4" />
