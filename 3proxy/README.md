# 3proxy SOCKS5

SOCKS5-прокси 3proxy с авторизацией по логину и паролю. Порт `1080` публикуется на хосте.

## Настройка

Создайте рабочий конфиг из примера:

```bash
cp 3proxy.cfg.example 3proxy.cfg
```

Откройте `3proxy.cfg` и замените строку:

```text
users proxy_user:CL:change_this_password
```

Формат строки:

```text
users USERNAME:CL:PASSWORD
```

В строке `allow` укажите того же пользователя:

```text
allow USERNAME
```

Пароль хранится в конфигурации в открытом виде.

## Запуск

```bash
docker compose up -d
```

Проверить состояние и логи:

```bash
docker compose ps
docker compose logs -f
```

После изменения логина, пароля или других параметров перезапустите контейнер:

```bash
docker compose restart
```

Остановить сервис:

```bash
docker compose down
```

## Подключение

Параметры подключения:

- Тип: `SOCKS5`
- Хост: IP-адрес или DNS-имя Docker-хоста
- Порт: `1080`
- Логин и пароль: значения из `3proxy.cfg`

URL подключения имеет вид:

```text
socks5://USERNAME:PASSWORD@HOST:1080
```
