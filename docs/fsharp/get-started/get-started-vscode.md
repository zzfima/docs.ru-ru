---
title: 'Начало работы с F # в коде Visual Studio'
description: 'Сведения об использовании языка F # с кодом Visual Studio и suite Ionide подключаемого модуля.'
ms.date: 02/28/2018
ms.openlocfilehash: 71cc0abfd8420794485d38e91efd9819379e3f55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Начало работы с F # в коде Visual Studio

Вы можете написать F # в [кода Visual Studio](https://code.visualstudio.com) с [Ionide подключаемый модуль](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), чтобы получить прекрасные возможности кросс платформенных, простое интегрированной среды разработки (среде разработки Integrade) с технологией IntelliSense и базовый код Рефакторинг.  Посетите [Ionide.io](http://ionide.io) для получения дополнительных сведений о наборе подключаемого модуля.

## <a name="prerequisites"></a>Предварительные требования

Необходимо иметь [git установлен](https://git-scm.com/download) и доступна на путь, чтобы сделать использование шаблонов проектов в Ionide.  Убедитесь, что он правильно установлен, введя `git --version` командной строки и нажав клавишу **ввод**.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

Использует Ionide [моно](http://www.mono-project.com).  Самый простой способ установить Mono на macOS — через Homebrew.  Просто введите следующую команду в окне терминала:

```
brew install mono
```

Необходимо также установить [пакета SDK для .NET Core](https://www.microsoft.com/net/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

В Linux, также использует Ionide [моно](https://www.mono-project.com). Если вы на Debian и Ubuntu, можно использовать следующее:

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

Необходимо также установить [пакета SDK для .NET Core](https://www.microsoft.com/net/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Если вы в Windows, необходимо [установить Visual Studio с поддержкой F #](get-started-visual-studio.md#installing-f). При этом устанавливаются все необходимые компоненты для записи, компиляции и выполнения кода F #.

Необходимо также установить [пакета SDK для .NET Core](https://www.microsoft.com/net/download/).

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a>Установка Visual Studio Code и подключаемый модуль Ionide

Можно установить Visual Studio код из [code.visualstudio.com](https://code.visualstudio.com) веб-сайта. После этого можно найти подключаемый модуль Ionide двумя способами:

1. Использовать палитру команд (Ctrl + Shift + P в Windows, ⌘ + Shift + P на macOS Ctrl + Shift + P в Linux) и введите следующую команду:

    ```
    >ext install Ionide
    ```

2. Щелкните значок расширения и выполните поиск «Ionide»:

    ![](media/getting-started-vscode/vscode-ext.png)

Только для поддержки F # в коде Visual Studio требуется подключаемый модуль [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Тем не менее, можно также установить [Ionide ИМИТАЦИИ](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) и получить [ПОДДЕЛАТЬ](https://fsharp.github.io/FAKE/) поддержки и [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) для получения [Paket](https://fsprojects.github.io/Paket/) поддержки. ПОДДЕЛАТЬ и Paket средства сообщества дополнительные F # для создания проектов и управление зависимостями, соответственно.

## <a name="creating-your-first-project-with-ionide"></a>Создание первого проекта с Ionide

Чтобы создать новый проект F #, откройте кода Visual Studio в новую папку (можно назвать его любым).

![](media/getting-started-vscode/vscode-open-dir.png)

Затем откройте в палитру команд (Ctrl + Shift + P в Windows, ⌘ + Shift + P на macOS Ctrl + Shift + P в Linux) и введите следующую команду:

```
>f#: New Project
```

Это работает на основе [FORGE](https://github.com/fsharp-editing/Forge) проекта.  Результат должен быть примерно таким:

![](media/getting-started-vscode/vscode-new-proj.png)

> [!NOTE]
Если вы не видите выше, обновите шаблоны, выполнив следующую команду в палитру команд: `>F#: Refresh Project Templates`.

Выберите «F #: новый проект», нажав **ввод**, которой вы перейдете этот шаг:

![](media/getting-started-vscode/vscode-proj-type.png)

Это будет выбрать шаблон для определенного типа проекта.  Существует довольно много вариантов, например [FsLab](https://fslab.org) шаблон для обработки и анализа данных или [Suave](https://suave.io) шаблона для веб-программирования.  В этой статье используется `classlib` шаблона, поэтому выделения и нажмите кнопку **ввод**.  Затем будет достигнут следующий шаг:

![](media/getting-started-vscode/vscode-new-dir.png)

Это позволяет при необходимости создания проекта в другом каталоге.  Не указывайте его сейчас.  Он будет создан проект в текущем каталоге.  После нажатия клавиши **ввод**, будет достигнут следующий шаг:

![](media/getting-started-vscode/vscode-proj-name.png)

Это позволяет имя проекта.  F # использует [случае Pascal](http://c2.com/cgi/wiki?PascalCase) для имен проектов.  В этой статье используется `ClassLibraryDemo` как имя.  Как только вы ввели имя для проекта, нажмите **ввод**.

Если были выполнены действия предыдущего шага, вы должны получить Visual Studio код рабочей области с левой стороны выглядит примерно следующим образом:

![](media/getting-started-vscode/vscode-new-proj-explorer.png)

Этот шаблон создает некоторые моменты, которые вы найдете полезные:

1. F # сам проект, под `ClassLibraryDemo` папки.
2. Правильной структуры каталогов для добавления пакетов через [ `Paket` ](https://fsprojects.github.io/Paket/).
3. Кросс платформенных создания скрипта с [ `FAKE` ](https://fsharp.github.io/FAKE/).
4. `paket.exe` Исполняемый файл, в которой можно получить пакеты и разрешить зависимости для вас.
5. Объект `.gitignore` файл, если вы хотите добавить этот проект с системой управления версиями, основанных на Git.

## <a name="writing-some-code"></a>Написание кода

Откройте *ClassLibraryDemo* папки.  Вы увидите следующие файлы:

1. `ClassLibraryDemo.fs`, файле реализации F # с помощью класса, определенного.
2. `CassLibraryDemo.fsproj`, F # файл проекта используется для построения данного проекта.
3. `Script.fsx`, в файл скрипта F # который загружает исходный файл.
4. `paket.references`, в файл Paket, который указывает зависимости проекта.

Откройте `Script.fsx`и добавьте следующий код в конце:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Эта функция преобразует слова в форму [Pig латиница](https://en.wikipedia.org/wiki/Pig_Latin).  Следующим шагом является оценка с помощью F # интерактивный (FSI).

Выделите всей функции (должна быть 11 строк).  Как только он выделяется, удерживайте **Alt** ключа и нажмите кнопку **ввод**.  Вы заметите всплывающее ниже окна и будет выглядеть примерно следующим образом:

![](media/getting-started-vscode/vscode-fsi.png)

Это сделали три действия:

1. Он запущен процесс FSI.
2. Выделенный вами код передаваемых FSI процесса.
3. Процесс FSI вычисляется код, отправляемых по.

Из-за отправляемых по [функция](../language-reference/functions/index.md), теперь можно вызвать этой функции с FSI!  В интерактивном окне введите следующую команду:

```fsharp
toPigLatin "banana";;
```

Должен появиться следующий результат:

```fsharp
val it : string = "ananabay"
```

Теперь попробуем с первой буквой гласные. Введите следующий текст:

```fsharp
toPigLatin "apple";;
```

Должен появиться следующий результат:

```fsharp
val it : string = "appleyay"
```

По-видимому, функция работает, как ожидалось.  Итак, просто написал первой функции F # в Visual Studio Code и его для оценки FSI.

>[!NOTE]
Как можно заметить, в строках в FSI завершаются `;;`.  Это происходит потому FSI позволяет вводить несколько строк.  `;;` В конце позволяет FSI знать, когда код будет завершено.

## <a name="explaining-the-code"></a>Объясняется в коде

Если вы не уверены, что фактически выполняет код, вот пошаговые.

Как видите, `toPigLatin` является функция, которая принимает word в качестве входных данных и преобразует его в Латинской Pig слова.  Для этого правила таковы:

Если первый символ, слово, которое начинается с гласные, добавьте в конец слова «yay».  Если он не начинается с гласные, переместите первого знака в конец слова и «один» добавьте к нему.

Возможно, вы заметили в FSI следующие:

```
val toPigLatin : word:string -> string
```

Том, что `toPigLatin` является функция, которая принимает `string` в качестве входного (называется `word`) и возвращает другой `string`.  Это называется [сигнатура типа функции](https://fsharpforfunandprofit.com/posts/function-signatures/), основные части F #, который является ключом к пониманию кода F #.  Можно также заметить при наведении указателя на функцию в Visual Studio Code.

В теле функции вы увидите двух отдельных частей:

1. Внутренние функции, называемой `isVowel`, которое определяет, если данный символ (`c`) является гласные путем проверки, если он соответствует одному из указанных шаблонов через [соответствие шаблону](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) Выражение, которое проверяет, если первый символ является гласные и создает значение, возвращаемое из входных символов на основе Если первый символ был гласные или нет:

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

Поток `toPigLatin` таким образом:

Проверьте, является ли первый символ слова входной гласные.  Если это так, приложите «yay» до конца слова.  В противном случае переместите первого знака в конец слова и «один» добавьте к нему.

Нет заключительную Обратите внимание, об этом: нет нет явных инструкций для возврата из функции, в отличие от многих других языков здесь.  Это происходит потому F # основано на выражении, и последнего выражения в теле функции является возвращаемым значением.  Поскольку `if..then..else` сам по себе является выражением, тело `then` блока или в теле `else` блок будет возвращаться в зависимости от входного значения.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Перемещение кода скрипта в файле реализации

Предыдущие разделы этой статьи показано общих первым шагом в написании кода F #: функцию начальной записи и выполнить его в интерактивном режиме с FSI.  Это называется разработка REPL, где REPL означает «Цикла оценки печати чтения».  Это отличный способ поэкспериментировать с функциональные возможности, пока не получится, что-либо работы.

Следующий этап разработки на основе REPL является перемещение рабочий код в файле реализации F #.  Он затем может компилироваться компилятором F # в сборку, которая может быть выполнена.

Чтобы начать, откройте `ClassLibraryDemo.fs`.  Вы заметите, что определенный код уже существует.  Продолжить и удалить определение класса, но убедитесь в том оставить [ `namespace` ](../language-reference/namespaces.md) объявление в начале.

Создайте новый [ `module` ](../language-reference/modules.md) вызывается `PigLatin` и скопируйте `toPigLatin` функции в нее таким образом:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

Это один из многих способов, которые можно организовать функций в коде F # и общий подход, если требуется вызов кода из C# или проекты Visual Basic.

Затем откройте `Script.fsx` файл еще раз и удалить весь `toPigLatin` работать, но не забудьте сохранить следующие две строки в файле:

```
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

Первая строка необходим для сценариев для загрузки FSI `ClassLibraryDemo.fs`.  Вторая строка — удобный: пропуск он необязателен, но вам будет нужно ввести `open ClassLibraryDemo` в окне с FSI, если вы хотите подключить `ToPigLatin` модуля в область действия.

Затем в окне «FSI» вызовите функцию с `PigLatin` модуля, определенного ранее:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Готово!  Получить те же результаты, но теперь загружаются из файла реализации F #.  Здесь основное отличие заключается в том, что исходными файлами F # компилируются в сборки, которые могут быть выполнены в любом месте, не только в FSI.

## <a name="summary"></a>Сводка

В этой статье вы узнали:

1. Как настроить Visual Studio код с Ionide.
2. Создание первого проекта F # с Ionide.
3. Инструкции по использованию скриптов F # для создания первой функции F # на Ionide, а затем выполнить его в FSI.
4. Как перенести код скрипта F # источника и затем вызвать этот код из FSI.

Вы теперь способны записывать гораздо большего объема кода F #, используя код Visual Studio и Ionide.

## <a name="troubleshooting"></a>Устранение неполадок

Ниже приведены несколько способов, которые можно устранить определенные неполадки, которые вы можете столкнуться.

1. Чтобы получить возможности редактирования кода среды Ionide, F #, файлы должны быть сохранены на диск и внутри папки, который открыт в рабочей области кода Visual Studio.
2. Если были внесены изменения в систему или установить необходимые компоненты Ionide с открытым кодом Visual Studio, перезапустите Visual Studio Code.
3. Проверьте, можно использовать компилятор F # и F # interactive из командной строки без полный путь.  Это можно сделать, введя `fsc` в командной строке компилятора F #, и `fsi` или `fsharpi` для Visual F # средств в Windows и Mono на Mac, Linux, соответственно.
4. Если у вас есть недопустимые символы в каталогах проекта, Ionide может не работать.  Переименование каталогов проекта, если это так.
5. Если ни одна из команд Ionide работают, проверьте вашей [сочетания клавиш в Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) для просмотра, если их переопределение случайно.
6. Если ни один из указанных выше проблема исправлена проблема Ionide разбивается на компьютере, попробуйте удалить `ionide-fsharp` каталог на компьютере и переустановите пакет подключаемого модуля.

Ionide является проекта с открытым кодом создаваемый и используемый средством членами сообщества F #.  Следует сообщить о проблемах и вы можете принять участие в [Ionide VSCode: репозитории FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).

Если имеется проблема в отчет, выполните [инструкции по получению журналов для использования при сообщение о проблеме,](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

Также можно задать для получения дополнительных сведений из Ionide разработчиков и сообщества F # в [Ionide Gitter канала](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Следующие шаги

Дополнительные сведения о F # и функции языка, извлечь [обзор языка F #](../tour.md).

## <a name="see-also"></a>См. также

[Обзор языка F#](../tour.md)

[Справочник по языку F#](../language-reference/index.md)

[Функции](../language-reference/functions/index.md)

[Модули](../language-reference/modules.md)

[Пространства имен](../language-reference/namespaces.md)

[Ionide VSCode: FSharp](https://github.com/ionide/ionide-vscode-fsharp)
