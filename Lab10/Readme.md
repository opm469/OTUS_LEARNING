# Конфигурация безопасности коммутатора  
## Топология  
![image](https://github.com/user-attachments/assets/027ec68e-92e7-47d0-9f38-6c15c79fe876)  
## Таблица адресации  
Утсройство | interface/vlan | IP-адрес | Маска подсети   
--- | --- | ---- | ----  
R1 | G0/0/1 | 192.168.10.1 | 255.255.255.0 
--- | Loopback 0 | 10.10.1.1 | 255.255.255.0
S1 | VLAN 10 | 192.168.10.201 | 255.255.255.0
S2 | VLAN 10 | 192.168.10.202 | 255.255.255.0 
PC A | NIC | DHCP | 255.255.255.0
PC B | NIC | DHCP | 255.255.255.0 
## Задачи   
* Настройка основного сетевого устройства  
* Настройка сетей VLAN
* Настройка безопасности коммутатора

![image](https://github.com/user-attachments/assets/e56a233b-e163-4be0-9aba-f3e3e3ec4679)     
![image](https://github.com/user-attachments/assets/c6a93dad-6c05-412f-bca9-4a5df7023f65)  
![image](https://github.com/user-attachments/assets/07e01432-8303-4ee3-99b7-1f20dfbfe802)  
![image](https://github.com/user-attachments/assets/a6388593-3a07-4e61-8833-600aed6ba8e6)  
![image](https://github.com/user-attachments/assets/6746ac13-fb51-4930-9aaf-f471d6458b7e)  
![image](https://github.com/user-attachments/assets/7963d424-f327-487a-809e-aa8731d21f64)  
![image](https://github.com/user-attachments/assets/2cd0cbab-7e1b-4cbc-a087-662c51d93a95)  
![image](https://github.com/user-attachments/assets/2f93dfef-5516-4450-b4ea-fc266339ce3c)  
![image](https://github.com/user-attachments/assets/f8b32bd9-2627-4702-a21e-cda67da5f1c0)  
![image](https://github.com/user-attachments/assets/e4deba3b-580b-4586-b6a1-9acb743e082c)  
![image](https://github.com/user-attachments/assets/78d67616-43ff-410f-94f4-b2320249a025)  
![image](https://github.com/user-attachments/assets/0fcbf430-566f-4fd2-9178-a8b9ba5a5b2e)  
![image](https://github.com/user-attachments/assets/6e3c2ce4-306e-4735-9a75-1001f11989a0)   
![image](https://github.com/user-attachments/assets/487410d1-5173-413c-97fd-2a0607b90e3d)  
![image](https://github.com/user-attachments/assets/589958ab-b704-452a-92bd-73585e5d091d)  
![image](https://github.com/user-attachments/assets/4c9a6cd9-71fa-4114-82f8-6c4c0057344a)  
![image](https://github.com/user-attachments/assets/b4980fa3-b967-499e-8d71-1c91f10b929a)  
![image](https://github.com/user-attachments/assets/100164e8-7032-4e3d-800b-d9bf558b00e1)  

--- | Конфигурация безопасности порта по умолчанию | ---
-- | -- | ---
Функция | Настройка по умолчанию 
Защита портов | Disabled
Максимальное количество записей MAC-адресов | 1 
Режим проверки на нарушение безопасности | Shutdown
Aging Time | 0 mins  
Aging Type | Absolute  
Secure Static Address Aging | Disabled
Sticky MAC Address | 0
![image](https://github.com/user-attachments/assets/937ea7e3-702d-4deb-8b91-533ec5dd61c0)  
![image](https://github.com/user-attachments/assets/4089f4c5-e140-41d8-85c4-a125eca8ba9f)  
![image](https://github.com/user-attachments/assets/ca8da01a-93e7-4113-b8a3-5befd458e3ec)  
![image](https://github.com/user-attachments/assets/48a30f2a-80c7-4c82-b716-cd446fc929a1)  
![image](https://github.com/user-attachments/assets/1dc04b62-9c5b-4af3-9fe9-633cbdd182d1)  
![image](https://github.com/user-attachments/assets/a0e4801a-0fa5-42a5-ae65-44cc0f1343e4)   
![image](https://github.com/user-attachments/assets/7cbb1c4e-69ff-4cb8-b2cb-0fc130d2cba2)   
![image](https://github.com/user-attachments/assets/4f7959bd-a8ea-48a2-9c37-559364f6ae38)  
![image](https://github.com/user-attachments/assets/a99900de-e7cf-473b-8fd6-a17f9109d2ee)  
![image](https://github.com/user-attachments/assets/d5ad64be-6dfc-4f61-8d91-63e08060c367)  
![image](https://github.com/user-attachments/assets/6e92fce8-ccdc-496b-8330-b2dbec531637)  
![image](https://github.com/user-attachments/assets/a5e18f6c-0d57-43e1-97a4-4a3b619c98fa)  
![image](https://github.com/user-attachments/assets/1e32c593-55ef-4535-a880-b6162c8d70e2)
![image](https://github.com/user-attachments/assets/458b481d-ba57-4eb9-be27-9dd32b338d89)  
![image](https://github.com/user-attachments/assets/a4472764-daad-4a10-8157-a61b9898ba4e)  
![image](https://github.com/user-attachments/assets/be847697-6972-4908-990c-38fa421905f2)  
![image](https://github.com/user-attachments/assets/86164350-3d6f-4951-93f1-fb0e6cadb0b3)  

С точки зрения безопасности порта на S2, почему нет значения таймера для оставшегося возраста в минутах, когда было сконфигурировано динамическое обучение - sticky?  
_Потому что stycky mac динамически изучаются и сохраняются в конфигурации порта и не удаляются автоматически по истечении времени_  
Что касается безопасности порта на S2, если вы загружаете скрипт текущей конфигурации на S2, почему порту 18 на PC-B никогда не получит IP-адрес через DHCP?  
_Количество Mac в port securiry ограничено_  
_DHCP Snooping  может блокировать DHCP-пакеты от неавторизованных MAC-адресов на этом порту_  
Что касается безопасности порта, в чем разница между типом абсолютного устаревания и типом устаревание по неактивности?
Абсолютное устаревание  
_MAC-адрес удаляется через заданный промежуток времени, независимо от того, активен ли адрес или нет_
_Таймер запускается с момента изучения MAC-адреса, и по истечении времени адрес удаляется из таблицы безопасности порта_
Устаревание по неактивности  
_MAC-адрес удаляется только если он неактивен в течение заданного времени_  
_Если адрес продолжает использоваться, таймер сбрасывается и отсчёт начинается заново_
