# Подключение к шардированному кластеру

Для подключения к [шардированному](../../concepts/sharding.md) кластеру Redis в строках подключения укажите IP-адреса или FQDN хостов-мастеров в каждом шарде.

Поддерживаются шифрованное соединение через порт `{{ port-mrd-tls }}` и нешифрованное через порт `{{ port-mrd }}`.

{% include [How to use TLS](../../../_includes/mdb/mrd/connect/how-to-use-tls.md) %}



## Подключение из графических IDE {#connection-ide}

{% include [IDE environment settings](../../../_includes/mdb/mrd/ide-envs.md) %}

Подключаться из графических IDE к хостам кластера можно только через SSH-туннель с помощью [созданной ВМ](./index.md#connect). Перед подключением [подготовьте сертификат](./index.md#get-ssl-cert).

{% list tabs %}

* DBeaver

    Поддержка подключения к {{ RD }}-кластеру доступна только в [коммерческих редакциях DBeaver](https://dbeaver.com/buy/).

    Чтобы подключиться к кластеру:

    1. Создайте новое соединение с БД:
        1. Выберите в меню **База данных** пункт **Новое соединение**.
        1. Выберите из списка БД **{{ RD }}**.
        1. Нажмите кнопку **Далее**.
        1. Укажите параметры подключения на вкладке **Главное**:
            * **Хост** — укажите через запятую FQDN хостов-мастеров каждого шарда.
            * **Порт** — `{{ port-mrd }}` для обычного кластера или `{{ port-mrd-tls }}` для кластера с включенным SSL-шифрованием.
            * В блоке **Аутентификация** укажите пароль от кластера.
        1. На вкладке **SSH**:
            1. Включите настройку **Использовать туннель SSH**.
            1. Укажите параметры SSH-туннеля:
                * **Хост/IP** — публичный IP-адрес [ВМ для подключения](./index.md#connect);
                * **Имя пользователя** — логин для подключения к ВМ;
                * **Метод аутентификации** — `Публичный ключ`;
                * **Секретный ключ** — путь к файлу закрытого ключа для подключения к ВМ;
                * **Passphrase** — пароль от закрытого ключа.
        1. На вкладке **SSL**:
            1. Включите настройки **Использовать SSL** и **Пропустить валидацию имени хоста**.
            1. В блоке **Способ**:
                1. Включите настройку **Набор сертификатов**.
                1. В поле **Корневой сертификат** укажите путь к файлу [SSL-сертификата для подключения](#get-ssl-cert).
    1. Нажмите кнопку **Тест соединения ...** для проверки соединения с БД. При успешном подключении будет выведен статус подключения, информация о СУБД и драйвере.
    1. Нажмите кнопку **Готово**, чтобы сохранить настройки соединения с БД.

{% endlist %}

## Примеры строк подключения {#connection-string}

{% include [Environment settings](../../../_includes/mdb/mdb-conn-strings-env.md) %}

{% include [How to see FQDN](../../../_includes/mdb/see-fqdn-in-console.md) %}

{% include [Connection strings for sharded cluster](../../../_includes/mdb/mrd/conn-strings-sharded.md) %}