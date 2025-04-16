 Базовая настройка коммутатора 

	Топология  
 ![image](https://github.com/user-attachments/assets/c59f97c9-d904-43a5-bc3e-8a5880d5072b)

Устройустро | Интерфейс | IP-адрес | Маска подсети | 
--------- | -------- | ---------- | ------------- | 
S1 | VLAN1 | 192.168.1.2 | 255.255.255.0 |
PC-A | NIC | 192.168.1.10 | 255.255.255.0 | 

 ### Решение:
Часть 1: 
* Создаем топологию сети
* Проверяем настойки по умолчанию


* Switch>en
* Switch#


  * Настроил актуальную дату и время

![image](https://github.com/user-attachments/assets/505e115f-29d8-4b96-a7e6-c963172edba5)

* С помощью show version, просматриваем текущую версию коммутатора

![image](https://github.com/user-attachments/assets/edc76561-adbc-46e3-a29e-99e2de23b023)

* При помощи команды show running-config, вызываем текущую конфигурацию устройства

  ![image](https://github.com/user-attachments/assets/cb4c4232-191f-44ce-8d63-a7000a0ad492)

  * Сколько интерфейсов FastEthernet имеется на коммутаторе 2960?
  * FastEthernet 0/1-24  

  * Сколько интерфейсов Gigabit Ethernet имеется на коммутаторе 2960?
  * Gigabit Ethernet 0/1-2 

  * Каков диапазон значений, отображаемых в vty-линиях?
  * line vty 0 4 , line vty 5 15
 

*  Просматриваем стартовую конфигурацию с помощью startup configuration.  
  Видим сообщение startup-config is not present, так как в стартовую конфигурацию ничего не загружено

   ![image](https://github.com/user-attachments/assets/a79b4e40-8b34-4bde-ae6c-dda2bd0bfc1f)

*   Просматриваем характеристики VLAN1

   VLAN | Name | Status | Port
-----| ----- | ---- | -----
1 | Default | Active | Fa0/1-24, G0/1-2

Все порты по умолчанию находятся в 1 влане

Назначен ли IP-адрес сети VLAN 1? 
  * Нет


Какой MAC-адрес имеет SVI? 
  * Вводим команду show interface VLAN 1

    ![image](https://github.com/user-attachments/assets/9e1f45b7-ee90-4429-997e-d644a2bbdd2d)

    Изучаем IP-свойства интерфейса SVI сети VLAN 1
  * Internet address is down

    Подключаем кабель Ethernet компьютера PC-A к порту 6 на коммутаторе и изучите IP-свойства интерфейса SVI сети VLAN 1

    ![image](https://github.com/user-attachments/assets/b6895e38-c580-4003-b01f-56a79541a0a9)

    Под управлением какой версии ОС Cisco IOS работает коммутатор?

    ![image](https://github.com/user-attachments/assets/47cada21-52d9-4323-aef3-00bda554e7dd)

    Как называется файл образа системы?
    
    System image file is "flash:c2960-lanbasek9-mz.150-2.SE4.bin"

Изучите свойства по умолчанию интерфейса FastEthernet, который используется компьютером PC-A.

![image](https://github.com/user-attachments/assets/a98b4608-31f2-4a71-bb11-96ee31322b15)

Интерфейс включен или выключен?
Включен

Какой MAC-адрес у интерфейса?

![image](https://github.com/user-attachments/assets/2a16d2c0-e007-4386-b8f8-5383f82b49c6)

Какие настройки скорости и дуплекса заданы в интерфейсе?

100mb

асть 2:  
 
 Шаг1:  
* Приступаем к настройке базовых параметров коммутатора
* Вводим команды
* no ip domain-lookup
* hostname S1
* service password-encryption
* enable secret class
* banner motd # Unauthorized access is strictly prohibited. #

![image](https://github.com/user-attachments/assets/3bbc976e-cd17-459f-8257-8fb712674d94)

Ограничиваем доступ к консольному порту
* line con 0
* password cisco
* logging synchronous

![image](https://github.com/user-attachments/assets/3ccce5a3-21eb-4150-ae71-722b625f406c)

Настройте каналы виртуального соединения для удаленного управления vty  
* line vty 0 4
* password
* login local
![image](https://github.com/user-attachments/assets/437b94ba-96f3-45dc-ba5a-91ef032dc21b)

*Для чего нужна команда login?*   
Команда login используется для включения аутентификации при доступе к устройству через консоль, Telnet или SSH.

Шаг2:  
Настойка IP-адреса на компьтере  
* Перейдите в Панель управления
* В представлении «Категория» выбераем: Просмотр состояния сети и задач
* Вибираем: изменение параметров адаптера на левой панели
* Щелкнит правой кнопкой мыши интерфейс Ethernet и выбераем «Свойства» 
* Выбераем: Протокол Интернета версии 4 (TCP/IPv4) > Свойства
* Выбераем: Использовать следующий IP-адрес и введите IP-адрес и маску подсети  и нажмите ОК.

* ![image](https://github.com/user-attachments/assets/7d23a64f-1411-4dd6-b907-d4455ce15e9f)
 
Проверяем сетевое подключение  
Шаг1:    
* С помощью команды show run, выводим всю текущюю конфигурацию
* Проверьте параметры VLAN 
* Какова полоса пропускания этого интерфейса? 
  BW 100000 Kbit или 100 Мбит/с

Шаг2:  
Проверяем скрозное соединение эхо-запросом
* C:\> ping 192.168.1.10 пинг идет
* C:\> ping 192.168.1.2 пинг идет

Шаг3:    
Проверяем удаленное управление коммутатором
* Открываем Command Promt
* Telnet 192.168.1.2
* Password : cisco
* S1>en
* Password : class
* Мы на устройстве

![image](https://github.com/user-attachments/assets/0aeeeef5-039a-4443-ad9c-ba441d1480b4)






















 
