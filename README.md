# ДЗ №34 Сетевые пакеты. VLAN'ы. LACP
--------------------------------------------------------------------------------------------
```
Строим бонды и вланы
в Office1 в тестовой подсети появляется сервера с доп интерфесами и адресами
в internal сети testLAN
- testClient1 - 10.10.10.254
- testClient2 - 10.10.10.254
- testServer1- 10.10.10.1
- testServer2- 10.10.10.1

равести вланами
testClient1 <-> testServer1
testClient2 <-> testServer2

между centralRouter и inetRouter
"пробросить" 2 линка (общая inernal сеть) и объединить их в бонд
проверить работу c отключением интерфейсов

для сдачи - вагрант файл с требуемой конфигурацией
Разворачиваться конфигурация должна через ансибл
```
- Для запуска стенда клонируем репозиторий в локальное хранилище, переходим в папку репозитория и запускаем стенд - ```vagrant up```
- Bond(по сути агрегирование каналов) настроено между inetRouter и centralRouter, эффективность работы настроенного логического канала состоящего из двух физических интерфейсов на двух вышеуказанных ВМ, можно рассмотреть с помощью скриншотов ```inetRouter.png``` и ```testClient1.png```(Папка screens), на которых отчетливо видно, что после имитации повреждения одного из физисечких каналов, само соединение не пропадает, поскольку второй канал продолжает выполнять свои функции уже в одиночку.
