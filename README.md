# Домашнее задание к занятию 3 «Резервное копирование» Шарапат Виктор

### Задание 1
- Составьте команду rsync, которая позволяет создавать зеркальную копию домашней директории пользователя в директорию `/tmp/backup`
- Необходимо исключить из синхронизации все директории, начинающиеся с точки (скрытые)
- Необходимо сделать так, чтобы rsync подсчитывал хэш-суммы для всех файлов, даже если их время модификации и размер идентичны в источнике и приемнике.
- На проверку направить скриншот с командой и результатом ее выполнения

### Решение 1:
![alt text](https://github.com/sharvik22/3md/blob/main/images/1-1.png)
![alt text](https://github.com/sharvik22/3md/blob/main/images/1-3.png)
![alt text](https://github.com/sharvik22/3md/blob/main/images/1-2.png)
---

### Задание 2
- Написать скрипт и настроить задачу на регулярное резервное копирование домашней директории пользователя с помощью rsync и cron.
- Резервная копия должна быть полностью зеркальной
- Резервная копия должна создаваться раз в день, в системном логе должна появляться запись об успешном или неуспешном выполнении операции
- Резервная копия размещается локально, в директории `/tmp/backup`
- На проверку направить файл crontab и скриншот с результатом работы утилиты.

### Решение 2:
### Резервное копирование по сети с использованием SSH-ключа домашней директории машины MV2 (/home/admon/) на машину MV1 (/tmp/backup/):

Содержимое домашней директории MV1
![alt text](https://github.com/sharvik22/3md/blob/main/images/2-3.png)

Содержимое папки tmp MV2
![alt text](https://github.com/sharvik22/3md/blob/main/images/2-1.png)

Скрипт

![alt text](https://github.com/sharvik22/3md/blob/main/images/2-7.png)


![alt text](https://github.com/sharvik22/3md/blob/main/images/2-2.png)

![alt text](https://github.com/sharvik22/3md/blob/main/images/2-4.png)
![alt text](https://github.com/sharvik22/3md/blob/main/images/2-5.png)
![alt text](https://github.com/sharvik22/3md/blob/main/images/2-6.png)

---

## Задания со звёздочкой*
Эти задания дополнительные. Их можно не выполнять. На зачёт это не повлияет. Вы можете их выполнить, если хотите глубже разобраться в материале.

---

### Задание 3*
- Настройте ограничение на используемую пропускную способность rsync до 1 Мбит/c
- Проверьте настройку, синхронизируя большой файл между двумя серверами
- На проверку направьте команду и результат ее выполнения в виде скриншота


### Задание 4*
- Напишите скрипт, который будет производить инкрементное резервное копирование домашней директории пользователя с помощью rsync на другой сервер
- Скрипт должен удалять старые резервные копии (сохранять только последние 5 штук)
- Напишите скрипт управления резервными копиями, в нем можно выбрать резервную копию и данные восстановятся к состоянию на момент создания данной резервной копии.
- На проверку направьте скрипт и скриншоты, демонстрирующие его работу в различных сценариях.
