Создание SSH-ключей для работы с Github
===================================

1. `ssh-keygen -t rsa -b 4096 -C "YOUR_EMAIL"` и нажимаем на всё `Enter` (т.е. принимаем значения по умолчанию: куда сохранить ключ, пароль не нужен и т.д.)
* `eval "$(ssh-agent -s)"` — проверяем, что SSH-агент запущен (должен появиться его PID)
* Если всё ОК, выполняем `ssh-add ~/.ssh/id_rsa`
* Mac OSX: Копируем публичный ключ: `pbcopy < ~/.ssh/id_rsa.pub`

  > Если на виртуальной машине такое не сработает, надо сделать `cat ~/.ssh/id_rsa.pub` и скопировать значение из терминала
* Идём по адресу [Setting: Keys](https://github.com/settings/keys) -> `New SSH key` -> вставляем ключ и, если нужно, задаём имя для этого ключа

В последующие разы `git` не будет требовать ввести логин и пароль при `push`'е.
