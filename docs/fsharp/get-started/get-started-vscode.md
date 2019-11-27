---
title: Начало работы с F# в Visual Studio Code
description: Узнайте, как использовать F# с Visual Studio Code и набором подключаемых модулей Ionide.
ms.date: 12/23/2018
ms.openlocfilehash: 2802438144eb2352c3abeeccfc126b16c6a87d8f
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204914"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="4635e-103">Начало работы с F# в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4635e-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="4635e-104">Вы можете писать F# в [Visual Studio Code](https://code.visualstudio.com) с [подключаемым модулем Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) , чтобы получить отличное от платформы упрощенное интегрированное окружение разработки (IDE) с технологией IntelliSense и оптимизацией кода.</span><span class="sxs-lookup"><span data-stu-id="4635e-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and code refactorings.</span></span> <span data-ttu-id="4635e-105">Посетите [Ionide.IO](http://ionide.io) , чтобы узнать больше о подключаемом модуле.</span><span class="sxs-lookup"><span data-stu-id="4635e-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="4635e-106">Для начала убедитесь, что у вас есть [ F# и правильно установлен подключаемый модуль Ionide](install-fsharp.md#install-f-with-visual-studio-code).</span><span class="sxs-lookup"><span data-stu-id="4635e-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

## <a name="create-your-first-project-with-ionide"></a><span data-ttu-id="4635e-107">Создание первого проекта с помощью Ionide</span><span class="sxs-lookup"><span data-stu-id="4635e-107">Create your first project with Ionide</span></span>

<span data-ttu-id="4635e-108">Чтобы создать новый F# проект, откройте командную строку и создайте новый проект с .NET Core CLI:</span><span class="sxs-lookup"><span data-stu-id="4635e-108">To create a new F# project, open a command line and create a new project with the .NET Core CLI:</span></span>

```dotnetcli
dotnet new console -lang F# -o FirstIonideProject
```

<span data-ttu-id="4635e-109">После завершения измените каталог на проект и откройте Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="4635e-109">Once it completes, change directory to the project and open Visual Studio Code:</span></span>

```console
cd FirstIonideProject
code .
```

<span data-ttu-id="4635e-110">После загрузки проекта на Visual Studio Code Вы увидите панель F# Обозреватель решений в левой части окна Открыть.</span><span class="sxs-lookup"><span data-stu-id="4635e-110">After the project loads on Visual Studio Code, you should see the F# Solution Explorer pane on the left-hand side of your window open.</span></span> <span data-ttu-id="4635e-111">Это означает, что Ionide успешно загрузил только что созданный проект.</span><span class="sxs-lookup"><span data-stu-id="4635e-111">This means Ionide has successfully loaded the project you just created.</span></span> <span data-ttu-id="4635e-112">Вы можете написать код в редакторе до этой точки во времени, но после того, как это произойдет, все готово к загрузке.</span><span class="sxs-lookup"><span data-stu-id="4635e-112">You can write code in the editor before this point in time, but once this happens, everything has finished loading.</span></span>

## <a name="configure-f-interactive"></a><span data-ttu-id="4635e-113">Настройка F# интерактивного</span><span class="sxs-lookup"><span data-stu-id="4635e-113">Configure F# interactive</span></span>

<span data-ttu-id="4635e-114">Во-первых, убедитесь, что скрипты .NET Core — это среда сценариев по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="4635e-114">First, ensure that .NET Core scripting is your default scripting environment:</span></span>

1. <span data-ttu-id="4635e-115">Откройте \*\*параметры Visual Studio Code (настройки > \*\* **кода** > **Параметры**).</span><span class="sxs-lookup"><span data-stu-id="4635e-115">Open the Visual Studio Code settings (**Code** > **Preferences** > **Settings**).</span></span>
1. <span data-ttu-id="4635e-116">Найдите термин  **F# сценарий**.</span><span class="sxs-lookup"><span data-stu-id="4635e-116">Search for the term **F# Script**.</span></span>
1. <span data-ttu-id="4635e-117">Установите флажок **FSharp: использовать скрипты пакета SDK**.</span><span class="sxs-lookup"><span data-stu-id="4635e-117">Click the checkbox that says **FSharp: use SDK scripts**.</span></span>

<span data-ttu-id="4635e-118">В настоящее время это необходимо из-за некоторых устаревших поведений в сценариях на основе .NET Framework, которые не работают с сценариями .NET Core, и Ionide в настоящее время выполняет эту обратную совместимость.</span><span class="sxs-lookup"><span data-stu-id="4635e-118">This is currently necessary due to some legacy behaviors in .NET Framework-based scripting that don't work with .NET Core scripting, and Ionide is currently striving for that backwards compatibility.</span></span> <span data-ttu-id="4635e-119">В будущем скрипты .NET Core станут значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4635e-119">In the future, .NET Core scripting will become the default.</span></span>

### <a name="write-your-first-script"></a><span data-ttu-id="4635e-120">Напишите первый скрипт</span><span class="sxs-lookup"><span data-stu-id="4635e-120">Write your first script</span></span>

<span data-ttu-id="4635e-121">После настройки Visual Studio Code для использования сценариев .NET Core перейдите в представление обозревателя в Visual Studio Code и создайте новый файл.</span><span class="sxs-lookup"><span data-stu-id="4635e-121">Once you've configured Visual Studio Code to use .NET Core scripting, navigate to the Explorer view in Visual Studio Code and create a new file.</span></span> <span data-ttu-id="4635e-122">Назовите его *мифирстскрипт. fsx*.</span><span class="sxs-lookup"><span data-stu-id="4635e-122">Name it *MyFirstScript.fsx*.</span></span>

<span data-ttu-id="4635e-123">Теперь добавьте в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="4635e-123">Now add the following code to it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="4635e-124">Эта функция преобразует слово в форму [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="4635e-124">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="4635e-125">Следующим шагом является его оценка с помощью F# интерактивной (FSI).</span><span class="sxs-lookup"><span data-stu-id="4635e-125">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="4635e-126">Выделите всю функцию (она должна составлять 11 строк).</span><span class="sxs-lookup"><span data-stu-id="4635e-126">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="4635e-127">После выделения удерживайте клавишу **ALT** и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="4635e-127">Once it's highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="4635e-128">В нижней части экрана появится всплывающее окно терминала, которое должно выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="4635e-128">You'll notice a terminal window pop up on the bottom of the screen, and it should look similar to this:</span></span>

![Пример F# интерактивного вывода с помощью Ionide](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="4635e-130">Это сделало три вещи:</span><span class="sxs-lookup"><span data-stu-id="4635e-130">This did three things:</span></span>

1. <span data-ttu-id="4635e-131">Он запустил процесс FSI.</span><span class="sxs-lookup"><span data-stu-id="4635e-131">It started the FSI process.</span></span>
2. <span data-ttu-id="4635e-132">Он отправил код, выделенный вам для процесса FSI.</span><span class="sxs-lookup"><span data-stu-id="4635e-132">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="4635e-133">Процесс FSI проверил код, который вы отправили.</span><span class="sxs-lookup"><span data-stu-id="4635e-133">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="4635e-134">Так как вы передавали [функцию](../language-reference/functions/index.md), теперь вы можете вызвать эту функцию с помощью FSI!</span><span class="sxs-lookup"><span data-stu-id="4635e-134">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="4635e-135">В интерактивном окне введите следующее:</span><span class="sxs-lookup"><span data-stu-id="4635e-135">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="4635e-136">Вы должны увидеть следующий результат:</span><span class="sxs-lookup"><span data-stu-id="4635e-136">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="4635e-137">Теперь давайте попробуем использовать гласную в качестве первой буквы.</span><span class="sxs-lookup"><span data-stu-id="4635e-137">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="4635e-138">Введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="4635e-138">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="4635e-139">Вы должны увидеть следующий результат:</span><span class="sxs-lookup"><span data-stu-id="4635e-139">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="4635e-140">Вероятно, функция работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="4635e-140">The function appears to be working as expected.</span></span> <span data-ttu-id="4635e-141">Поздравляем, вы только что написали первую F# функцию в Visual Studio Code и оценили ее с помощью FSI!</span><span class="sxs-lookup"><span data-stu-id="4635e-141">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="4635e-142">Как вы могли заметить, строки в FSI прерываются с `;;`.</span><span class="sxs-lookup"><span data-stu-id="4635e-142">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="4635e-143">Это обусловлено тем, что FSI позволяет вводить несколько строк.</span><span class="sxs-lookup"><span data-stu-id="4635e-143">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="4635e-144">`;;` в конце позволяет сообщить ФСС о завершении кода.</span><span class="sxs-lookup"><span data-stu-id="4635e-144">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="4635e-145">Объяснение кода</span><span class="sxs-lookup"><span data-stu-id="4635e-145">Explaining the code</span></span>

<span data-ttu-id="4635e-146">Если вы не знаете, что делает код, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4635e-146">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="4635e-147">Как видите, `toPigLatin` — это функция, которая принимает слово в качестве входных данных и преобразует его в представление Pig-Latin этого слова.</span><span class="sxs-lookup"><span data-stu-id="4635e-147">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="4635e-148">Ниже приведены правила для этого.</span><span class="sxs-lookup"><span data-stu-id="4635e-148">The rules for this are as follows:</span></span>

<span data-ttu-id="4635e-149">Если первый символ в слове начинается с гласной, добавьте «ура» в конец слова.</span><span class="sxs-lookup"><span data-stu-id="4635e-149">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="4635e-150">Если он не начинается с гласной, переместите первый символ в конец слова и добавьте в него «гг».</span><span class="sxs-lookup"><span data-stu-id="4635e-150">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="4635e-151">Вы могли заметить следующее в FSI:</span><span class="sxs-lookup"><span data-stu-id="4635e-151">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="4635e-152">Это означает, что `toPigLatin` — это функция, которая принимает `string` в качестве входных данных (с именем `word`) и возвращает другой `string`.</span><span class="sxs-lookup"><span data-stu-id="4635e-152">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="4635e-153">Это называется [сигнатурой типа функции](https://fsharpforfunandprofit.com/posts/function-signatures/)— основной частью F# этого ключа для понимания F# кода.</span><span class="sxs-lookup"><span data-stu-id="4635e-153">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="4635e-154">Это также можно заметить при наведении указателя мыши на функцию в Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4635e-154">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="4635e-155">В теле функции можно заметить две различные части:</span><span class="sxs-lookup"><span data-stu-id="4635e-155">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="4635e-156">Внутренняя функция, именуемая `isVowel`, определяющая, является ли данный символ (`c`) гласным, проверяя, соответствует ли он одному из указанных шаблонов через [сопоставление шаблонов](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="4635e-156">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="4635e-157">Выражение [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) , которое проверяет, является ли первый символ гласным, и формирует возвращаемое значение из входных символов на основе того, был ли первый символ гласным или нет:</span><span class="sxs-lookup"><span data-stu-id="4635e-157">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="4635e-158">Таким образом, поток `toPigLatin`:</span><span class="sxs-lookup"><span data-stu-id="4635e-158">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="4635e-159">Проверьте, является ли первый символ входного слова гласным.</span><span class="sxs-lookup"><span data-stu-id="4635e-159">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="4635e-160">Если это так, прикрепите "ура" к концу слова.</span><span class="sxs-lookup"><span data-stu-id="4635e-160">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="4635e-161">В противном случае переместите первый символ в конец слова и добавьте в него «гг».</span><span class="sxs-lookup"><span data-stu-id="4635e-161">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="4635e-162">Есть одно конечное замечание: нет явных инструкций для возврата из функции, в отличие от многих других языков.</span><span class="sxs-lookup"><span data-stu-id="4635e-162">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="4635e-163">Это происходит потому F# , что основан на выражениях, а Последнее выражение в теле функции является возвращаемым значением.</span><span class="sxs-lookup"><span data-stu-id="4635e-163">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="4635e-164">Поскольку `if..then..else` является выражением, в зависимости от входного значения будет возвращаться тело блока `then` или тело блока `else`.</span><span class="sxs-lookup"><span data-stu-id="4635e-164">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="turn-the-console-app-into-a-pig-latin-generator"></a><span data-ttu-id="4635e-165">Преобразование консольного приложения в генератор Pig Latin</span><span class="sxs-lookup"><span data-stu-id="4635e-165">Turn the console app into a Pig Latin generator</span></span>

<span data-ttu-id="4635e-166">В предыдущих разделах этой статьи был показан общий первый шаг в написании F# кода: написание начальной функции и ее интерактивное исполнение с помощью FSI.</span><span class="sxs-lookup"><span data-stu-id="4635e-166">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="4635e-167">Это называется разработкой на основе REPL, где [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) означает "чтение-вычисление-цикл печати".</span><span class="sxs-lookup"><span data-stu-id="4635e-167">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="4635e-168">Это отличный способ поэкспериментировать с функциями, пока не будет выполнена какая-то работа.</span><span class="sxs-lookup"><span data-stu-id="4635e-168">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="4635e-169">Следующим шагом в разработке на основе REPL является перемещение рабочего кода в файл F# реализации.</span><span class="sxs-lookup"><span data-stu-id="4635e-169">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="4635e-170">Затем он может быть скомпилирован F# компилятором в сборку, которую можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="4635e-170">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="4635e-171">Чтобы начать, откройте файл *Program. FS* , созданный ранее с помощью .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="4635e-171">To begin, open the *Program.fs* file that you created earlier with the .NET Core CLI.</span></span> <span data-ttu-id="4635e-172">Вы заметите, что в нем уже есть код.</span><span class="sxs-lookup"><span data-stu-id="4635e-172">You'll notice that some code is already in there.</span></span>

<span data-ttu-id="4635e-173">Затем создайте новый [`module`](../language-reference/modules.md) с именем `PigLatin` и скопируйте в него созданную ранее функцию `toPigLatin`:</span><span class="sxs-lookup"><span data-stu-id="4635e-173">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function you created earlier into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="4635e-174">Этот модуль должен быть выше `main` функции и под объявлением `open System`.</span><span class="sxs-lookup"><span data-stu-id="4635e-174">This module should be above the `main` function and below the `open System` declaration.</span></span> <span data-ttu-id="4635e-175">Порядок объявлений имеет значение F#, поэтому необходимо определить функцию перед вызовом ее в файле.</span><span class="sxs-lookup"><span data-stu-id="4635e-175">Order of declarations matters in F#, so you'll need to define the function before you call it in a file.</span></span>

<span data-ttu-id="4635e-176">Теперь в функции `main` вызовите функцию генератора латиницы pig для аргументов:</span><span class="sxs-lookup"><span data-stu-id="4635e-176">Now, in the `main` function, call your Pig Latin generator function on the arguments:</span></span>

```fsharp
[<EntryPoint>]
let main argv =
    for name in argv do
        let newName = PigLatin.toPigLatin name
        printfn "%s in Pig Latin is: %s" name newName

    0
```

<span data-ttu-id="4635e-177">Теперь вы можете запустить консольное приложение из командной строки:</span><span class="sxs-lookup"><span data-stu-id="4635e-177">Now you can run your console app from the command line:</span></span>

```console
dotnet run apple banana
```

<span data-ttu-id="4635e-178">Вы увидите, что он выводит тот же результат, что и файл скрипта, но на этот раз в качестве выполняемой программы!</span><span class="sxs-lookup"><span data-stu-id="4635e-178">And you'll see that it outputs the same result as your script file, but this time as a running program!</span></span>

## <a name="troubleshooting-ionide"></a><span data-ttu-id="4635e-179">Устранение неполадок Ionide</span><span class="sxs-lookup"><span data-stu-id="4635e-179">Troubleshooting Ionide</span></span>

<span data-ttu-id="4635e-180">Вот несколько способов устранения некоторых проблем, с которыми вы можете столкнуться.</span><span class="sxs-lookup"><span data-stu-id="4635e-180">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="4635e-181">Чтобы получить возможности редактирования кода Ionide, необходимо сохранить F# файлы на диске и в папке, открытой в Visual Studio Code рабочей области.</span><span class="sxs-lookup"><span data-stu-id="4635e-181">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
1. <span data-ttu-id="4635e-182">Если вы внесли изменения в систему или установили необходимые компоненты Ionide с Visual Studio Code открыть, перезапустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4635e-182">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
1. <span data-ttu-id="4635e-183">Если в каталогах проекта есть недопустимые символы, Ionide может не работать.</span><span class="sxs-lookup"><span data-stu-id="4635e-183">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="4635e-184">Переименуйте каталоги проектов, если это так.</span><span class="sxs-lookup"><span data-stu-id="4635e-184">Rename your project directories if this is the case.</span></span>
1. <span data-ttu-id="4635e-185">Если ни одна из команд Ionide не работает, проверьте [Visual Studio Code сочетания клавиш](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) , чтобы узнать, не переопределяете их случайно.</span><span class="sxs-lookup"><span data-stu-id="4635e-185">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
1. <span data-ttu-id="4635e-186">Если Ionide не работает на компьютере и ни один из указанных выше проблем не устранил проблему, попробуйте удалить `ionide-fsharp`ный каталог на компьютере и переустановить набор подключаемых модулей.</span><span class="sxs-lookup"><span data-stu-id="4635e-186">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>
1. <span data-ttu-id="4635e-187">Если не удалось загрузить проект ( F# Обозреватель решений покажет это), щелкните правой кнопкой мыши этот проект и выберите команду **Просмотреть подробности** , чтобы получить дополнительные диагностические сведения.</span><span class="sxs-lookup"><span data-stu-id="4635e-187">If a project failed to load (the F# Solution Explorer will show this), right-click on that project and click **See details** to get more diagnostic info.</span></span>

<span data-ttu-id="4635e-188">Ionide — это проект с открытым исходным кодом, созданный и обслуживаемый членами F# сообщества.</span><span class="sxs-lookup"><span data-stu-id="4635e-188">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="4635e-189">Сообщите о проблемах и вы можете участвовать в [репозитории GitHub ionide-vscode-FSharp](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="4635e-189">Please report issues and feel free to contribute at the [ionide-vscode-fsharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="4635e-190">Кроме того, вы можете запросить дополнительную помощь от разработчиков Ionide и F# сообщества в [канале Ionide gitter](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="4635e-190">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4635e-191">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="4635e-191">Next steps</span></span>

<span data-ttu-id="4635e-192">Дополнительные сведения о F# и функциях языка см. в статье [Обзор F# ](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="4635e-192">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
