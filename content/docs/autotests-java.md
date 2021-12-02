---
title: "Работа с Автотестами на курсе «Java-Разработчик»"
weight: 10
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# Работа с автотестами «Java-Разработчик»

{{< hint info >}}
ℹ️ На вашем курсе есть задания с автотестами в gitlab. Это позволит вам получать ответ соответствует ли ваше решение требования в домашнем задании.

{{< /hint >}}

## ⬇️ Получение материалов домашних заданий

Если задание с автотестами, то ниже условия домашнего задания, увидите блок `Сдача домашнего задания`**:**

![dd%20eed3486088c5418a87e09751164fb9c7/Untitled.png](dd%20eed3486088c5418a87e09751164fb9c7/Untitled.png)

Нажмите кнопку `Приступить к выполнению`

Ветка и Merge Request будет созданы автоматически

![dd%20eed3486088c5418a87e09751164fb9c7/Untitled%201.png](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%201.png)

Нажмите **Перейти в Gitlab** и вам откроется репозиторий для выполнения домашнего задания

{{< hint info >}}
ℹ️ Для каждого домашнего задания у вас будет в профиле создаваться новый репозиторий на gitlab.skillbox.ru
{{< /hint >}}

Внутри репозитория - материалы для выполнения домашнего задания.

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%202.png)

Также в репозитории будет создана ветка **homework** и **Merge Request**, имя ветки указано в блоке `Сдача домашнего задания`

![dd%20eed3486088c5418a87e09751164fb9c7/Untitled%203.png](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%203.png)

Посмотреть список веток и перейти в каждую из них, вы можете используя выпадающее меню. Убедитесь что у вас есть ветка homework.

{{< hint info >}}
ℹ️ Имя ветки может быть различное, в зависимости от домашнего задания.
{{< /hint >}}

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%204.png)

После этого приступайте к выполнению домашнего задания

{{< hint danger >}}
ℹ️ Не удаляйте автоматически созданный Merge Request и ветку, домашнее задание связано с ними. Дальнейшее прохождение домашнего задания будет невозможно без обращения в техническую поддержку ([hello@skillbox.ru](mailto:hello@skillbox.ru))
{{< /hint >}}

## ⌨️ Выполнение домашнего задания

После того как убедились что репозиторий и ветка на месте. Приступайте к выполнению домашнего задания:

### Получаем код из репозитория

- Клонируем репозиторий, используя среду разработки **Intellij Idea.**
- Выберите пункт меню **File → New → Project from Version Control...**

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%205.png)

Откроется диалоговое окно, в поля которого вставьте ссылку на репозиторий и выберите папку, в нее будет склонирован репозиторий.

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%206.png)

{{< hint warning >}}
⚠️ Папка должна быть пустой.
Папка не должна находится внутри папки репозитория `java_basics`
{{< /hint >}}

Скопируйте ссылку для клонирования репозитория, нажав на кнопку Clone на странице вашего репозитория:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%207.png)

В итоге после вставки и выбора директории:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%208.png)

Нажимайте **Clone**, после клонирования репозитория, IDEA откроет проект.

Если у вас откроется диалоговое окно:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%209.png)

Выбирайте **Trust Project**. Это подтверждение о доверии к проекту, и вы готовые его запускать.

### Подготовка к выполнению работы

- перейдите в ветку указанное в условие, в примере это `homework`

Для этого выберите в меню **Git&nbsp;→&nbsp;Branches...**</

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2010.png)

Вам откроется список веток проекта:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2011.png)

Для переключения на ветку **homework**, выберите из раздела Remote Branches (ветки в удаленном репозитории) ветку origin/homework. Нажмите на этот пункт и далее в меню выберите пункт **Сheckout** (переключится на выбранную ветку).

После переключения ветки, в нижнем правом углу у вас должно быть указана ветка в которой вы находитесь:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2012.png)

### Выполнение задания

Теперь приступайте к выполнению домашнего задания и написанию кода.

Предлагаю внести небольшое изменение в код, выполнить коммит, отправить в удаленный репозиторий и посмотреть как работают автотесты и где смотреть результаты.

1. Откройте для редактирования файл
2. Поменяйте одно из значений. Это не является решением, мы точно ожидаем что тесты не пройдем.

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2013.png)

Запустим тесты локально, то есть не загружая на проверку.

1. Откройте в дереве проекта папку `src/test/java` . Вызовите контекстное меню у папки java (обычно это можно сделать нажав правой клавишей мыше по названию папки).
2. В открывшемся меню выберите пункт `Run 'All Tests'`

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2014.png)

В итоге запустятся тесты и вы можете проанализировать результат работы вашего кода.

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2015.png)

1. В списке будут находится все запущенные тесты. Зеленая галочка - тест успешно пройден. Желтая иконка - тест запустился, но результат не соответствуют ожидаемому значению. Красная иконка - при выполнении кода произошла ошибка в работе программы. Ваша задача написать код таким образом, чтобы все иконки одновременно при запуске тестов стали зелеными.

2. **Expected** - ожидаемое значение, верный результат.
3. **Actual** - значение, которое вернул ваш код.
4. Если ожидаемое и актуальное значение объемны, то удобно их посмотреть в отдельном окне. Для этого нажмите на **<Click the difference>.** Для примера, показано окно difference для теста **Вывод количества грузовиков...**

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2016.png)

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2017.png)

Рекомендуемый подход - проверить код локально, то есть на компьютере с помощью тестов. Если возникают вопросы - посоветоваться с коллегами и кураторами в чате курса. После отправлять работу в репозиторий.

## ⏩ Отправка работы в удаленный репозиторий

Убедитесь, что вы находитесь в ветке **homework**. В нашем примере, мы заменили только одно значение и ожидаем что тесты не пройдут.

### Выполните коммит

Зафиксируем изменения кода в виде коммита. Только коммиты можно отправлять в удаленный репозиторий.

Для этого, нажмите в панели инструментов **на иконку** или выберите пункт меню **Git → Commit...**

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2018.png)

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2019.png)

У вас откроет окно или панель для выполнения коммита:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2020.png)

1. Здесь выбирайте файлы для коммита. Среда разработки обычно выбирает все изменённые файлы. Мы поменяли только одно значение, в одном файле. Поэтому у нас в коммит попадет только один файл.
2. Каждый коммит имеет комментарий. Это краткое описание изменений в файлах коммита.
3. После выбора файлов и написании комментария, создайте коммит нажав на **Commit**

После создания коммита, проверьте успешное выполнение:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2021.png)

1. В нижнем меню, выберите **Git** (если этого пункта нет, то выполните в верхнем меню **Git → Show Git Log**)
2. В списке коммитов на самом верху должен быть комментарий вашего коммита. И у него должен быть ярлык **homework**. Это значит, что коммит выполнен в ветке **homework**. А значит все сделано верно
3. Также можете посмотреть, какие измененные файлы попали в выбранный коммит.

### Отправьте коммит в удаленный репозиторий

Для отправки коммита (операция Push), нажмите на иконку или выберите пункт меню **Git → Push...**

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2022.png)

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2023.png)

Откроется диалоговое окно:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2024.png)

1. Указаны из какой ветки и в какую ветку в удаленном репозитории попадет коммит. Обычно, да и в нашем случае ветки в удаленном репозитории и в локальном называются одинаково. Обе homework. Далее идет список коммитов для отправки. У нас только один коммит.
2. Нажимайте кнопку Push. У вас могут запросить ввести логин и пароль от аккаунта на [gitlab.skillbox.ru](http://gitlab.skillbox.ru) и после коммит будет загружен.

В логе, в подтверждении успеха у вашего коммита появится ярлык **origin & homework**

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2025.png)

а это значит, что ваш коммит находится в ветке **homework** и в удаленном репозитории **origin. Origin,** это обычно метка основного удаленного репозитория проекта. Если этой метки нет, то значит коммиты еще не отправлены и находятся только на вашем компьютере.

## 📶 Как посмотреть результаты выполнения автотестов

Как только вы отправили коммит в ветку homework удаленного репозитория. Переходите на страницу вашего репозитория на gitlab.skillbox.ru. Это можно сделать из LMS, нажав кнопку **Перейти в Gitlab.**

![dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2026.png](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2026.png)

На скриншоте показана ситуация, когда вы только что отправили коммит и запустилась проверка вашего кода.

Когда тесты завершаться, если они не пройдены - увидите следующее сообщение.

![dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2027.png](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2027.png)

В репозитории, для просмотра результатов тестов, перейдите в раздел Pipelines

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2028.png)

Вам откроется список запущенных задания для проверки кода.

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2029.png)

В поле статус указан результат прохождения тестов.

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2030.png)

- **Failed** - тесты не прошли, необходимо посмотреть результат, внести изменения в код, выполнить коммит и снова отправить.

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2031.png)

- **Passed** - все тесты выполнились успешно, домашнее задание выполнено. Вам оно зачтется и откроется следующее.

Для просмотра результата выполнения тестов с failed статусом, нажмите на статус.

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2032.png)

Каждый запуск проверок поделен на несколько этапом:

1. **Test** - запуск тестов, это такие же тесты, что вы запускаете локально. Может быть 1 и более пунктов. Каждый такой блок называется Job.
2. **Codestyle** - проверка качества кода. В нашем случае все ок, и стоит зеленая галочка.
3. **Report** - это технический Job, он формирует отчет, если хотя бы один пункт не был пройден
4. Для просмотра результатов тестов, используйте вкладку **Tests**

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2033.png)

Здесь вы можете посмотреть каждый тест из каждой Job из раздела Tests.

Зайдите в **geometryCalculator**:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2034.png)

Тут вы можете посмотреть какждый тетс отдельно, его название, статус и ожидаемое значение. Для этого нажмите на кнопку **View details.**

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2035.png)

## 📃 Как посмотреть результат проверки стиля кода

Если после отправки коммита, вы внутри Pipeline видите, что проверка **Codestyle** не прошла:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2036.png)

скачайте отчет и посмотрите список требуемых исправлений. Для этого перейдите в Report

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2037.png)

и справа на панели нажмите Download, в разделе Artifacts.

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2038.png)

Вы получите архив. Распакуйте его и откройте файл `target/site/index.html`, этот файл откроется в браузере. И выглядит таким образом:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2039.png)

В этот отчете вся информация о проекте. Нас интересует вкладка **Отчеты проекта.** Переходи в них.

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2040.png)

- **Surefire Report** - по ссылке содержится результат выполнения тестов. Это дублируют ту вкладку, что есть в gitlab.
- **Checkstyle** - содержит результаты выполнения проверки стиля кода.

Переходите по ссылке **Checkstyle**. На страницк будет отчет, и внизу детальный список замечаний:

![Untitled](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2041.png)

В котором на каждой строке указан тип ошибки, имя правила, описание что требуется исправить и строка на которой найдена ошибка.

Вам необходимо устранить все замечания из этого списка. После этого выполнить коммит, выполнить отправку коммита в удаленный репозиторий и дождаться результата выполнения проверки тестами и стиля кода.

Если найдены ошибки, то повторите действия, начиная с пункта **Как посмотреть результаты выполнения автотестов.**

## 🆗 Результат при успешном прохождении тестов

Если все тесты успешно пройдены, увидите сообщение об успехе.

Поздравляю! Вы выполнили поставленную задачу!

После того как вам зачтут задание, завершите работу в репозитории и перенесите изменения из ветки **homework** в **master**. Это опциональный этап, при этом обычно при разработке в команде, после завершения работы надо отдельной задачей. Изменения "сливают" в одну ветку.

## 🛠️ Окончание работы над домашним заданием

После того как все тесты будут пройдены или преподаватель одобрит домашнее задание, зайдите в список Merge Request

![dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2042.png](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2042.png)

и выполните слияние ветки с домашней работой и веткой master:

![dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2043.png](dd%20eed3486088c5418a87e09751164fb9c7/Untitled%2043.png)

Отличная работа!✅

На этом выполнение домашней работы завершено!

Приступайте к следующему заданию! 👍

## ❓ Частые вопросы и ответы

### Ошибка при отправке коммита: Push rejected

Если при отправке коммита, вы видите уведомление **Push rejected to origin/master**
![dd%20eed3486088c5418a87e09751164fb9c7/2021-12-02_11-47.png](dd%20eed3486088c5418a87e09751164fb9c7/2021-12-02_11-47.png)

или если работаете через консоль, такой ответ:

```log
! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to
'gitlab.skillbox.ru:myAccount/java_numbersanddates_1.git'
```

это значит, что вы пытаетесь отправить коммит напрямую в ветку `master`. Вам надо переключится на ветку `homework` выполнить практическое задание в ней
и уже отправить коммит в `homework`.

Одиан из вариантов решения вопроса по переносу данных коммита в другую веткущд:

{{< hint warning>}}
Сделайте копию папки с репозиторием, вы всегда сможете восстановить файлы, если что-то пойдет не так.
{{< /hint >}}

1. Отмените ваш коммит в `master`. Это действие не удалит ваши файлы. Для этого откройте вкладку **Git → Log**. Выберите коммит `init` и вызовите в меню **Reset Current Branch to Here...**
![dd%20eed3486088c5418a87e09751164fb9c7/2021-12-02_12-11.png](dd%20eed3486088c5418a87e09751164fb9c7/2021-12-02_12-11.png)

2. Выберите **Mixed**. При таком режиме, отмениться коммит, изменения которые были в коммите останутся в вашей рабочей директории, эти изменения не будут использоваться в Git. Поэтому мы сможем эти изменения перенести в новую ветку и там уже выполнить коммит.
![dd%20eed3486088c5418a87e09751164fb9c7/2021-12-02_12-00_1.png](dd%20eed3486088c5418a87e09751164fb9c7/2021-12-02_12-00_1.png)

3. Переключитесь на ветку `homework`. Выполните коммит и уже отправьте коммит в удаленный репозиторий.