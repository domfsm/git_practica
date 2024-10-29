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
Команды не обязательно печатать и выполнять по очереди. Можно разделить двумя амперсандами (&&);
## Начало работы c Git
### Инициализируем репозиторий
#### Сделать дерикторию репозиторием 
```git init``` -- инициализировать;<br>
```rm -rf .git``` -- "разгитить" дерикторию;<br>
```git status``` -- проверка состояния репозитория;<br>
### Добавление файлов в репозиторий
```git add``` -- подготовить файлы к сохранению;<br>
```git add --all``` -- подготовили к сохранению все файлы в репозитории;<br>
```git add .``` -- добавить всю текущую дерикторию;<br>
### Делаем коммит
```git commit -m 'Мой первый коммит!'``` -- создает коммит c ключом ```-m```,<br> 
который присваивает коммиту сообщение;<br>
### Просматриваем историю коммитов
```git log``` -- просмотр истории коммитов;<br>
## Создаём удалённый репозиторий (GitHub)
1. Зайдите в свой профиль по ссылке https://github.com/username, <br>
где username — имя, которое вы указали при регистрации.
2. Создайте репозиторий. Название удалённого репозитория необязательно должно совпадать <br> 
с именем проекта у вас на компьютере. Но чтобы не путаться, лучше называть их одинаково.
## Генерируем SSH-ключ
### Проверка наличия SSH-ключа
```cd ~``` -- перешли в домашнюю директорию;<br>
```ls -la .ssh/``` -- список созданных ключей;<br>
### Инструкция по генерации SSH-ключа
1. Для генерации SSH-пары можно использовать программу ```ssh-keygen```<br>
```ssh-keygen -t ed25519 -C "email@yandex.ru"``` -- Если вы видите сообщение об ошибке, то, скорее всего, <br> 
ваша система не поддерживает алгоритм шифрования ed25519.<br> 
Ничего страшного: используйте другой алгоритм;<br>
```ssh-keygen -t rsa -b 4096 -C "email@yandex.ru"``` -- другой алгоритм;<br>
2. Программа запросит кодовую фразу (англ. passphrase) для доступа к SSH-ключу.
### Привязываем SSH-ключ
1. ```id_rsa.pub``` или ```id_ed25519.pub``` добавляем (публичный ключ) на удаленный ресурс (GitHub)
2. ```ssh -T git@github.com``` -- проверьте правильность ключа
## Связываем локальный и удалённый репозитории
```git remote add``` -- привязывает удалённый репозиторий к локальному;<br>
```git remote add origin git@github.com:%ИМЯ_АККАУНТА%/название репозитория``` -- пример привязки к GitHub<br>
```git remote -v ``` -- проверить, что репозитории связаны<br>
## Синхронизируем локальный и удалённый репозитории
```git push -u origin main``` -- отправить изменения на удалённый репозиторий<br> 
(eсли команда приведёт к ошибке, попробуйте заменить main на master);<br>
## Хеш — идентификатор коммита
* Git преобразует информацию о коммитах с помощью алгоритма SHA-1 и для <br> 
каждого из них рассчитывает уникальный идентификатор — хеш.
* Хеш — основной идентификатор коммита и позволяет узнать его автора,<br> 
дату и содержимое закоммиченных файлов
* Все хеши, а также таблицу соответствий ```хеш → информация о коммите``` Git хранит в папке ```.git```.
### Исследуем лог
 ```git log --oneline``` -- получить сокращённый лог;<br>
## Статусы файлов в Git
* ```untracked``` -- неотслеживаемый;
* ```staged``` -- подготовленный (то есть в списоке файлов, которые войдут в коммит);
* ```tracked``` -- отслеживаемый (файлы, которые уже были зафиксированы с помощью ```git commit```);
* ```modified``` -- изменённый (файл был закоммичен и после этого изменён);
```mermaid
graph LR;
untracked -- "git add" --> staged;
staged    -- "???"     --> tracked/comitted;

%% стрелка без текста для примера: 
  A --> B;

```