# git-hints

## Небольшой гит-репозиторий для самостоятельной работы

`git clone https://github.com/PraktikumJava/git-hints.git`

Хеш коммита

Таблица 'соответствия хеш → информация о коммите' хранится в папке .git

Результат хеширования в Git — символьная строка. Она относительно коротка (40 символов в случае SHA-1) и состоит из цифр
0—9 и латинских букв A—F (неважно, заглавных или строчных). Хеш обладает следующими важными свойствами:
- если хеш получить дважды для одного и того же набора входных данных, то результат будет гарантированно одинаковый;
- если хоть что-то в исходных данных поменяется (хотя бы один символ), то хеш тоже изменится (причём сильно).

git log

После вызова git log появляется список коммитов с их описанием.
1. Строка из цифр и латинских букв после слова commit — это уже знакомый вам хеш коммита.
2. Author — имя автора и его электронная почта.
3. Date — дата и время создания коммита.
4. Сообщение к коммиту.

Cокращённый хеш (первые несколько символов полного) можно использовать точно так же, как и полный.
Команда git log --oneline

HEAD — всему голова
При вызове команды git log вы также могли заметить надпись (HEAD -> master) после хеша одного из коммитов.
Файл HEAD (англ. «голова», «головной») — один из служебных файлов папки .git. Он указывает на коммит, который сделан 
последним (то есть на самый новый).
Убедитесь в этом с помощью терминала. Перейдите в папку .git командой cd. Посмотрите содержимое файла HEAD командой cat.
Внутри HEAD — ссылка на служебный файл: refs/heads/master (или refs/heads/main в зависимости от названия ветки).
Если заглянуть в этот файл, можно увидеть хеш последнего коммита.
Когда вы делаете коммит, Git обновляет refs/heads/master — записывает в него хеш последнего коммита. Получается, что
HEAD тоже обновляется, так как ссылается на refs/heads/master.

При работе с Git указатель HEAD используется довольно часто. Мы уже упоминали, что многие команды Git принимают в
качестве параметра хеш коммита. Если нужно передать последний коммит, то вместо его хеша можно просто написать слово 
HEAD — Git поймёт, что вы имели в виду последний коммит.


```mermaid
graph LR;
  untracked -- "git add" --> staged;
  staged    -- "git commit -m 'комментарий'"     --> tracked/comitted;
  staged    -- "внесены изменения в файл после git add"     <-- tracked/modified;

%% стрелка без текста для примера: 
  A --> B;
``` 

