
# Лабораторная работа 4.

## Процесс выполнения
### Создание и настройка контейнеров
Для выполнения лабараторной работы буду использовать Docker для Windows с WSL.
Создаем две папки для наши контейнеров:
- /d/Repositories/lab4/container-1
- /d/Repositories/lab4/container-2

Теперь создаем наш докерфайл:
```bash
touch Dockerfile
```
и прописываем в него такое содержимое:
![image](https://github.com/user-attachments/assets/643f23f3-07e2-4a60-89d8-06c9a15602f9)

Копируем:
```bash
cp Dockerfile ../container-2
```
Проверяем работу контейнеров:
```bash
docker build -t container-1 .
dcoker run -it --name con1 container-1
```
![image](https://github.com/user-attachments/assets/43a3e234-f68d-491b-b3fa-957d137c2cb0)
(Git Bash здесь меня подвел, использую CMD.EXE)
__Аналогично со вторым контейнером.__

### Создание и проверка работы сети
Создаем нашу сеть и присоединяем контейнеры:
```bah
docker network create myNet
docker network connect myNet con1
docker network connect myNet con2
```
![image](https://github.com/user-attachments/assets/5a38edba-42fe-4ce8-8e24-ba57daa61db4)
