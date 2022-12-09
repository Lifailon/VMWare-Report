## Datastore-Report-Telegram - скрипт события с оповещением в Telegram.
Для работы скрипта используется модуль PowerCLI (install-module -name vmware.powercli). В начале скрипта необходимо указать token бота (в моем случае @BotFather) и id чата (группы), куда отправлять оповещения. $esxi - адрес вашего сервера, $user - логин и $pass - путь к хэшу пароля.
> Для создания хэш-пароля, воспользуйтесь командой: Read-Host –AsSecureString | ConvertFrom-SecureString | Out-File "$home\Documents\vcsa_password.txt"

Опрашивает все Datastore, вычисляет процент свободного места и инициализирует ВМ, которые используют свои vmdk на Datastore. Переменаня $proc (в примере, 30%) является тригерным условием, для отправки уведомления.

![Image alt](https://github.com/Lifailon/VMWare-Report-Telegram/blob/rsa/Report.jpg)
