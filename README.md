# routine
---

## Развернуть репозиторий локально
```bash

```
---
## Построить диаграмму классов
```bash
pip install pylint
```
```bash
pyreverse -o dot my_dir_name/
```
https://dreampuf.github.io/GraphvizOnline/
---
## Собрать дистрибутив
устанавливаем модуль
```bash
pip install pyinstaller
```
создаем файл .spec, папки build и dist создаются автоматически
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
pyinstaller main.spec
```
