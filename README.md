# Как начать работать с Git

Собрал и описал **основные команды**, чтобы при получении issues от **Алóиса Альцгéймера** было где подсмотреть и ответить **git reset HEAD --hard**

Тестовый репозиторий, подписывайтесь на наш телеграмм канал по [ссылке](https://t.me/YellowHummer)

## Установи GIT

```sh
для Windows скачать по ссылке http://msysgit.github.io
для RPM > yum install git-core
для DEB > apt-get install git
```

## Настрой Git, так Git связывает Ваш аккаунт и Ваши изменения

```sh
git config --global user.name JohnnyDoe         // Ваше имя
git config --global user.email jshut@yandex.ru  // Ваш Email
```

## Настрой Git для Windows

```sh
git config --global core.autocrlf true
git config --global core.safecrlf false
git config --global core.eol native
```

## Настрой Git для работы на Windows с репозиторием использующимся в Linux

```sh
git config --global core.autocrlf input
git config --global core.safecrlf false
git config --global core.eol native
```

## Создай локальный GIT репозиторий для своего продукта

```sh
cd ./git                    // открываем каталог "git" в папке пользователя OS
git init ./PROJECTNAME      // инициализируем каталог проекта. <PROJECTNAME> - любое имя вашего проекта, может не совпадать с именем удаленного репозитория.
cd ./PROJECTNAME            // открываем каталог проекта
```

## Подключи стандартные каталоги

```sh
git remote add origin https://github.com/johnnyshut/HowToGitHub     // создаем ветвь разработки "origin" в удаленном репозитории
git fetch origin                                                    // получение изменений и вывод их на экран
git merge origin/master                                             // объединение изменений с локальным проектом
```

## Создай файл в локальном репозитории

```sh
mkdir hello             // создадим каталог в локальном репозитории
cd hello                // перейдем в созданный каталог "hello"
touch helloWorld.txt    // создадим файл "helloWorld.txt"!
```

## Свяжи новый файл с удаленным репозиторием

```sh
git add helloWorld.txt          // отмечаем файл для отправки или команда "git add .", чтобы отметить все файлы
git commit -m "First Commit"    // помечаем все новые и измененные файлы сообщением (commit)
```

## Отправь код на удаленный репозиторий

```sh
git push -u origin master   // флаги используются только в первый раз, потом используем команду без флагов "git push"
git status                  // вывод информации об изменениях которые были сделаны
git pull                    // скачивание репозитория, полностью. Выполняет последовательно fetch и merge, без вывода на экран статусов
```

## Как вызвать справку

```sh
git help <команда>
git <команда> --help
man git-<команда>
```

## Подключаемся на другом компьютере

## Клонирование репозитория

```sh
git clone https://github.com/johnnyshut/HowToGitHub     // git скачает удаленный репозиторий в новую папку HowToGitHub и создаст локальный репозиторий
```

## После изменений в локальном репозитории, фиксируем изменения

```sh
git add .
git commit -m "I changed the my life!"
git push
```

## Откат изменений

```no-highlight
git reset HEAD --hard           // полный откат до предыдущего коммита
git checkout helloWorld.txt     // сброс изменений в файле на версию коммита
git checkout v1                 // откат до установленного тега, например v1
```

Рекомендую ознакомиться так же с другими подсказками:

- Настройка [gitattributes](/gitattributes.md)
- TODO

*P.S. Все команды актуальны для любого сервиса Git
Перед работай с Git зарегистрируйся на github.com и создайте репозиторий
Инструкция по созданию репозитория по [ссылке](https://help.github.com/en/articles/creating-a-new-repository) на официальном сайте.
