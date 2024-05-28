# Ansible Playbook: Установка и Настройка

Этот Ansible playbook автоматизирует установку и настройку NGINX, Lighthouse, ClickHouse и Vector на указанных хостах.

## Обзор

Playbook организован в несколько ролей, каждая из которых отвечает за определенный компонент:

- **Установка и Настройка NGINX**: Устанавливает NGINX и настраивает его параметры.

- **Установка и Настройка Lighthouse**: Устанавливает Lighthouse и настраивает NGINX для его обслуживания.

- **Установка и Настройка ClickHouse**: Загружает и устанавливает пакеты ClickHouse, настраивает сервер ClickHouse и создает базу данных.

- **Установка и Настройка Vector**: Загружает и устанавливает пакеты Vector, настраивает Vector и настраивает службу systemd.

## Предварительные требования

Перед запуском этого playbook убедитесь в следующем:

- Ansible установлен на машине, с которой вы запускаете playbook.
- Есть доступ по SSH к целевым хостам.
- Есть подключение к Интернету для загрузки пакетов.

## Использование

1. Клонируйте этот репозиторий на ваш локальный компьютер:

    ```bash
    git clone https://github.com/kshatyy/Ansible.git
    ```

2. Перейдите в каталог playbook:

    ```bash
    cd ansible-playbook-directory
    ```

3. Обновите файл инвентаря (`inventory.yml`) с вашими целевыми хостами.

4. Настройте переменные в playbook по мере необходимости. Вы можете найти их в каталоге `group_vars`.

5. Запустите playbook:

    ```bash
    ansible-playbook -i inventory/prod.yml site.yml
    ```

## Теги

Playbook поддерживает следующие теги, позволяя вам выборочно запускать определенные части playbook:

- **nginx**: Устанавливает и настраивает NGINX.
- **lighthouse**: Устанавливает и настраивает Lighthouse.
- **clickhouse**: Устанавливает и настраивает ClickHouse.
- **vector**: Устанавливает и настраивает Vector.

Чтобы запустить конкретный тег, используйте опцию `-t`, за которой следует имя тега:

```bash
ansible-playbook -i inventory/prod.yml site.yml -t nginx
```

## Скриншоты к ДЗ
5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.
![Снимок](https://github.com/kshatyy/Ansible/assets/154414081/e1940b9c-4ce3-4fa7-b61c-c4025b647dbb)

6. Попробуйте запустить playbook на этом окружении с флагом `--check`.
![Снимок1](https://github.com/kshatyy/Ansible/assets/154414081/1cddf657-366f-423c-a90d-c52f5f2e0da0)

7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.
![Снимок2](https://github.com/kshatyy/Ansible/assets/154414081/011efa08-fb6e-4e0d-9723-4ffafe4a5f74)
![Снимок3](https://github.com/kshatyy/Ansible/assets/154414081/af753db4-895c-443e-ab6a-1d5bad324249)
![Снимок4](https://github.com/kshatyy/Ansible/assets/154414081/6249ba61-6693-4733-9686-0ae625af1faf)

8. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.
![Снимок](https://github.com/kshatyy/Ansible/assets/154414081/1d235031-e8b6-4ef3-92fa-e9a9b491cb0b)
![Снимок1](https://github.com/kshatyy/Ansible/assets/154414081/d92dccd3-fe8b-4c15-ab38-a53f0363518e)
![Снимок2](https://github.com/kshatyy/Ansible/assets/154414081/88b76c07-796f-40ce-a2e1-2cdb957ddb2f)

10. Готовый playbook выложите в свой репозиторий, поставьте тег 08-ansible-03-yandex на фиксирующий коммит, в ответ предоставьте ссылку на него.

```bash
https://github.com/kshatyy/Ansible/releases/tag/08-ansible-03-yandex
```
