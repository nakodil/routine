# routine

---
## Разворачиваем репозиторий локально
Инициализируем локальный репозиторий
```bash
git init
```
Подключаем удаленный репозиторий к локальному
```bash
git remote add origin https://github.com/my_user/my_project.git
```
Копируем содержимое удаленного репозитория в локальный
```bash
git pull origin main
```

---
## Строим диаграмму классов
Устанавливаем модуль
```bash
pip install pylint
```
Создаем файлы .dot (classes.dot, packages.dot) для папки
```bash
pyreverse -o dot my_dir_name/
```
Просматриваем .dot файлы на сайте
https://dreampuf.github.io/GraphvizOnline/

---
## Собираем дистрибутив
Устанавливаем модуль
```bash
pip install pyinstaller
```
Создаем файл .spec, папки build и dist создаются автоматически
```bash
pyinstaller -makespec --onefile --windowed my_file_name.py
```
В Analytics файла .spec добавляем в datas имя папки с ресурсами
```python
datas=[
    ('assets', 'assets'),
],
```
В EXE файла .spec добавляем аррумент icon с путем к файлу иконки
```python
icon='assets/img/icon.ico',
```
Собираем .exe файл
```bash
pyinstaller my_file_name.spec
```

---
### ruff.toml
```python
[lint]
select = ["ALL", "E501"]
ignore = [
    "FBT001",
    "FBT002",
    "FBT003",
    "RUF001",
    "RUF002",
    "RUF003",
    "T201",
    "PERF402",
    "S311",
    "S605",
    "S607",
]
```
