Вот перевод файла `README.md` на русский язык:

```markdown
## Среда сборки RPM-пакетов для RHEL от Teddysun

Этот Docker-образ может использоваться для сборки RPM-пакетов.

Для получения дополнительной информации о Docker и технологиях контейнеризации обратитесь к [официальной документации][1].

## Поддерживаемые теги и ссылки на `Dockerfile`

- `latest`, `10` [*(Dockerfile)*][8]
- `9` [*(Dockerfile)*][7]
- `8` [*(Dockerfile)*][2]
- `7` [*(Dockerfile)*][3]

### Справочная информация

- Поддерживаемые архитектуры ([*подробнее*][4]): `amd64`, `arm64`

## Интеграция

RPM-пакеты будут собираться в директории `/home/builder/rpmbuild`, которая должна содержать исходные архивы, патчи и собранные RPM/SRPM-файлы.

## Подготовка хоста

Если вам нужно установить Docker самостоятельно, следуйте [официальному руководству по установке][5].

## Учётная запись пользователя и root-доступ

Пользователь `builder` (UID 1000) является членом групп users и wheel и имеет право выполнять команды sudo без пароля от любого пользователя и группы.

## Загрузка образа

Для CentOS 7

```bash
$ docker pull teddysun/rpmbuild:7
```

Для CentOS 8 Stream / Rocky Linux 8 / AlmaLinux 8

```bash
$ docker pull teddysun/rpmbuild:8
```

Для CentOS 9 Stream / Rocky Linux 9 / AlmaLinux 9

```bash
$ docker pull teddysun/rpmbuild:9
```

Для CentOS 10 Stream / Rocky Linux 10 / AlmaLinux 10

```bash
$ docker pull teddysun/rpmbuild:10
```

Образ можно найти на [Docker Hub][6].

## Запуск контейнера

Пример запуска контейнера для CentOS 7:

```bash
$ mkdir -m 777 -p /opt/builder7
$ docker run -it --rm -h buildbot --name rpmbuild7 -v /opt/builder7:/home/builder/rpmbuild teddysun/rpmbuild:7
```

Пример запуска контейнера для CentOS 8 Stream / Rocky Linux 8 / AlmaLinux 8:

```bash
$ mkdir -m 777 -p /opt/builder8
$ docker run -it --rm -h buildbot --name rpmbuild8 -v /opt/builder8:/home/builder/rpmbuild teddysun/rpmbuild:8
```

Пример запуска контейнера для CentOS 9 Stream / Rocky Linux 9 / AlmaLinux 9:

```bash
$ mkdir -m 777 -p /opt/builder9
$ docker run -it --rm -h buildbot --name rpmbuild9 -v /opt/builder9:/home/builder/rpmbuild teddysun/rpmbuild:9
```

Пример запуска контейнера для CentOS 10 Stream / Rocky Linux 10 / AlmaLinux 10:

```bash
$ mkdir -m 777 -p /opt/builder10
$ docker run -it --rm -h buildbot --name rpmbuild10 -v /opt/builder10:/home/builder/rpmbuild teddysun/rpmbuild:10
```

[1]: https://docs.docker.com/
[2]: https://github.com/teddysun/across/blob/master/docker/rpmbuild/Dockerfile.rpmbuild8
[3]: https://github.com/teddysun/across/blob/master/docker/rpmbuild/Dockerfile.rpmbuild7
[4]: https://github.com/docker-library/official-images#architectures-other-than-amd64
[5]: https://docs.docker.com/install/
[6]: https://hub.docker.com/r/teddysun/rpmbuild/
[7]: https://github.com/teddysun/across/blob/master/docker/rpmbuild/Dockerfile.rpmbuild9
[8]: https://github.com/teddysun/across/blob/master/docker/rpmbuild/Dockerfile.rpmbuild10
```

**Основные особенности перевода:**

1. **Технические термины:**
   - `RPM packages` → `RPM-пакеты`
   - `Supported architectures` → `Поддерживаемые архитектуры`
   - `password-less sudo` → `выполнять команды sudo без пароля`
   - `source archives` → `исходные архивы`

2. **Дистрибутивы Linux:**
   - Сохранены оригинальные названия (CentOS, Rocky Linux, AlmaLinux)
   - Указаны соответствующие версии (8, 9, 10)

3. **Команды и пути:**
   - Все команды Docker сохранены в оригинале
   - Пути (`/home/builder/rpmbuild`, `/opt/builder7`) не изменены
   - Права доступа (`mkdir -m 777`) сохранены

4. **Особенности работы:**
   - Подробно переведено описание пользователя `builder`
   - Указание на интерактивный режим (`-it`) и автоматическое удаление (`--rm`)
   - Монтирование томов (`-v /opt/builder7:/home/builder/rpmbuild`)

5. **Ссылки:**
   - Сохранена оригинальная нумерация ([1]-[8])
   - URL-адреса не изменены
   - Подписи к ссылкам переведены ("подробнее", "Dockerfile")
