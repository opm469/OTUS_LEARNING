# Настройка IPv6-адресов на сетеых устройствах  

## Топология  
![image](https://github.com/user-attachments/assets/855fe2fa-6d69-430e-84ac-a50ad7e98b70)  

Утсройство | Интерфейс | IPv6-адрес | Link local IPv6-адрес | Длина префикса | Шлюз по умолчанию   
------- | ----- | ------  | ----- | ------- | -----   
R1 | G0/0/0 | 2001:db8:acad:a::1 | fe80::1 | 64 | -   
-- | G0/0/1 | 2001:db8:acad:1::1 | fe80::1 | 64 |-  
S1 |Vlan1 | 2001:db8:acad:1::b | fe80::b | 64 -  
PC-A | NIC | 2001:db8:acad:1::3 | SLACC |64 | fe80::1 |  
PC_B | NIC | 2001:db8:acad:a::3 | SLACC | 64 | fe80::1 |   

## Задачи  
* Настройка топологии и конфигурация основных параметров маршрутизатора и коммутатора
* Настройка Ручная IPv6-адресов
* Проверка сквозного соединения

Настройка маршрутизатора 

![image](https://github.com/user-attachments/assets/a75ba06c-2a1b-4e2a-bfb6-4512d806c4d9) 

![image](https://github.com/user-attachments/assets/e5065550-cd70-4eb0-9f07-561f9ac234ef)  

Натсройка коммутатора  

![image](https://github.com/user-attachments/assets/c7c5c4d6-08f2-48be-b899-50de78b49072)  

![image](https://github.com/user-attachments/assets/98203516-2d7c-480a-a0d4-624959118b59)


Назначаем ipv6-адреса интерфейсам и активируем их

![image](https://github.com/user-attachments/assets/df0d045f-099a-44b5-b975-5deffc2ea6cf)   

![image](https://github.com/user-attachments/assets/b0665f4a-e3c9-42bd-9b29-491bf40edc3a)  

![image](https://github.com/user-attachments/assets/07fa28d0-75bd-4389-88e4-a4668318b404)

![image](https://github.com/user-attachments/assets/34bb8bcd-f95c-4e1f-8c01-b6a8249f3d53)  

![image](https://github.com/user-attachments/assets/5557fd87-02b8-4b45-8ff7-b51b0c4c5a8a)


![image](https://github.com/user-attachments/assets/326dcf3c-320e-4eac-99dd-8c14e7916611)  

![image](https://github.com/user-attachments/assets/d2dd2375-2fb2-44f2-93fa-5dd45b7c8922)

![image](https://github.com/user-attachments/assets/ec4e14cb-c54b-4248-be14-f09cc15febfe)  

* На PC-B с помощью команды ipconfig  смотрим данные ip-адресов

![image](https://github.com/user-attachments/assets/2a03b944-15e1-4f98-9202-30788fed4ee3)  

Назначен ли индивидуальный IPv6-адрес сетевой интерфейсной карте (NIC) на PC-B?  
_Нет_  

Активируйте IPv6-маршрутизацию на R1 с помощью команды IPv6 unicast-routing  
![image](https://github.com/user-attachments/assets/468baab6-d38e-46bf-8130-764748807ab2)  

![image](https://github.com/user-attachments/assets/19275a46-fe35-44c3-a310-de8469c1e0fa)  

* PC-B получил глобальный префикс маршрутизации и идентификатор подсети, потому что команда unicast-routing позволяют интерфейсам маршрутизатора получать и распространять глобальные IPv6-префиксы.

![image](https://github.com/user-attachments/assets/fa5fd95e-9821-44e5-ab82-bf4869a978d1)  




* Назначаем статический Ipv6-адреса компьтерам
* Проверяем сквозное подключение  

![image](https://github.com/user-attachments/assets/bde2ec13-e123-41c1-826d-4ca78b172ead)  

![image](https://github.com/user-attachments/assets/4ff81cb6-c924-4e39-b053-ffa3d23c1752)

![image](https://github.com/user-attachments/assets/e47b06ce-4164-4d06-82aa-367876b03f03)  

![image](https://github.com/user-attachments/assets/224531c7-329f-45bf-a46e-0127d531156c)

Почему обоим интерфейсам Ethernet на R1 можно назначить один и тот же локальный адрес канала — FE80::1?  
_Потому что link-local addresses должны быть уникальными только в пределах одного сегмента сети, а не по всей сети в целом_  
Какой идентификатор подсети в индивидуальном IPv6-адресе 2001:db8:acad::aaaa:1234/64?  
_Первые 48 бит 2001:db8:acad - это префикс, следующие 16 бит - это 0000 иденификатор подсети, и последние 64 бита aaaa:1234:: - это идентификатор интерефейса_
