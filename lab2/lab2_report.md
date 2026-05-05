University: [ITMO University](https://itmo.ru/ru/)\
Faculty: [FICT](https://fict.itmo.ru)\
Course: Cloud platforms as the basis of technology entrepreneurship\
Year: 2025/2026\
Group: U4125\
Author: Ermanov Alexey Sergeevich\
Lab: Lab2\
Date of create: 05.05.2026\
Date of finished: 
# Лабораторная работа №2
## Развертывание сервиса в Cloud Run

## Цель работы  
Ознакомиться с сервисом Cloud Run, изучить процесс развертывания контейнерного приложения, а также проанализировать работу сервиса с использованием логов и метрик.

## Ход работы  

### 1. Создание сервиса Cloud Run  
В рамках лабораторной работы был создан сервис в Google Cloud Run.

Для развертывания использовался контейнерный образ:
us-docker.pkg.dev/cloudrun/container/hello
<img width="1276" height="683" alt="2026-05-05_16-27-51" src="https://github.com/user-attachments/assets/77206536-5b2d-40c1-baa0-a84740340a04" />


Параметры сервиса:
- имя: lab2-ae-hello  
- регион: europe-west1 (Belgium)

Сервис был успешно развернут и получил публичный URL.

---

### 2. Тестирование сервиса  
Был выполнен переход по URL сервиса.
<img width="1524" height="798" alt="2026-05-05_16-28-34" src="https://github.com/user-attachments/assets/03438b42-1dff-42fb-aa90-cd14aa14cfd5" />
<img width="1293" height="954" alt="2026-05-05_16-29-22" src="https://github.com/user-attachments/assets/6361cb7f-61c4-4b09-a1e6-ba9124716db3" />

Результат:
отображается страница "It's running!"

Это подтверждает, что сервис корректно работает и обрабатывает HTTP-запросы.

---

### 3. Анализ логов  
В разделе Logs были проанализированы записи работы сервиса.

<img width="1539" height="825" alt="2026-05-05_16-30-14" src="https://github.com/user-attachments/assets/e2cdaa2b-b3db-4f3c-afb4-b6348296754e" />

В логах зафиксировано:
- успешный запуск контейнера  
- прохождение health-check (TCP probe succeeded)  
- HTTP-запросы с кодом 200  
- сообщения о готовности ревизии  

Ошибок обнаружено не было.


---

### 4. Анализ метрик  
В разделе Metrics были проанализированы следующие показатели:
- количество запросов (Request count)  
- задержка обработки (Latency)  
- загрузка CPU и памяти  
- количество инстансов  

<img width="1533" height="864" alt="2026-05-05_16-33-59" src="https://github.com/user-attachments/assets/ac79097e-3eeb-40fb-a7ad-513adf037604" />
<img width="1538" height="864" alt="2026-05-05_16-34-12" src="https://github.com/user-attachments/assets/d2e61197-e99b-44db-afa1-af439fae08ea" />

Вывод:
- сервис корректно масштабируется  
- нагрузка минимальная  
- задержки находятся в пределах нормы  
- ошибок нет

---

### 5. Изменение конфигурации (порт)  
Была создана новая ревизия с изменением порта с 8080 на 8090.

<img width="1489" height="860" alt="2026-05-05_16-42-51" src="https://github.com/user-attachments/assets/3a54ce48-c753-438a-ad04-125d2366fd46" />

Результат:
- сервис продолжил работать корректно  
- контейнер успешно запустился  
- ошибки отсутствуют  

Причина:
Cloud Run использует переменную окружения PORT, поэтому контейнер автоматически адаптируется к заданному порту.


---

### 6. Переключение трафика между версиями  
Было выполнено распределение трафика между двумя ревизиями:
- первая ревизия — 50%  
- вторая ревизия — 50%  

<img width="1535" height="801" alt="2026-05-05_16-43-23" src="https://github.com/user-attachments/assets/9d5ac5b2-62ff-431f-b227-396f3af47d18" />
<img width="1251" height="940" alt="2026-05-05_16-43-50" src="https://github.com/user-attachments/assets/9b58d410-aa1e-48d3-9476-da4769124bfc" />
<img width="1270" height="834" alt="2026-05-05_16-45-14" src="https://github.com/user-attachments/assets/d358ac6a-463a-4e4a-ae23-a0fe0e357337" />
<img width="1534" height="815" alt="2026-05-05_16-45-39" src="https://github.com/user-attachments/assets/5b2ab4cb-2135-43e2-a3fd-9f37eaa99e02" />
<img width="1540" height="625" alt="2026-05-05_16-46-20" src="https://github.com/user-attachments/assets/4d8dd0ff-fedc-47f5-8f3b-e80e49c9b442" />


Результат:
- обе версии обрабатывают запросы  
- сервис остается доступным  
- ошибок не возникает

---


## Вывод  
В ходе лабораторной работы был изучен сервис Cloud Run.

Были получены навыки:
- развертывания контейнерного приложения  
- тестирования сервиса  
- анализа логов и метрик  
- изменения конфигурации  
- управления версиями и трафиком  

Cloud Run позволяет быстро развертывать приложения и автоматически масштабировать их без управления инфраструктурой.
- доступ: публичный (Allow public access)  

Сервис был успешно развернут и получил публичный URL.
