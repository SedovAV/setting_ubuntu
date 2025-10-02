## setting_ubuntu

### NVIDIA 570

Для вычислений (NVIDIA RTX 5070 Ti) на Ubuntu доступны драйверы с открытым исходным кодом. Для этой модели GPU поддерживаются nvidia-driver-570-open и nvidia-driver-575-open. Только драйверы с "-open" совместимы с новыми GPU. gist.github.comaskubuntu.comnvidia.com
Важно: стандартные драйверы NVIDIA (например, nvidia-driver-570) не поддерживают RTX 50-ю серию, так как не имеют поддержки для GPU этой модели. spin.atomicobject.comleadergpu.com

#### Инструкция по установке для Ubuntu 24.04:

Удалить существующие установки NVIDIA. Например,

`sudo apt-get remove --purge '^nvidia-.*'`

Установить необходимые зависимости и добавить репозиторий PPA с драйверами NVIDIA.

`sudo apt update`

`sudo apt install build-essential dkms`

`sudo add-apt-repository ppa:graphics-drivers/ppa`
    
Установить драйвер с открытым исходным кодом:
    
`sudo apt install nvidia-driver-570-open`
    
После установки нужно перезагрузить систему и проверить работу драйвера с помощью утилиты

`nvidia-smi`

### Возможные ошибки и их решение
Если nvidia-smi не работает после перезагрузки, нужно проверить, правильно ли настроена Secure Boot и успешно ли пройдена регистрация MOK. Для ошибок «Key was rejected by service» — убедиться, что процесс регистрации MOK был завершён во время загрузки.
Если возникают проблемы с менеджером дисплея, можно перезагрузить его:

`sudo systemctl restart display-manager.service`
