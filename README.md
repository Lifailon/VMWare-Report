## Datastore-Report-Telegram - скрипт события с оповещением в Telegram.
Для работы скрипта используется модуль PowerCLI (install-module -name vmware.powercli). В начале скрипта необходимо указать token бота (в моем случае @BotFather) и id чата (группы), куда отправлять оповещения. $esxi - адрес вашего сервера, $user - логин и $pass - путь к хэшу пароля.
> Для создания хэш-пароля, воспользуйтесь командой: Read-Host –AsSecureString | ConvertFrom-SecureString | Out-File "$home\Documents\vcsa_password.txt"

Опрашивает все Datastore, вычисляет процент свободного места и инициализирует ВМ, которые используют свои vmdk на Datastore. Переменаня $proc (в примере, 30%) является тригерным условием, для отправки уведомления.

![Image alt](https://github.com/Lifailon/VMWare-Report-Telegram/blob/rsa/Report.jpg)

## Reconfig-VM-Report - отображает события всех изменений конфигурации ВМ за текущий день
В примере (на скриншоте) я вначале отключил сетевой адаптер (Network adapter 2 - Connected Off), после этого удалил его и выключил, а затем включил первый сетевой адаптер, тем самым инициализировал порядковый номер device 4000 и 4001, относящиеся к Network adapter. Таким образом, можно фиксировать изменения конфигурации относящиеся к конкретным Device.
