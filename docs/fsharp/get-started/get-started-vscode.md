---
title: Начало работы с F# в Visual Studio Code
description: Сведения об использовании F# с Visual Studio Code и Ionide suite подключаемого модуля.
ms.date: 12/23/2018
ms.openlocfilehash: 79863d57abbc71d59ce01fe30abf1db0a569f1e1
ms.sourcegitcommit: 5d9f4b805787f890ca6e0dc7ea30a43018bc9cbb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57788496"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="d0de7-103">Начало работы с F# в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d0de7-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="d0de7-104">Можно написать F# в [Visual Studio Code](https://code.visualstudio.com) с [подключаемый модуль Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) для получения кросс платформенных, облегченный интегрированная среда разработки (IDE) удобной с IntelliSense и базовый код операции рефакторинга.</span><span class="sxs-lookup"><span data-stu-id="d0de7-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="d0de7-105">Посетите [Ionide.io](http://ionide.io) Дополнительные сведения о подключаемом модуле.</span><span class="sxs-lookup"><span data-stu-id="d0de7-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="d0de7-106">Чтобы начать, убедитесь, что у вас есть [ F# и правильно установлен подключаемый модуль Ionide](install-fsharp.md#install-f-with-visual-studio-code).</span><span class="sxs-lookup"><span data-stu-id="d0de7-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

> [!NOTE]
> <span data-ttu-id="d0de7-107">Ionide создаст .NET Framework F# проекты, не .NET core, имеющих проблемы совместимости между различными платформами.</span><span class="sxs-lookup"><span data-stu-id="d0de7-107">Ionide will generate .NET Framework F# projects, not dotnet core, which can have cross-platform compatibility issues.</span></span> <span data-ttu-id="d0de7-108">Если вы используете на **Linux** или **OSX**, более простой способ приступить к работе является использование (средства командной строки) [https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line].</span><span class="sxs-lookup"><span data-stu-id="d0de7-108">If you are running on **Linux** or **OSX**, a simpler way to get started is to use the (command line tools)[https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line].</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="d0de7-109">Создание первого проекта с помощью Ionide</span><span class="sxs-lookup"><span data-stu-id="d0de7-109">Creating your first project with Ionide</span></span>

<span data-ttu-id="d0de7-110">Чтобы создать новую F# проекта, откройте Visual Studio Code в новую папку (можно назвать ее любым).</span><span class="sxs-lookup"><span data-stu-id="d0de7-110">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="d0de7-111">Затем откройте палитру команд (**представление > палитру команд**) и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d0de7-111">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="d0de7-112">Это реализуется с помощью [FORGE](https://github.com/fsharp-editing/Forge) проекта.</span><span class="sxs-lookup"><span data-stu-id="d0de7-112">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="d0de7-113">Если вы не видите параметры шаблона, обновите шаблоны, выполнив следующую команду в палитре команд: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="d0de7-113">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="d0de7-114">Выберите "F#: Новый проект», нажав **ввод**.</span><span class="sxs-lookup"><span data-stu-id="d0de7-114">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="d0de7-115">Это осуществляется переход к следующему шагу, можно выбрать шаблон проекта.</span><span class="sxs-lookup"><span data-stu-id="d0de7-115">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="d0de7-116">Выбрать `classlib` шаблона и нажмите клавишу **ввод**.</span><span class="sxs-lookup"><span data-stu-id="d0de7-116">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="d0de7-117">Затем выберите каталог для создания проекта.</span><span class="sxs-lookup"><span data-stu-id="d0de7-117">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="d0de7-118">Если оставить его пустым, используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="d0de7-118">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="d0de7-119">Наконец имя проекта на последнем шаге.</span><span class="sxs-lookup"><span data-stu-id="d0de7-119">Finally, name your project in the final step.</span></span> <span data-ttu-id="d0de7-120">F#использует [регистре Pascal](http://c2.com/cgi/wiki?PascalCase) для имен проектов.</span><span class="sxs-lookup"><span data-stu-id="d0de7-120">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="d0de7-121">В этой статье используется `ClassLibraryDemo` как имя.</span><span class="sxs-lookup"><span data-stu-id="d0de7-121">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="d0de7-122">Как только вы ввели имя, которое будет для вашего проекта, попадания **ввод**.</span><span class="sxs-lookup"><span data-stu-id="d0de7-122">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="d0de7-123">Если вы выполнили ранее, вы должны получить Visual Studio код рабочую область в левой части окна отображаются со следующими:</span><span class="sxs-lookup"><span data-stu-id="d0de7-123">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="d0de7-124">F# Проектом, под `ClassLibraryDemo` папки.</span><span class="sxs-lookup"><span data-stu-id="d0de7-124">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="d0de7-125">Правильной структуры каталогов для добавления пакетов с помощью [ `Paket` ](https://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="d0de7-125">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="d0de7-126">Кросс платформенные сборки скрипт с [ `FAKE` ](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="d0de7-126">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="d0de7-127">`paket.exe` Исполняемый файл, который можно получить пакеты и разрешать зависимости для вас.</span><span class="sxs-lookup"><span data-stu-id="d0de7-127">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="d0de7-128">Объект `.gitignore` файла, если вы хотите добавить этот проект в системе управления версиями на основе Git.</span><span class="sxs-lookup"><span data-stu-id="d0de7-128">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="d0de7-129">Написав некоторый код</span><span class="sxs-lookup"><span data-stu-id="d0de7-129">Writing some code</span></span>

<span data-ttu-id="d0de7-130">Откройте *ClassLibraryDemo* папки.</span><span class="sxs-lookup"><span data-stu-id="d0de7-130">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="d0de7-131">Вы должны увидеть следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="d0de7-131">You should see the following files:</span></span>

1. <span data-ttu-id="d0de7-132">`ClassLibraryDemo.fs`, F# файл реализации с помощью класса, определенного.</span><span class="sxs-lookup"><span data-stu-id="d0de7-132">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="d0de7-133">`ClassLibraryDemo.fsproj`, F# файл проекта, используемый для построения этого проекта.</span><span class="sxs-lookup"><span data-stu-id="d0de7-133">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="d0de7-134">`Script.fsx`, F# файл скрипта, который загружает исходный файл.</span><span class="sxs-lookup"><span data-stu-id="d0de7-134">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="d0de7-135">`paket.references`, файл Paket, который задает зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="d0de7-135">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="d0de7-136">Откройте `Script.fsx`и добавьте следующий код в конце его:</span><span class="sxs-lookup"><span data-stu-id="d0de7-136">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="d0de7-137">Эта функция преобразует слово в форму [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="d0de7-137">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="d0de7-138">Следующим шагом является ознакомлению с ним с помощью F# интерактивный (FSI).</span><span class="sxs-lookup"><span data-stu-id="d0de7-138">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="d0de7-139">Выделите всей функции (должна быть 11 строк).</span><span class="sxs-lookup"><span data-stu-id="d0de7-139">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="d0de7-140">Как только он будет выделен, удерживайте **Alt** ключа и нажмите кнопку **ввод**.</span><span class="sxs-lookup"><span data-stu-id="d0de7-140">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="d0de7-141">Вы заметите окно, всплывающее окно под, и она должна отобразиться примерно следующее:</span><span class="sxs-lookup"><span data-stu-id="d0de7-141">You'll notice a window pop up below, and it should show something like this:</span></span>

![Пример F# интерактивное окно вывода с помощью Ionide](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="d0de7-143">Это выполняет три действия:</span><span class="sxs-lookup"><span data-stu-id="d0de7-143">This did three things:</span></span>

1. <span data-ttu-id="d0de7-144">Он запущен процесс FSI.</span><span class="sxs-lookup"><span data-stu-id="d0de7-144">It started the FSI process.</span></span>
2. <span data-ttu-id="d0de7-145">Над процессом FSI он отправлен выделенный вами код.</span><span class="sxs-lookup"><span data-stu-id="d0de7-145">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="d0de7-146">Процесс FSI вычисляется код, который вы отправили по.</span><span class="sxs-lookup"><span data-stu-id="d0de7-146">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="d0de7-147">Так как все отправленные через [функция](../language-reference/functions/index.md), теперь можно вызвать этой функции с FSI!</span><span class="sxs-lookup"><span data-stu-id="d0de7-147">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="d0de7-148">В интерактивном окне введите следующее:</span><span class="sxs-lookup"><span data-stu-id="d0de7-148">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="d0de7-149">Вы должны увидеть следующий результат:</span><span class="sxs-lookup"><span data-stu-id="d0de7-149">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="d0de7-150">Теперь давайте попробуем с первой буквой гласных.</span><span class="sxs-lookup"><span data-stu-id="d0de7-150">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="d0de7-151">Введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="d0de7-151">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="d0de7-152">Вы должны увидеть следующий результат:</span><span class="sxs-lookup"><span data-stu-id="d0de7-152">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="d0de7-153">Функция будет работать правильно.</span><span class="sxs-lookup"><span data-stu-id="d0de7-153">The function appears to be working as expected.</span></span> <span data-ttu-id="d0de7-154">Поздравляем, вы только что написанный первого F# функционировать в Visual Studio Code и оценки его FSI!</span><span class="sxs-lookup"><span data-stu-id="d0de7-154">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="d0de7-155">Как вы могли заметить, строки в FSI завершаются `;;`.</span><span class="sxs-lookup"><span data-stu-id="d0de7-155">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="d0de7-156">Это обусловлено FSI позволяет вводить несколько строк.</span><span class="sxs-lookup"><span data-stu-id="d0de7-156">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="d0de7-157">`;;` В конце позволяет FSI знать, когда код будет завершено.</span><span class="sxs-lookup"><span data-stu-id="d0de7-157">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="d0de7-158">О том, в коде</span><span class="sxs-lookup"><span data-stu-id="d0de7-158">Explaining the code</span></span>

<span data-ttu-id="d0de7-159">Если вы не уверены, что фактически выполняет код, вот поэтапные.</span><span class="sxs-lookup"><span data-stu-id="d0de7-159">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="d0de7-160">Как вы видите, `toPigLatin` — это функция, которая принимает слова в качестве входных данных и преобразует его в Pig Latin данного слова.</span><span class="sxs-lookup"><span data-stu-id="d0de7-160">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="d0de7-161">Правила определены следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d0de7-161">The rules for this are as follows:</span></span>

<span data-ttu-id="d0de7-162">Если первый символ в слово начинается с гласных, добавьте в конец слова «yay».</span><span class="sxs-lookup"><span data-stu-id="d0de7-162">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="d0de7-163">Если он не начинается с гласных, переместить первого знака до конца слова и «ay» добавить к нему.</span><span class="sxs-lookup"><span data-stu-id="d0de7-163">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="d0de7-164">Можно заметить следующие FSI:</span><span class="sxs-lookup"><span data-stu-id="d0de7-164">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="d0de7-165">Это означает, что `toPigLatin` — это функция, которая принимает `string` как входные данные (вызывается `word`) и возвращает другой `string`.</span><span class="sxs-lookup"><span data-stu-id="d0de7-165">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="d0de7-166">Этот процесс называется [сигнатура типа функции](https://fsharpforfunandprofit.com/posts/function-signatures/), важнейший элемент F# , критически важна для понимания F# кода.</span><span class="sxs-lookup"><span data-stu-id="d0de7-166">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="d0de7-167">Можно также заметить при наведении указателя на функцию в Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d0de7-167">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="d0de7-168">В теле функции вы заметите две различные части:</span><span class="sxs-lookup"><span data-stu-id="d0de7-168">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="d0de7-169">Внутренняя функция, вызывается `isVowel`, определяющий, если определенный символ (`c`) является гласных путем проверки, если он соответствует одному из шаблонов, предоставленные через [сопоставление шаблонов](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="d0de7-169">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="d0de7-170">[ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) Выражение, которое проверяет, если первый символ — гласных и конструкций, возвращаемое значение из входных символов на основе Если первый символ был гласных или нет:</span><span class="sxs-lookup"><span data-stu-id="d0de7-170">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="d0de7-171">Поток `toPigLatin` , таким образом:</span><span class="sxs-lookup"><span data-stu-id="d0de7-171">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="d0de7-172">Проверьте, является ли первый символ входного слово гласных.</span><span class="sxs-lookup"><span data-stu-id="d0de7-172">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="d0de7-173">Если это так, подключите «yay» до конца слова.</span><span class="sxs-lookup"><span data-stu-id="d0de7-173">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="d0de7-174">В противном случае переместите первого знака до конца слова и «ay» добавить к нему.</span><span class="sxs-lookup"><span data-stu-id="d0de7-174">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="d0de7-175">Имеется заключительную Обратите внимание, что об этом: нет нет явных инструкций для возврата из функции, в отличие от многих других языков.</span><span class="sxs-lookup"><span data-stu-id="d0de7-175">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="d0de7-176">Это обусловлено F# основано на выражении, и последнего выражения в теле функции является возвращаемым значением.</span><span class="sxs-lookup"><span data-stu-id="d0de7-176">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="d0de7-177">Так как `if..then..else` сам является выражением, тело `then` блока или в тексте `else` блок будет возвращаться в зависимости от входного значения.</span><span class="sxs-lookup"><span data-stu-id="d0de7-177">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="d0de7-178">Перемещение кода скрипта в файле реализации</span><span class="sxs-lookup"><span data-stu-id="d0de7-178">Moving your script code into the implementation file</span></span>

<span data-ttu-id="d0de7-179">Предыдущих разделах этой статьи показано распространенных первым шагом в письменной F# кода: написание функцию начальной и выполнение его в интерактивном режиме с FSI.</span><span class="sxs-lookup"><span data-stu-id="d0de7-179">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="d0de7-180">Этот процесс известен как разработка на основе REPL, где [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) расшифровывается как «Read-Evaluate-Print Loop».</span><span class="sxs-lookup"><span data-stu-id="d0de7-180">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="d0de7-181">Это отличный способ поэкспериментировать с функциональными возможностями, пока не получится, что-то работа.</span><span class="sxs-lookup"><span data-stu-id="d0de7-181">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="d0de7-182">Следующий шаг в разработки на основе REPL — Чтобы переместить рабочий код в F# файл реализации.</span><span class="sxs-lookup"><span data-stu-id="d0de7-182">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="d0de7-183">Он может быть скомпилирован с F# компилятора в сборку, которая может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="d0de7-183">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="d0de7-184">Для начала работы откройте `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="d0de7-184">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="d0de7-185">Вы заметите, что некоторый код уже существует.</span><span class="sxs-lookup"><span data-stu-id="d0de7-185">You'll notice that some code is already in there.</span></span> <span data-ttu-id="d0de7-186">Продолжить и удалить определение класса, но не забудьте оставить [ `namespace` ](../language-reference/namespaces.md) объявление вверху.</span><span class="sxs-lookup"><span data-stu-id="d0de7-186">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="d0de7-187">Создайте новый [ `module` ](../language-reference/modules.md) вызывается `PigLatin` и скопируйте `toPigLatin` функции в нее таким образом:</span><span class="sxs-lookup"><span data-stu-id="d0de7-187">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="d0de7-188">Затем откройте `Script.fsx` файл еще раз и удалить весь `toPigLatin` работать, но не забудьте сохранить следующие две строки в файле:</span><span class="sxs-lookup"><span data-stu-id="d0de7-188">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```
<span data-ttu-id="d0de7-189">Выберите обе строки текста и нажмите клавиши Alt + ВВОД, чтобы выполнить эти строки в FSI.</span><span class="sxs-lookup"><span data-stu-id="d0de7-189">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="d0de7-190">Это будет загружать содержимое библиотеки Pig Latin в процесс FSI и `open` `ClassLibraryDemo` пространства имен таким образом, чтобы у вас есть доступ к функциям.</span><span class="sxs-lookup"><span data-stu-id="d0de7-190">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="d0de7-191">Затем в окне «FSI» вызовите функцию с `PigLatin` модуль, который вы задали ранее:</span><span class="sxs-lookup"><span data-stu-id="d0de7-191">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="d0de7-192">Готово!</span><span class="sxs-lookup"><span data-stu-id="d0de7-192">Success!</span></span> <span data-ttu-id="d0de7-193">Вы получите те же результаты, как раньше, но теперь загружаются из F# файл реализации.</span><span class="sxs-lookup"><span data-stu-id="d0de7-193">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="d0de7-194">Основное отличие здесь заключается в, F# исходные файлы компилируются в сборки, которые могут быть выполнены в любом месте, не только в FSI.</span><span class="sxs-lookup"><span data-stu-id="d0de7-194">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="d0de7-195">Сводка</span><span class="sxs-lookup"><span data-stu-id="d0de7-195">Summary</span></span>

<span data-ttu-id="d0de7-196">В этой статье вы узнали:</span><span class="sxs-lookup"><span data-stu-id="d0de7-196">In this article, you've learned:</span></span>

1. <span data-ttu-id="d0de7-197">Как настроить Visual Studio Code с помощью Ionide.</span><span class="sxs-lookup"><span data-stu-id="d0de7-197">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="d0de7-198">Как создать свою первую F# проекта с помощью Ionide.</span><span class="sxs-lookup"><span data-stu-id="d0de7-198">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="d0de7-199">Как использовать F# сценарии для написания первого F# работать в Ionide и затем выполнить его в FSI.</span><span class="sxs-lookup"><span data-stu-id="d0de7-199">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="d0de7-200">Как перенести код сценария, чтобы F# источника, а затем вызвать этот код из FSI.</span><span class="sxs-lookup"><span data-stu-id="d0de7-200">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="d0de7-201">Теперь все необходимые средства для записи многое другое F# кода с помощью Visual Studio Code и Ionide.</span><span class="sxs-lookup"><span data-stu-id="d0de7-201">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d0de7-202">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d0de7-202">Troubleshooting</span></span>

<span data-ttu-id="d0de7-203">Ниже приведены несколько способов устранения некоторых проблем, которые вы можете столкнуться.</span><span class="sxs-lookup"><span data-stu-id="d0de7-203">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="d0de7-204">Чтобы получить возможности редактирования кода среды Ionide, ваш F# файлы должны быть сохранены на диске, а также внутри папки, который открыт в рабочей области Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d0de7-204">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="d0de7-205">Если были внесены изменения в систему или установить необходимые компоненты Ionide с помощью Visual Studio Code откройте, перезапустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d0de7-205">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="d0de7-206">Убедитесь, что можно использовать F# компилятора и F# интерактивные сообщения от командной строки без полного пути.</span><span class="sxs-lookup"><span data-stu-id="d0de7-206">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="d0de7-207">Это можно сделать, введя `fsc` в командную строку для F# компилятора, и `fsi` или `fsharpi` для визуального F# средства в Windows и Mono в Mac/Linux, соответственно.</span><span class="sxs-lookup"><span data-stu-id="d0de7-207">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="d0de7-208">Если у вас есть недопустимые символы в каталогах проекта, Ionide может не работать.</span><span class="sxs-lookup"><span data-stu-id="d0de7-208">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="d0de7-209">Переименование каталогов проекта, если это так.</span><span class="sxs-lookup"><span data-stu-id="d0de7-209">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="d0de7-210">Если ни одна из команд Ionide работаете, проверьте ваши [сочетания клавиш Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) для просмотра, если вы переопределение случайно.</span><span class="sxs-lookup"><span data-stu-id="d0de7-210">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="d0de7-211">Если Ionide разбивается на вашем компьютере, и ни один из указанных выше исправил вашу проблему, попробуйте удалить `ionide-fsharp` каталог на компьютере и переустановить suite подключаемого модуля.</span><span class="sxs-lookup"><span data-stu-id="d0de7-211">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="d0de7-212">Ionide — это проект с открытым кодом создаваемый и используемый средством членами F# сообщества.</span><span class="sxs-lookup"><span data-stu-id="d0de7-212">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="d0de7-213">Пожалуйста, сообщить о проблемах и вы можете внести свой вклад в [Ionide VSCode: Репозиторий FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="d0de7-213">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="d0de7-214">Если у вас проблема к отчету, выполните [инструкции по получению журналы для использования при описании проблемы](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="d0de7-214">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="d0de7-215">Также можно задать для получения дополнительных сведений от разработчиков Ionide и F# сообщества в [канал Ionide Gitter](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="d0de7-215">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d0de7-216">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="d0de7-216">Next steps</span></span>

<span data-ttu-id="d0de7-217">Дополнительные сведения о F# функций языка, извлечения и возврата [примером F# ](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="d0de7-217">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
