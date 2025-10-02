# setting_ubuntu

`sudo passwd root`

`sudo apt install r8125-dkms`

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

_____________________________________________________________________________________________

`sudo apt install sofware-properties-common apt-transport-https wget`

`wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -`

`sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"`

`sudo apt update`

`sudo apt install code`

`apt install -y vim mc curl software-properties-common ca-certificates apt-transport-https`

`wget -O- https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor | tee /etc/apt/keyrings/docker.gpg > /dev/null`

`echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu jammy stable"| tee /etc/apt/sources.list.d/docker.list > /dev/null`

`apt update`

`apt install -y docker-ce`

`apt install -y docker-compose`

`apt install snapd`

`snap install dbeaver-ce`

`apt install -y umbrello`

`apt install -y yandex-browser`

`apt update`

`apt install -y python3-bs4`

`apt install -y python3-cryptography`

`apt install -y python3-fastapi`

`apt install -y python3-fastapi-users`

`apt install -y python3-fastapi-users-db-sqlalchemy`

`apt install -y python3-flask`

`apt install -y python3-flask-Login`

`apt install -y python3-flask-socketio`

`apt install -y python3-django`

`apt install -y python3-lxml`

`apt install -y python3-nltk`

`apt install -y python3-numpy`

`apt install -y python3-openpyxl`

`apt install -y python3-psycopg2`

`apt install -y python3-pillow`

`apt install -y python3-pydantic`

`apt install -y python3-pandas`

`apt install -y python3-pygame`

`apt install -y python3-regex`

`apt install -y python3-requests`

`apt install -y -U python3-spacy`

`apt install -y -U python3-ru_core_news_sm`

`apt install -y python3-sklearn`

`apt install -y python3-pip`

`apt install -y python3-werkzeug`

`apt install -y python3-sqlalchemy`

`apt install -y python3-uvicorn`

`apt update`

`apt install code`
