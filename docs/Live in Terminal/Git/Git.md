# Git

**Git** — це безкоштовна розподілена система контролю версій (VCS) з відкритим вихідним кодом, призначена для швидкої та ефективної роботи з будь-якими проектами, від невеликих до дуже великих.

Вона дозволяє нам записувати зміни в проекті і повертатися до певної версії відстежуваних файлів в будь-який момент часу.  Ця система може використовуватися багатьма людьми для ефективної спільної роботи та **співпраці над командними проектами**, де кожен розробник може мати власну версію проекту, розміщену на своєму комп'ютері. Пізніше ці індивідуальні версії проекту можуть бути об'єднані та адаптовані в основну версію проекту.

## Конфігурація та встановлення

Git використовується переважно через інтерфейс командного рядка, до якого ми можемо отримати доступ за допомогою терміналу.
Однак, спершу нам потрібно переконатися, що Git встановлено на наших комп'ютерах.
комп'ютерах.

Ви можете завантажити Git тут: <https://git-scm.com/downloads>

Клацніть посилання для завантаження для вашої операційної системи, а потім
дотримуйтесь вказівок майстра встановлення, щоб налаштувати все на вашому
комп'ютері!
Після встановлення запустіть ваш термінал і введіть наступну команду, щоб
перевірити, чи готовий Git до використання на вашому комп'ютері:

```bash
git --version
```

Якщо все пройшло успішно, вона повинна повернути версію Git'а, яка встановлена
на вашому комп'ютері.

> [!info] POSIX
> Якщо ви використовуєте комп'ютер Mac або Linux, ви можете використовувати стандартний термінал, який попередньо встановлений на вашому комп'ютері.

> [!info] Windows
> Якщо ви використовуєте Windows, ви можете скористатися вбудованим терміналом Powershell або термінал Git Bash, який постачається разом з інсталяцією Git з інсталяцією Git'а.

Щоб задати ім'я та пошту в конфігурації, введіть наступні команди, попередньо змінивши значення в лапках на правильні:

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

## Repositories

Працюючи з Git'ом, важливо бути знайомим з терміном репозиторій. Репозиторій Git'а - це "контейнер" для проекту, у якому програма Git відстежує усі зміни.

Можна виділити два основних типи Git-репозиторіїв:

- **Local repository** - ізольований репозиторій, що зберігається на вашому власному комп'ютері, де ви можете працювати над локальною версією вашого проекту.
- **Remote repository** - зазвичай зберігається на віддаленому сервері. Це особливо корисно, коли при роботі в команді - це місце, де ви можете ділитися своїм кодом проекту, бачити чужий код і інтегрувати його в свою локальну версію проекту, а також перенести свої зміни до віддаленого репозиторію.

У цьому відео ми будемо працювати тільки з локальними репозиторіями.

### Ініціалізація репозиторію

Щоб створити новий репозиторій і почати відстежувати свій проект за допомогою Git'а, відкрийте ваш термінал і перейдіть до головної теки вашого проекту,
а потім введіть наступну команду:

```bash
git init
```

Ця команда створить прихований каталог .git для вашого проекту, де Git зберігає всі внутрішні дані відстеження для поточного сховища.

### Staging and committing code

Committing - це процес, під час якого зміни "офіційно" додаються до сховища Git'а.

У Git'і ми можемо розглядати комміти як контрольні точки або знімки вашого проекту в його поточному стані. Іншими словами, ми зберігаємо поточну версію нашого коду в коміті. Ми можемо створювати стільки коммітів, скільки нам потрібно в історії коммітів, і ми можемо переходити між коммітами, щоб побачити різні версії коду нашого проекту. Це дозволяє нам ефективно керувати нашим прогресом і відстежувати проект у міру його розробки.

Зазвичай комміти створюються у певні логічні моменти розробки проекту, зазвичай після додавання певного вмісту, функцій або модифікацій (наприклад, нових функціональних можливостей або виправлень помилок).

#### Checking the status

Перебуваючи у теці проекту у нашому терміналі, ми можемо ввести для перевірки стану нашого сховища:

```bash
git status
```

Це команда, яка дуже часто використовується при роботі з Git'ом. Вона показує, які файли було змінено, які файли відстежуються тощо.
На основі інформації з команди git status ми можемо додати не відстежувані файли проекту до збірки на основі інформації, отриманої за допомогою команди git.
Пізніше git status повідомить про будь-які зміни, які ми зробили у відстежуваних файлах, перш ніж ми вирішимо знову додати їх до знову до сховища.

#### Staging ﬁles

З теки проекту ми можемо скористатися командою git add, щоб додати наші файли до сховища, що дозволить їх відстежувати.
Ми можемо додати конкретний файл до сховища за допомогою наступної команди командою

```bash
git add file.js
```

Щоб додати декілька файлів, ми можемо зробити так:

```bash
git add file.js file2.js file3.js
```

Замість того, щоб додавати файли окремо, ми також можемо додати всі файли з теки проєкту до області збірки:

```bash
git add .
```

За замовчуванням, це додасть всі файли і теки всередині теки проекту до збірки, звідки вони будуть готові до фіксації та відстежуватися.

#### Making commits

**Commit** - це знімок нашого коду в певний момент часу, який ми зберігаємо в історії коммітів нашого сховища. Після додавання усіх файлів які ми хочемо відслідковувати, до сховища за допомогою команди `git add`, ми готові до створення комміту.

Щоб зафіксувати файли зі сховища, ми використовуємо наступну команду
команду:

```bash
git commit -m "Commit message"
```

Всередині лапок ми повинні написати повідомлення про зміни, яке використовується для ідентифікації в історії коммітів. Хорошим тоном є дотримання одного із стандартів прийнятим у команді. Зазвичай це заголовок та тіло комміту, з резюме змін, які ви внесли.

#### Commit history

Щоб побачити всі комміти, які були зроблені для нашого проекту, ви можете скористатися наступною командою:

```bash
git log
```

У логах буде показана детальна інформація для кожного комміту, наприклад, ім'я автора, згенерований хеш для комміту згенерований хеш для комміту, дата і час комміту, а також повідомлення про комміти, яке ми надали.

Щоб повернутися до попереднього стану коду вашого проекту, який ви зафіксували, ви можете скористатися наступною командою:

```bash
git checkout <commit-hash>
```

Замініть `<commit-hash>` на фактичний хеш для конкретного комміту який ви хочете переглянути, який можна отримати за допомогою команди `git log`.

Щоб повернутися до останнього коміту (найновішої версії коду нашого проекту), ви можете ввести цю команду:

```bash
git checkout master
```

#### Ігнорування файлів

Щоб ігнорувати файли, які ви не бажаєте відстежувати або додавати до збірки, ви можете створити файл з назвою `.gitignore` у головній теці вашого проекту.

Усередині цього файлу ви можете перерахувати всі назви файлів та тек, які ви не бажаєте відстежувати (кожен проігнорований файл і теку слід переносити з нового рядка у файлі `.gitignore`).

Ви можете прочитати статтю про ігнорування файлів [за цим посиланням](https://help.github.com/en/articles/ignoring-files).

### Branches

**Гілку** можна інтерпретувати як індивідуальну часову шкалу коммітів нашого проекту.

За допомогою Git'у ми можемо створити багато таких альтернативних середовищ (тобто створити різні **гілки**), щоб інші версії коду нашого проекту могли існувати і відстежуватися паралельно.

Це дозволяє нам додавати нові (експериментальні, незавершені та потенційно вадливі) функції в окремі гілки, не торкаючись *"офіційної "* стабільної версії коду нашого проекту (яка зазвичай зберігається на гілці **master**).

Коли ми ініціалізуємо сховище і починаємо робити комміти, вони за замовчуванням зберігаються у гілці **master**.

#### Створення нової гілки

Ви можете створити нову гілку за допомогою наступної команди:

```bash
git branch <new-branch-name>
```

Створена нова гілка буде посиланням на поточний стан вашого сховища.


> [!tip]
> Гарна ідея створити гілку **develop**, де ви можете працювати над покращенням вашого коду, додаванням нових експериментальних можливостей, тощо. Після розробки і тестування цих нових функцій, щоб переконатися, що вони не містять помилок і можуть бути використані, ви можете об'єднати їх в основну гілку.

#### Зміна гілки

Щоб перейти до іншої гілки, скористайтеся командою **git checkout**:

```bash
git checkout <назва гілки>
```

Таким чином, ви переходите на іншу ізольовану тимчасову шкалу вашого проекту, змінюючи гілки.


> [!tip]
> Наприклад, ви можете працювати над різними функціями у вашому коді і мати окрему гілку для кожної функції. Коли ви переключаєтеся на гілку, ви можете фіксувати зміни коду, які впливають тільки на цю гілку. Потім ви можете переключитися на іншу гілку для роботи над іншою функцією, на яку не вплинуть зміни і фіксації, зроблені в попередній гілці.

Для створення нової гілки і одночасного переходу до неї ви можете використовувати прапорець **-b**:

```bash
git checkout -b <new-branch-name>
```

> [!info]
> Щоб переглянути список гілок вашого проекту, скористайтеся цією командою:
> - `git branch гілка`

Щоб повернутися до гілки **master**, скористайтеся цією командою:

```bash
git checkout master
```

#### Об'єднання гілок

Ви можете об'єднувати гілки в ситуаціях, коли ви хочете перенести зміни коду, які ви зробили в окремій гілці, в іншу гілку.

Наприклад, після того, як ви повністю реалізували і протестували нову функцію у вашому коді, ви хочете перенести ці зміни до стабільної гілки вашого проекту (якою зазвичай є гілка **master** за замовчуванням).

Щоб перенести зміни з іншої гілки до поточної гілки, ви можете скористатися цією командою:

```bash
git merge <назва гілки>
```

Ви заміните `<назва гілки>` на назву гілки, яку ви хочете інтегрувати у вашу поточну гілку.

#### Видалення гілки

Щоб видалити гілку, ви можете виконати команду **git branch** з прапором **-d**:

```bash
git branch -d <назва гілки>
```

ℹ️ Детальніше про розгалуження та злиття [за цим посиланням](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

---

## Посилання

- [Офіційна сторінка](https://git-scm.com/)
- [Git Cheat sheet](https://cs.fyi/guide/git-cheatsheet)
- [The free **Pro Git** book](https://git-scm.com/book/en/v2)
- [Learn about GitHub](https://guides.github.com/)
