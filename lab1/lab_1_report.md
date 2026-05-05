University: [ITMO University](https://itmo.ru/ru/)\
Faculty: [FICT](https://fict.itmo.ru)\
Course: Cloud platforms as the basis of technology entrepreneurship\
Year: 2025/2026\
Group: U4125\
Author: Ermanov Alexey Sergeevich\
Lab: Lab1\
Date of create: 05.05.2026\
Date of finished: 
# Лабораторная работа №1
## Обзор Google Cloud и исследование основных сервисов

## Цель работы

Ознакомиться с основными возможностями платформы Google Cloud, изучить сервисы IAM, Compute Engine и Cloud Storage, а также проверить влияние ролей доступа на работу с ресурсами.

## Ход работы

### 1. Получение доступа к Google Cloud

Была заполнена форма для получения доступа к Google Cloud. После этого был открыт доступ к проекту.

---

### 2. Создание Service Account

Был создан сервисный аккаунт:

`aermanov-sa-lab1`

Аккаунту была назначена роль:

`Storage Admin`

<img width="1275" height="768" alt="2026-05-05_15-11-42" src="https://github.com/user-attachments/assets/6637443b-0842-4448-919f-b463576bcfa1" />

<img width="1207" height="819" alt="2026-05-05_15-13-42" src="https://github.com/user-attachments/assets/12481139-a1a5-40ee-86ee-e6b2bf845c0e" />

---

### 3. Создание виртуальной машины

Была создана виртуальная машина:

`aermanov-vm-lab1`

Параметры:

- Machine type: e2-micro  
- Provisioning model: Spot  

Виртуальная машина была успешно запущена.

<img width="1449" height="860" alt="2026-05-05_15-17-04" src="https://github.com/user-attachments/assets/9bb5c3d2-b4cc-4c88-8b7c-5670bd148a7b" />

---

### 4. Подключение к VM и работа с Cloud Storage

Подключение к виртуальной машине было выполнено через SSH. С помощью утилиты gcloud найден бакет lab1-bucket-itmo и скопированы 3 файла в локальную папку на VM. Командой ls -lah проверил наличие файлов на VM.

<img width="1095" height="478" alt="2026-05-05_15-29-14" src="https://github.com/user-attachments/assets/ee36d57d-2084-4980-bbfb-3ce1d9ef64fd" />

### 5. Смена роли и проверка доступа

Поменял права доступа моего service account с Storage Admin на Compute Viewer и попробовал скопировать файлы снова. Вышла ошибка, у service account отсутствуют права на доступ к объектам Cloud Storage.

<img width="1035" height="902" alt="2026-05-05_15-43-58" src="https://github.com/user-attachments/assets/6c5b3642-a6e2-4087-8ee0-1ce033a5a6fa" />

<img width="1098" height="181" alt="2026-05-05_16-05-57" src="https://github.com/user-attachments/assets/b5a28977-8b44-4b2f-b22a-6914f20593be" />

## Итоговый вывод

После изменения роли service account с Storage Admin на Compute Viewer доступ к объектам Cloud Storage был ограничен. Попытка скачать файл из бакета завершилась ошибкой 403, что подтверждает отсутствие необходимых прав.

Таким образом, IAM-роли напрямую влияют на доступ к ресурсам Google Cloud, и без соответствующих разрешений выполнение операций с Cloud Storage невозможно.
