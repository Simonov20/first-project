# 1.Командная строка
### 1) Навигация
pwd (от англ. print working directory, «показать рабочую папку») — покажи, в какой я папке;  
ls (от англ. list directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;  
ls -a — покажи также скрытые файлы и папки;  
ls -la — покажи также скрытые файлы и папки списком;  
cd first-project (от англ. change directory, «сменить директорию») — перейди в папку first-project;  
cd first-project/html — перейди в папку html, которая находится в папке first-project;  
cd .. — перейди на уровень выше, в родительскую папку;  
cd ~ — перейди в домашнюю директорию (/Users/Username);  
cd / — перейди в корневую директорию; 
 
Работа с файлами и папками  

### 2) Создание
touch index.html (англ. touch, «коснуться») — создай файл index.html в текущей папке;  
touch index.html style.css script.js — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;  
mkdir second-project (от англ. make directory, «создать директорию») — создай папку с именем second-project в текущей папке.  
### 3) Копирование и перемещение  
cp file.txt ~/my-dir (от англ. copy, «копировать») — скопируй файл в другое место;  
mv file.txt ~/my-dir (от англ. move, «переместить») — перемести файл или папку в другое место.  
### 4) Чтение  
cat file.txt (от англ. concatenate and print, «объединить и распечатать») — распечатай содержимое текстового файла file.txt. 
### 5) Удаление  
rm about.html (от англ. remove, «удалить») — удали файл about.html;  
rmdir images (от англ. remove directory, «удалить директорию») — удали папку images;  
rm -r second-project (от англ. remove, «удалить» + recursive, «рекурсивный») — удали папку second-project и всё, что она содержит.\  

# 2. Первый коммит

git init - создали репозиторий   
rm -rf .git - удалили подпапку .git если что-то пошло не так  
	ключ -r (от англ. recursive — «рекурсивно») позволяет удалять папки вместе с их содержимым;  
	ключ -f (от англ. force — «заставить») избавит вас от вопросов вроде «Вы точно хотите удалить этот файл?;  
git status - узнать текущий статус файлов в репозитории:  
+ инициализирован ли репозиторий
+ какая ветвь активна
+ какие файлы отслеживаются
+ какие будут добавлены в коммит
+ а какие не будут
git add - Подготовить файлы к сохранению, git add --all # подготовили к сохранению все файлы в репозитории;  
git commit -m ['комментарий к коммиту в кавычках'];    
Самая распространенная ошибка при попытке коммита, это забыть подготовить к коммиту(git add), иначе коммит не получится;  
git log - Просмотреть историю коммитов(git log --oneline - сокращенная версии - удобно);  

# 3. Удалённый репозиторий
SSH — протокол, который обеспечивает безопасный обмен данными в сети и использует для этого ключи;    
SSH-ключ — ваш виртуальный идентификатор в GitHub;    
SSH-ключ состоит из двух частей — публичной и приватной. Публичный ключ зашифрует данные, а приватный — расшифрует;    

### Инструкция по связыванию SSH-ключа и GitHub-аккаунта: 
1. $ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub" - генерации SSH-пары (жмем enter для подтверждения);  
2. ls -a ~/.ssh - проверка сгенерированных ключей(Файл в .pub — публичный, им можно делиться);  
3. $ clip < ~/.ssh/id_ed25519.pub - скопировать содержимое ключа в буфер обмена;  
4. Перейдите на GitHub и выберите пункт Settings  
5. В меню слева нажмите на пункт SSH and GPG keys.  
6. В открывшейся вкладке выберите New SSH key.  
7. Заполняем поля. В поле Key скопируйте ваш ключ из буфера обмена.  
8. Нажмите на кнопку Add SSH key.  
9. ssh -T git@github.com - Проверьте правильность ключа с помощью следующей команды.  
10. git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git   
	Перейдите на страницу удалённого репозитория(Git Hub), выберите тип SSH и скопируйте URL(раширение .git)   
	Команде необходимо передать два параметра: имя удалённого репозитория и его URL. В качестве имени используйте слово origin  
11. git remote -v - Убедиться, что репозитории связаны, -v — короткая форма флага --verbose (англ. «подробный»)  
12. git push - Отправить изменения на удалённый репозиторий.  
	git push -u origin main - В первый раз эту команду нужно вызвать с флагом -u и параметрами origin.    
	В дальнейшем при работе с удалённым репозиторием флаг -u можно опустить и писать просто git push.  