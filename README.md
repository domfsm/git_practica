# Основы Git
## Базовые команды в консоли
### Навигация 
```pwd```    -- показать рабочую дерикторию;<br>
```ls```     -- отобразить содержимое дериктории;<br>
```ls -a```  -- покажет скрытые файлы м папки, название которых ничинаются с ".";<br>
```cd``` -- сменить дерикторию;<br>
```cd ..``` -- перейти на уровень выше;<br>
```cd ~``` -- перейтив домашнюю дерикторию;<br>
```cd /``` -- перейтив корневую дерикторию;<br>
### Работа с файлами и папками
#### Создание
```touch index.html``` -- создание файла в текущей дериктории;<br>
```touch index.html style.css script.js``` -- созлание нескольких файлов;<br>
```mkdir``` -- создание дериктории;<br>
#### Копирование и перемещение
```cp file.txt ~/my-dir``` -- скопирует файл в другое место;<br>
```mv file.txt ~/my-dir``` -- переместит файл или дерикторию в другое место;<br>
#### Чтение
```cat file.txt``` -- чтение файла(распечатай содержимое текстового файла);<br>
#### Удаление 
```rm about.html``` -- удаление файла;<br>
```rmdir images``` -- удалить дерикторию;<br>
```rm -r``` -- "recursive" удалить дерикторию и все, что она содержит;<br>
#### Полезные возможности
Команды не обязательно печатать и выполнять по очереди. Можно разделить двумя амперсандами (&&)
