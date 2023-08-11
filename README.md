Git

~/ - домашняя директория
./ - текущая директория
../ - предыдущая директория (каталог на уровень выше)

mkdir - создать директорию

cd - изменить директорию (сменить директорию, перейти в каталог)

> - направление

git init -инициализация (создание) гит репозитария, сделать папку репозиторием

ls - просмотр содержимого каталога

каталог - папка

85 команд Linux на все случаи жизни. Ну почти - Лайфхакер
https://lifehacker.ru/komandy-linux/

pwd - выводит текущую рабочую директорию (не особо нужна, т.к. и так видно по сути)

/ используется, чтобы перемещаться через несколько директорий

ls -a - выводит выводит расширенный список (отобразятся все скрытые файлы)

touch - создать файл

cp - копирование файлов

mv - перемещение файлов и папок

С помощью флага -p можно создать целую структуру директорий одной командой: mkdir -p.

cat - чтение файлов (работает только с текстовыми файлами)

rm - удаление файлов
rmdir - удаление папок
rm -r удаляет папку со всем содержимым

&& - разделение команд

~ - называется тильда

git config --global user.name "User Namovich" 
git config --global user.email username@yandex.ru

Все глобальные настройки Git хранит в файле .gitconfig в домашней директории

cat ~/.gitconfig  - показывает текущие значения настроек
git config --list - показывает текущие значения настроек

rm -rf .git - "разгитить" папку, если что-то пошло не так

ключ -r (от англ. recursive — «рекурсивно») позволяет удалять папки вместе с их содержимым
ключ -f (от англ. force — «заставить») избавит вас от вопросов вроде «Вы точно хотите удалить этот файл? А этот? И этот тоже?»

git status - проверить состояние репозитория

git add - подготовить файлы к сохранению

git add --all - команда для отслеживания всех файлов в репозитории
--all ключ, который позволяет подготовить к сохранению все файлы в репозитории

git add .  - можно добавить в репозиторий текущую папку со всеми файлами

git commit - выполнить коммит

-m (от англ. message — «сообщение»),  ключ, который присваивает коммиту сообщение

git log - просмотреть историю коммитов

ls -la .ssh/ - вывести список созданных ключей

ssh-keygen - генерация SSH-пары

ls -a ~/.ssh  - проверить, что ключи действительно сгенерировались

-la - ключ, показывающий расширенную информацию о содержимом

clip < ~/.ssh/id_ed25519.pub - скопировать содержимое ключа в буфер обмена

ssh -T git@github.com - проверить правильность ключа

git remote add - привязать удалённый репозиторий к локальному

Команде необходимо передать два параметра: имя удалённого репозитория и его URL. В качестве имени используйте слово origin. А URL вы скопировали со страницы удалённого репозитория.

git remote -v - убедиться, что репозитории связаны

Флаг -v — короткая форма флага --verbose (англ. «подробный»). Он позволяет показать больше информации в выводе.

git push -  Отправить изменения на удалённый репозиторий

В первый раз эту команду нужно вызвать с флагом -u и параметрами origin (имя удалённого репозитория) и main или master (название текущей ветки). Флаг -u свяжет локальную ветку с одноимённой удалённой. Как вы связывали локальный и удалённый репозитории в предыдущем уроке, так же и здесь нужно дополнительно связать ветки.

Дополнительная информация(дом. зад. 2).

Git преобразует информацию о коммитах с помощью алгоритма SHA-1 и для каждого из них рассчитывает уникальный идентификатор — хеш.

Хеш — основной идентификатор коммита и позволяет узнать его автора, дату и содержимое закоммиченных файлов.

Все хеши, а также таблицу соответствий хеш → информация о коммите Git хранит в папке .git.


Можно вызвать не только полный лог, но и сокращённый — это делается командой git log --oneline.

В сокращённом логе выводятся сокращённые хеши — их можно использовать точно так же, как и полные.


Когда вы делаете коммит, Git обновляет refs/heads/master — записывает в него хеш последнего коммита. Получается, что HEAD тоже обновляется, так как ссылается на refs/heads/master.

При работе с Git указатель HEAD используется довольно часто. Мы уже упоминали, что многие команды Git принимают в качестве параметра хеш коммита. Если нужно передать последний коммит, то вместо его хеша можно просто написать слово HEAD — Git поймёт, что вы имели в виду последний коммит.

В числе прочих файлов в папке .git есть служебный файл HEAD. Он указывает на самый свежий коммит.

Вместо хеша последнего коммита можно написать слово HEAD — Git вас поймёт.
