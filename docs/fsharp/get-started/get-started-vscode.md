---
title: Начало работы с F# в Visual Studio Code
description: Узнайте, как использовать F# с Visual Studio Code и набором подключаемых модулей Ionide.
ms.date: 12/23/2018
ms.openlocfilehash: 2fa0518488d37b2130aaba96028ac92dac77eb97
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082989"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="ec32e-103">Начало работы с F# в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ec32e-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="ec32e-104">Вы можете писать F# в [Visual Studio Code](https://code.visualstudio.com) с помощью [подключаемого модуля Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) , чтобы получить отличное от платформы упрощенное интегрированное окружение разработки (IDE) с технологией IntelliSense и базовым рефакторингом кода.</span><span class="sxs-lookup"><span data-stu-id="ec32e-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="ec32e-105">Посетите [Ionide.IO](http://ionide.io) , чтобы узнать больше о подключаемом модуле.</span><span class="sxs-lookup"><span data-stu-id="ec32e-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="ec32e-106">Для начала убедитесь, что у вас есть [ F# и правильно установлен подключаемый модуль Ionide](install-fsharp.md#install-f-with-visual-studio-code).</span><span class="sxs-lookup"><span data-stu-id="ec32e-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

> [!NOTE]
> <span data-ttu-id="ec32e-107">Ionide будет создавать .NET Framework F# проекты, а не как DotNet Core, которые могут иметь проблемы совместимости между платформами.</span><span class="sxs-lookup"><span data-stu-id="ec32e-107">Ionide will generate .NET Framework F# projects, not dotnet core, which can have cross-platform compatibility issues.</span></span> <span data-ttu-id="ec32e-108">Если вы используете **Linux** или **OSX**, проще всего начать работу с помощью [программ командной строки](get-started-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="ec32e-108">If you are running on **Linux** or **OSX**, a simpler way to get started is to use the [command-line tools](get-started-command-line.md).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="ec32e-109">Создание первого проекта с помощью Ionide</span><span class="sxs-lookup"><span data-stu-id="ec32e-109">Creating your first project with Ionide</span></span>

<span data-ttu-id="ec32e-110">Чтобы создать новый F# проект, откройте Visual Studio Code в новой папке (вы можете присвоить ему любое имя).</span><span class="sxs-lookup"><span data-stu-id="ec32e-110">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="ec32e-111">Затем откройте палитру команд (**представление > палитра команд**) и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ec32e-111">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```console
> F# new project
```

<span data-ttu-id="ec32e-112">Это работает на платформе проекта [подделки](https://github.com/fsharp-editing/Forge) .</span><span class="sxs-lookup"><span data-stu-id="ec32e-112">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="ec32e-113">Если параметры шаблона не отображаются, попробуйте обновить шаблоны, выполнив следующую команду в палитре команд: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="ec32e-113">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="ec32e-114">Выберите "F#: Новый проект ", нажав клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="ec32e-114">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="ec32e-115">Откроется следующий шаг, предназначенный для выбора шаблона проекта.</span><span class="sxs-lookup"><span data-stu-id="ec32e-115">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="ec32e-116">Выберите шаблон и нажмите клавишу **ВВОД.** `classlib`</span><span class="sxs-lookup"><span data-stu-id="ec32e-116">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="ec32e-117">Затем выберите каталог для создания проекта в.</span><span class="sxs-lookup"><span data-stu-id="ec32e-117">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="ec32e-118">Если оставить его пустым, то будет использовать текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="ec32e-118">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="ec32e-119">Наконец, назовите проект на последнем шаге.</span><span class="sxs-lookup"><span data-stu-id="ec32e-119">Finally, name your project in the final step.</span></span> <span data-ttu-id="ec32e-120">F#использует [сценарий Pascal](http://c2.com/cgi/wiki?PascalCase) для имен проектов.</span><span class="sxs-lookup"><span data-stu-id="ec32e-120">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="ec32e-121">В этой статье `ClassLibraryDemo` в качестве имени используется.</span><span class="sxs-lookup"><span data-stu-id="ec32e-121">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="ec32e-122">Введя нужное имя для проекта, нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="ec32e-122">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="ec32e-123">Если вы прийдете к предыдущему шагу, вы должны получить в левой части рабочую область Visual Studio Code, которая будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ec32e-123">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="ec32e-124">Сам F# проект под `ClassLibraryDemo` папкой.</span><span class="sxs-lookup"><span data-stu-id="ec32e-124">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="ec32e-125">Правильная структура каталогов для добавления пакетов через [`Paket`](https://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="ec32e-125">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="ec32e-126">Скрипт кросс-платформенной сборки с [`FAKE`](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="ec32e-126">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="ec32e-127">`paket.exe` Исполняемый файл, который может получать пакеты и разрешать зависимости.</span><span class="sxs-lookup"><span data-stu-id="ec32e-127">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="ec32e-128">Файл `.gitignore` , если требуется добавить этот проект в систему управления версиями на основе Git.</span><span class="sxs-lookup"><span data-stu-id="ec32e-128">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="ec32e-129">Написание кода</span><span class="sxs-lookup"><span data-stu-id="ec32e-129">Writing some code</span></span>

<span data-ttu-id="ec32e-130">Откройте папку *класслибраридемо* .</span><span class="sxs-lookup"><span data-stu-id="ec32e-130">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="ec32e-131">Вы должны увидеть следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="ec32e-131">You should see the following files:</span></span>

1. <span data-ttu-id="ec32e-132">`ClassLibraryDemo.fs`— файл F# реализации с определенным классом.</span><span class="sxs-lookup"><span data-stu-id="ec32e-132">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="ec32e-133">`ClassLibraryDemo.fsproj`— файл F# проекта, используемый для построения этого проекта.</span><span class="sxs-lookup"><span data-stu-id="ec32e-133">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="ec32e-134">`Script.fsx`— файл F# скрипта, который загружает исходный файл.</span><span class="sxs-lookup"><span data-stu-id="ec32e-134">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="ec32e-135">`paket.references`— файл пакет, указывающий зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="ec32e-135">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="ec32e-136">Откройте `Script.fsx`и добавьте в его конец следующий код:</span><span class="sxs-lookup"><span data-stu-id="ec32e-136">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="ec32e-137">Эта функция преобразует слово в форму [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="ec32e-137">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="ec32e-138">Следующим шагом является его оценка с помощью F# интерактивной (FSI).</span><span class="sxs-lookup"><span data-stu-id="ec32e-138">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="ec32e-139">Выделите всю функцию (она должна составлять 11 строк).</span><span class="sxs-lookup"><span data-stu-id="ec32e-139">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="ec32e-140">После выделения удерживайте клавишу **ALT** и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="ec32e-140">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="ec32e-141">Обратите внимание на всплывающее окно окна, которое должно выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="ec32e-141">You'll notice a window pop up below, and it should show something like this:</span></span>

![Пример F# интерактивного вывода с помощью Ionide](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="ec32e-143">Это сделало три вещи:</span><span class="sxs-lookup"><span data-stu-id="ec32e-143">This did three things:</span></span>

1. <span data-ttu-id="ec32e-144">Он запустил процесс FSI.</span><span class="sxs-lookup"><span data-stu-id="ec32e-144">It started the FSI process.</span></span>
2. <span data-ttu-id="ec32e-145">Он отправил код, выделенный вам для процесса FSI.</span><span class="sxs-lookup"><span data-stu-id="ec32e-145">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="ec32e-146">Процесс FSI проверил код, который вы отправили.</span><span class="sxs-lookup"><span data-stu-id="ec32e-146">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="ec32e-147">Так как вы передавали [функцию](../language-reference/functions/index.md), теперь вы можете вызвать эту функцию с помощью FSI!</span><span class="sxs-lookup"><span data-stu-id="ec32e-147">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="ec32e-148">В интерактивном окне введите следующее:</span><span class="sxs-lookup"><span data-stu-id="ec32e-148">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="ec32e-149">Вы должны увидеть следующий результат:</span><span class="sxs-lookup"><span data-stu-id="ec32e-149">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="ec32e-150">Теперь давайте попробуем использовать гласную в качестве первой буквы.</span><span class="sxs-lookup"><span data-stu-id="ec32e-150">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="ec32e-151">Введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="ec32e-151">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="ec32e-152">Вы должны увидеть следующий результат:</span><span class="sxs-lookup"><span data-stu-id="ec32e-152">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="ec32e-153">Вероятно, функция работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="ec32e-153">The function appears to be working as expected.</span></span> <span data-ttu-id="ec32e-154">Поздравляем, вы только что написали первую F# функцию в Visual Studio Code и оценили ее с помощью FSI!</span><span class="sxs-lookup"><span data-stu-id="ec32e-154">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="ec32e-155">Как вы могли заметить, строки в FSI завершаются с помощью `;;`.</span><span class="sxs-lookup"><span data-stu-id="ec32e-155">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="ec32e-156">Это обусловлено тем, что FSI позволяет вводить несколько строк.</span><span class="sxs-lookup"><span data-stu-id="ec32e-156">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="ec32e-157">`;;` По окончании в конце кода программа FSI будет узнавать, когда код завершен.</span><span class="sxs-lookup"><span data-stu-id="ec32e-157">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="ec32e-158">Объяснение кода</span><span class="sxs-lookup"><span data-stu-id="ec32e-158">Explaining the code</span></span>

<span data-ttu-id="ec32e-159">Если вы не знаете, что делает код, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ec32e-159">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="ec32e-160">Как видите, `toPigLatin` функция представляет собой функцию, которая принимает слово в качестве входных данных и преобразует его в Pig-Latin представление этого слова.</span><span class="sxs-lookup"><span data-stu-id="ec32e-160">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="ec32e-161">Ниже приведены правила для этого.</span><span class="sxs-lookup"><span data-stu-id="ec32e-161">The rules for this are as follows:</span></span>

<span data-ttu-id="ec32e-162">Если первый символ в слове начинается с гласной, добавьте «ура» в конец слова.</span><span class="sxs-lookup"><span data-stu-id="ec32e-162">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="ec32e-163">Если он не начинается с гласной, переместите первый символ в конец слова и добавьте в него «гг».</span><span class="sxs-lookup"><span data-stu-id="ec32e-163">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="ec32e-164">Вы могли заметить следующее в FSI:</span><span class="sxs-lookup"><span data-stu-id="ec32e-164">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="ec32e-165">Это указывает, `toPigLatin` что функция принимает в качестве входных `string` данных (с именем `word`) и возвращает другой `string`объект.</span><span class="sxs-lookup"><span data-stu-id="ec32e-165">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="ec32e-166">Это называется [сигнатурой типа функции](https://fsharpforfunandprofit.com/posts/function-signatures/)— основной частью F# этого ключа для понимания F# кода.</span><span class="sxs-lookup"><span data-stu-id="ec32e-166">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="ec32e-167">Это также можно заметить при наведении указателя мыши на функцию в Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="ec32e-167">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="ec32e-168">В теле функции можно заметить две различные части:</span><span class="sxs-lookup"><span data-stu-id="ec32e-168">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="ec32e-169">Внутренняя функция, вызываемая `isVowel`, определяет, является ли данный символ (`c`) гласным, проверяя, соответствует ли он одному из указанных шаблонов с помощью [сопоставления шаблонов](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="ec32e-169">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="ec32e-170">[`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) Выражение, которое проверяет, является ли первый символ гласным, и формирует возвращаемое значение из входных символов на основе того, является ли первый символ гласным или нет:</span><span class="sxs-lookup"><span data-stu-id="ec32e-170">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="ec32e-171">Таким образом, `toPigLatin` поток:</span><span class="sxs-lookup"><span data-stu-id="ec32e-171">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="ec32e-172">Проверьте, является ли первый символ входного слова гласным.</span><span class="sxs-lookup"><span data-stu-id="ec32e-172">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="ec32e-173">Если это так, прикрепите "ура" к концу слова.</span><span class="sxs-lookup"><span data-stu-id="ec32e-173">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="ec32e-174">В противном случае переместите первый символ в конец слова и добавьте в него «гг».</span><span class="sxs-lookup"><span data-stu-id="ec32e-174">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="ec32e-175">Есть одно конечное замечание: нет явных инструкций для возврата из функции, в отличие от многих других языков.</span><span class="sxs-lookup"><span data-stu-id="ec32e-175">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="ec32e-176">Это происходит потому F# , что основан на выражениях, а Последнее выражение в теле функции является возвращаемым значением.</span><span class="sxs-lookup"><span data-stu-id="ec32e-176">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="ec32e-177">Поскольку `if..then..else` сам по себе является выражением, в зависимости `then` от входного значения будет возвращаться `else` тело блока или текст блока.</span><span class="sxs-lookup"><span data-stu-id="ec32e-177">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="ec32e-178">Перемещение кода скрипта в файл реализации</span><span class="sxs-lookup"><span data-stu-id="ec32e-178">Moving your script code into the implementation file</span></span>

<span data-ttu-id="ec32e-179">В предыдущих разделах этой статьи был показан общий первый шаг в написании F# кода: написание начальной функции и ее интерактивное исполнение с помощью FSI.</span><span class="sxs-lookup"><span data-stu-id="ec32e-179">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="ec32e-180">Это называется разработкой на основе REPL, где [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) означает "чтение-вычисление-цикл печати".</span><span class="sxs-lookup"><span data-stu-id="ec32e-180">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="ec32e-181">Это отличный способ поэкспериментировать с функциями, пока не будет выполнена какая-то работа.</span><span class="sxs-lookup"><span data-stu-id="ec32e-181">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="ec32e-182">Следующим шагом в разработке на основе REPL является перемещение рабочего кода в файл F# реализации.</span><span class="sxs-lookup"><span data-stu-id="ec32e-182">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="ec32e-183">Затем он может быть скомпилирован F# компилятором в сборку, которую можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="ec32e-183">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="ec32e-184">Чтобы начать, откройте `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="ec32e-184">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="ec32e-185">Вы заметите, что в нем уже есть код.</span><span class="sxs-lookup"><span data-stu-id="ec32e-185">You'll notice that some code is already in there.</span></span> <span data-ttu-id="ec32e-186">Удалите определение класса, но обязательно оставьте [`namespace`](../language-reference/namespaces.md) объявление в верхней части.</span><span class="sxs-lookup"><span data-stu-id="ec32e-186">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="ec32e-187">Затем создайте новый [`module`](../language-reference/modules.md) вызов `PigLatin` и скопируйте `toPigLatin` в него функцию:</span><span class="sxs-lookup"><span data-stu-id="ec32e-187">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="ec32e-188">Затем снова откройте `Script.fsx` файл и удалите функцию целиком `toPigLatin` , но убедитесь в том, что в файле хранятся следующие две строки:</span><span class="sxs-lookup"><span data-stu-id="ec32e-188">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="ec32e-189">Выберите обе строки текста и нажмите клавиши ALT + ВВОД, чтобы выполнить эти строки в FSI.</span><span class="sxs-lookup"><span data-stu-id="ec32e-189">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="ec32e-190">Это позволит загрузить содержимое библиотеки Pig Latin в процесс FSI и `open` `ClassLibraryDemo` пространство имен, чтобы получить доступ к функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="ec32e-190">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="ec32e-191">Затем в окне FSI вызовите функцию с `PigLatin` модулем, который вы определили ранее:</span><span class="sxs-lookup"><span data-stu-id="ec32e-191">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```console
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="ec32e-192">Готово!</span><span class="sxs-lookup"><span data-stu-id="ec32e-192">Success!</span></span> <span data-ttu-id="ec32e-193">Вы получаете те же результаты, что и раньше, но теперь загрузили их из файла F# реализации.</span><span class="sxs-lookup"><span data-stu-id="ec32e-193">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="ec32e-194">Основное отличие заключается в том, F# что исходные файлы компилируются в сборки, которые могут выполняться где угодно, а не только в FSI.</span><span class="sxs-lookup"><span data-stu-id="ec32e-194">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="ec32e-195">Сводка</span><span class="sxs-lookup"><span data-stu-id="ec32e-195">Summary</span></span>

<span data-ttu-id="ec32e-196">В этой статье вы узнали:</span><span class="sxs-lookup"><span data-stu-id="ec32e-196">In this article, you've learned:</span></span>

1. <span data-ttu-id="ec32e-197">Как настроить Visual Studio Code с помощью Ionide.</span><span class="sxs-lookup"><span data-stu-id="ec32e-197">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="ec32e-198">Как создать первый F# проект с помощью Ionide.</span><span class="sxs-lookup"><span data-stu-id="ec32e-198">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="ec32e-199">Как использовать F# скрипты для написания первой F# функции в Ionide, а затем выполнять ее в FSI.</span><span class="sxs-lookup"><span data-stu-id="ec32e-199">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="ec32e-200">Как перенести код скрипта в F# источник и затем вызвать этот код из FSI.</span><span class="sxs-lookup"><span data-stu-id="ec32e-200">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="ec32e-201">Теперь вы можете писать гораздо больше F# кода, используя Visual Studio Code и Ionide.</span><span class="sxs-lookup"><span data-stu-id="ec32e-201">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ec32e-202">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ec32e-202">Troubleshooting</span></span>

<span data-ttu-id="ec32e-203">Вот несколько способов устранения некоторых проблем, с которыми вы можете столкнуться.</span><span class="sxs-lookup"><span data-stu-id="ec32e-203">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="ec32e-204">Чтобы получить возможности редактирования кода Ionide, необходимо сохранить F# файлы на диске и в папке, открытой в Visual Studio Code рабочей области.</span><span class="sxs-lookup"><span data-stu-id="ec32e-204">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="ec32e-205">Если вы внесли изменения в систему или установили необходимые компоненты Ionide с Visual Studio Code открыть, перезапустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="ec32e-205">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="ec32e-206">Убедитесь, что вы можете использовать F# компилятор и F# интерактивное взаимодействие из командной строки без полного пути.</span><span class="sxs-lookup"><span data-stu-id="ec32e-206">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="ec32e-207">Это можно сделать `fsc` , введя в командной строке F# компилятора `fsi` , или `fsharpi` для визуальных F# инструментов в Windows и Mono в Mac/Linux соответственно.</span><span class="sxs-lookup"><span data-stu-id="ec32e-207">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="ec32e-208">Если в каталогах проекта есть недопустимые символы, Ionide может не работать.</span><span class="sxs-lookup"><span data-stu-id="ec32e-208">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="ec32e-209">Переименуйте каталоги проектов, если это так.</span><span class="sxs-lookup"><span data-stu-id="ec32e-209">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="ec32e-210">Если ни одна из команд Ionide не работает, проверьте [Visual Studio Code сочетания клавиш](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) , чтобы узнать, не переопределяете их случайно.</span><span class="sxs-lookup"><span data-stu-id="ec32e-210">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="ec32e-211">Если Ionide не работает на компьютере и ни один из указанных выше проблем не устранил проблему, попробуйте удалить `ionide-fsharp` каталог на компьютере и переустановить набор подключаемых модулей.</span><span class="sxs-lookup"><span data-stu-id="ec32e-211">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="ec32e-212">Ionide — это проект с открытым исходным кодом, созданный и обслуживаемый членами F# сообщества.</span><span class="sxs-lookup"><span data-stu-id="ec32e-212">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="ec32e-213">Сообщите о проблемах и вы можете участвовать [в Ionide-VSCode: Репозиторий](https://github.com/ionide/ionide-vscode-fsharp)GitHub для FSharp.</span><span class="sxs-lookup"><span data-stu-id="ec32e-213">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="ec32e-214">Если у вас возникли проблемы с отчетом, следуйте [инструкциям по получению журналов для использования при сообщении о возникшей ошибке](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="ec32e-214">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="ec32e-215">Кроме того, вы можете запросить дополнительную помощь от разработчиков Ionide и F# сообщества в [канале Ionide gitter](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="ec32e-215">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ec32e-216">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="ec32e-216">Next steps</span></span>

<span data-ttu-id="ec32e-217">Дополнительные сведения о F# и функциях языка см. в статье [Обзор F# ](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="ec32e-217">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
