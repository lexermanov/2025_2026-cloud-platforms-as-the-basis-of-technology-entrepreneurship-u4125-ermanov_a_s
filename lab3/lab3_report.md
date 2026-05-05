University: [ITMO University](https://itmo.ru/ru/)\
Faculty: [FICT](https://fict.itmo.ru)\
Course: Cloud platforms as the basis of technology entrepreneurship\
Year: 2025/2026\
Group: U4125\
Author: Ermanov Alexey Sergeevich\
Lab: Lab3\
Date of create: 05.05.2026\
Date of finished: 
## Лабораторная работа №3
**Тема:** Исследование Cloud Storage  

---

## Цель работы  
Ознакомиться с основными принципами работы облачного хранилища, изучить объектное хранение данных и получить практические навыки работы с Google Cloud Storage.

---

## Ход работы  

### 1. Создание Cloud Storage bucket  
Был создан bucket со следующими параметрами:

- Имя: `aermanov-bucket-lab3`  
- Регион: Multi-region (US)  
- Класс хранения: Standard  
- Тип доступа: Uniform
  
<img width="1786" height="861" alt="2026-05-05_19-28-12" src="https://github.com/user-attachments/assets/9916e2f6-b127-4713-a1d6-22b5d907452c" />

---

### 2. Загрузка файлов  
В созданный bucket было загружено 4 изображения формата `.jpg`.
<img width="1517" height="863" alt="2026-05-05_19-29-35" src="https://github.com/user-attachments/assets/532b4034-63d5-43dd-8f5a-932a8918f877" />

---

### 3. Создание папки и перемещение файлов  
Внутри bucket была создана папка `folderka`, после чего все изображения были перемещены в неё.
<img width="1512" height="761" alt="2026-05-05_19-35-12" src="https://github.com/user-attachments/assets/ce9ed150-e294-4ba7-b87e-643fefc03004" />

---

### 4. Настройка публичного доступа  
Для обеспечения публичного доступа был выполнен следующий шаг:

- Добавлен: `allUsers`  
- Назначена роль: `Storage Object Viewer`  

Это позволило предоставить доступ к файлам только на чтение без возможности их изменения.
<img width="1544" height="871" alt="2026-05-05_19-37-44" src="https://github.com/user-attachments/assets/3f3cac31-1e54-4a02-a704-c123abb057cc" />

---

### 5. Получение ссылки на файл  
Ссылка на файл была получена через контекстное меню объекта

Пример ссылки: https://storage.googleapis.com/lab3-0505/tie/_MG_3983.jpg

Ссылка была открыта в браузере, изображение успешно загрузилось
<img width="1542" height="634" alt="2026-05-05_19-38-31" src="https://github.com/user-attachments/assets/46d4b36f-221e-40a1-9eca-3443bde47320" />
<img width="1300" height="981" alt="2026-05-05_19-40-46" src="https://github.com/user-attachments/assets/a51bc5cd-43e2-4151-94ba-aee6136697ac" />

### 6. Удаление ресурсов  
После завершения работы:

- все файлы были удалены  
- bucket `aermanov-bucket-lab3` был удалён  

---

## Вывод  

В ходе лабораторной работы были изучены основные принципы работы объектного хранилища Google Cloud Storage. Был создан bucket, загружены и структурированы файлы, настроен публичный доступ через IAM, а также получена и проверена публичная ссылка на объект.  
