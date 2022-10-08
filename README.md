
![](https://img.shields.io/badge/Telegram-t.me%2Ftheonlywiilldii-brightgreen)(https://t.me/theonlywiilldii) ![](https://img.shields.io/badge/VK-vk.com%2Ftheonlymark-red)(https://vk.com/theonlymark)

# Система контроля версий Git
![GitHub](https://miro.medium.com/max/4800/1*cTPHRuyn46e4Su4QJ7S5NQ.gif)
- [X] **Первоначальная настройка Git** :blue_heart:
  
> Первое, что вам следует сделать после установки Git — указать ваше имя и адрес электронной почты.
  ```
    git config --global user.name ""
    git config --global user.email ""
  ```

> Создать локально новый репозиторий
  ```
    git init
  ```

- [X] **Просмотр конфигураций удаленных репозиториев** :green_heart:

> Список ваших удаленных подключений к другим репозиториям.
  ```
    git remote
  ```

> Аналогично команде выше, но включает URL-адрес каждого подключения.
  ```
    git remote -v
  ```

> Создание нового подключения к удаленному репозиторию.
  ```
    git remote add <name> <url>
  ```

> Удаление подключения к удаленному репозиторию с именем.
  ```
    git remote rm <name>
  ```

- [X] **Работа с удалёнными репозиториями** :purple_heart:
  
> Клонировать существующий репозиторий
  ```
    git clone <url>
  ```

- [X] **Загрузка репозитория на сайт/локальный сервер** :heart:
  
+ Локальный
  
> Добавить все измененные файлы в индекс репозитория.
  ```
    git add .
  ```

> Запись индексированных изменений в репозиторий Git.
  ```
    git commit -m "Первый коммит"
  ```

> Переимновать индексированные изменения

  ```
    git commit --amend -m "Новый коммит"
  ```
- Сайт

>Отправка изменений
  ```
  git push -u origin main
  ```

> Извлечь из указанного удаленного репозитория копию текущей ветки и немедленно слить ее с локальной копией. 

  ```
  git pull
  ```

- [X] Работа с ветками в Git :heartpulse:
> Команда git branch — главный инструмент для работы с ветвлением. С ее помощью можно добавлять новые ветки, перечислять и переименовывать существующие и удалять их.
>> Список всех существующих веток
  ```
    git branch -av
  ```

> Переключение в ветки
  ```
    git checkout <ветка>
  ```

> Создать новую ветку
  ```
    git branch <новая-ветка>
  ```

> Создать новую ветку и сразу переключится в нее
  ```
    git checkout -b <новая-ветка>
  ```

> Удалить локальную ветку
  ```
    git branch -d <ветка>
  ```

- [X] **Локальные изменения** :yellow_heart:
  
> Файлы в рабочей директории были изменены
  ```
    git status
  ```

> Изменения в отслеживаемых файлах
  ```
    git diff
    git diff <commit1> <commit2>
  ```

- [X] **История коммитов** :alien:

> Показать всю историю коммитов начиная с последних
  ```
    git log
  ```
> Показать историю изменений определенного файла
  ```
    git log -p <файл>
  ```
> Кто, какие и когда изменения вносил в <файл>
  ```
    git blame <файл>
  ```

- [x] **Отмена** :hankey:

> Удалить все локальные изменения в рабочем каталоге
>> Это самый прямой, ОПАСНЫЙ и часто используемый вариант. При использовании аргумента `--hard` указатели в истории коммитов обновляются на указанный коммит. Затем происходит сброс раздела проиндексированных файлов и рабочего каталога до указанного коммита. Все предыдущие ожидающие изменения в разделе проиндексированных файлов и рабочем каталоге сбрасываются в соответствии с состоянием дерева коммитов. Это значит, что любая работа, находившаяся в состоянии ожидания в разделе проиндексированных файлов и рабочем каталоге, будет потеряна.
  ```
  git reset --hard <хэшcommit>
  ```

> Это режим работы по умолчанию. Указатели ссылок обновляются. Раздел проиндексированных файлов сбрасывается до состояния указанного коммита. Любые изменения, которые были отменены в разделе проиндексированных файлов, перемещаются в рабочий каталог.

  ```
  git reset --mixed <хэшcommit>
  ```

> При передаче аргумента `--soft` выполняется обновление указателей, и на этом операция сброса останавливается. Раздел проиндексированных файлов и рабочий каталог остаются неизменными. Четко продемонстрировать такое поведение довольно сложно. 

  ```
  git reset --soft <хэшcommit>
  ```

> Сбрасывает раздел проиндексированных файлов и рабочий каталог до состояния последнего коммита. Флаг `--hard` говорит Git, что нужно не только отменить изменения в разделе проиндексированных файлов, но и перезаписать все изменения в рабочем каталоге. Другими словами, эта команда уничтожит все неотправленные изменения, поэтому перед ее использованием убедитесь, что вы действительно хотите удалить ваши локальные наработки.

```
  git reset --hard
```

> Вернуть файл из стейджинга, но оставить изменения в нем неприкосновенными.

```
  git restore --staged myFile.txt
```

> Отменить локальные изменения в конкретном файле

```
  git restore myFile.txt
```

![END](https://psv4.userapi.com/c237331/u559371293/docs/d12/1a3a199c5170/1640455153605.gif?extra=ko8YyRMV1ojxhMeXxim_YI92ExA_QehLoVxSrw0Zsd68JICv9rbMOXM4EcDAq6X7zgHdtgsXeldrC-kbgnO0_DOKipA3YdUItvr_P9pVA_DjASJSnjU1YmOfFFj2sxtZUNRAOe2VpWRGkYYmFv2xvSVqVWg)![END](https://psv4.userapi.com/c237331/u559371293/docs/d12/1a3a199c5170/1640455153605.gif?extra=ko8YyRMV1ojxhMeXxim_YI92ExA_QehLoVxSrw0Zsd68JICv9rbMOXM4EcDAq6X7zgHdtgsXeldrC-kbgnO0_DOKipA3YdUItvr_P9pVA_DjASJSnjU1YmOfFFj2sxtZUNRAOe2VpWRGkYYmFv2xvSVqVWg)![END](https://psv4.userapi.com/c237331/u559371293/docs/d12/1a3a199c5170/1640455153605.gif?extra=ko8YyRMV1ojxhMeXxim_YI92ExA_QehLoVxSrw0Zsd68JICv9rbMOXM4EcDAq6X7zgHdtgsXeldrC-kbgnO0_DOKipA3YdUItvr_P9pVA_DjASJSnjU1YmOfFFj2sxtZUNRAOe2VpWRGkYYmFv2xvSVqVWg)