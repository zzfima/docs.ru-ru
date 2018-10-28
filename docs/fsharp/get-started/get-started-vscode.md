---
title: 'Начало работы с F # в Visual Studio Code'
description: 'Сведения об использовании F # с помощью Visual Studio Code и Ionide suite подключаемого модуля.'
ms.date: 05/28/2018
ms.openlocfilehash: e962be2796cf0d6eb90d459730659e492f864716
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192672"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="fe1d4-103">Начало работы с F # в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fe1d4-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="fe1d4-104">Можно написать F # в [Visual Studio Code](https://code.visualstudio.com) с [подключаемый модуль Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) для получения кросс платформенных, облегченный интегрированная среда разработки (IDE) удобной с IntelliSense и базовый код операции рефакторинга.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="fe1d4-105">Посетите [Ionide.io](http://ionide.io) Дополнительные сведения о подключаемом модуле.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="fe1d4-106">Чтобы начать, убедитесь, что у вас есть [F # и правильно установлен подключаемый модуль Ionide](install-fsharp.md#install-f-with-visual-studio-code).</span><span class="sxs-lookup"><span data-stu-id="fe1d4-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="fe1d4-107">Создание первого проекта с помощью Ionide</span><span class="sxs-lookup"><span data-stu-id="fe1d4-107">Creating your first project with Ionide</span></span>

<span data-ttu-id="fe1d4-108">Чтобы создать проект F #, откройте Visual Studio Code в новую папку (можно назвать ее любым).</span><span class="sxs-lookup"><span data-stu-id="fe1d4-108">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="fe1d4-109">Затем откройте палитру команд (**представление > палитру команд**) и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-109">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="fe1d4-110">Это реализуется с помощью [FORGE](https://github.com/fsharp-editing/Forge) проекта.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-110">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
<span data-ttu-id="fe1d4-111">Если вы не видите параметры шаблона, обновите шаблоны, выполнив следующую команду в палитре команд: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-111">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="fe1d4-112">Выберите «: новый проект на F #», нажав **ввод**.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-112">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="fe1d4-113">Это осуществляется переход к следующему шагу, можно выбрать шаблон проекта.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-113">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="fe1d4-114">Выбрать `classlib` шаблона и нажмите клавишу **ввод**.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-114">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="fe1d4-115">Затем выберите каталог для создания проекта.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-115">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="fe1d4-116">Если оставить его пустым, используется текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-116">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="fe1d4-117">Наконец имя проекта на последнем шаге.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-117">Finally, name your project in the final step.</span></span> <span data-ttu-id="fe1d4-118">F # использует [регистре Pascal](http://c2.com/cgi/wiki?PascalCase) для имен проектов.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-118">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="fe1d4-119">В этой статье используется `ClassLibraryDemo` как имя.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-119">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="fe1d4-120">Как только вы ввели имя, которое будет для вашего проекта, попадания **ввод**.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-120">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="fe1d4-121">Если вы выполнили ранее, вы должны получить Visual Studio код рабочую область в левой части окна отображаются со следующими:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-121">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="fe1d4-122">F # сам проект, под `ClassLibraryDemo` папки.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-122">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="fe1d4-123">Правильной структуры каталогов для добавления пакетов с помощью [ `Paket` ](https://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="fe1d4-123">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="fe1d4-124">Кросс платформенные сборки скрипт с [ `FAKE` ](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="fe1d4-124">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="fe1d4-125">`paket.exe` Исполняемый файл, который можно получить пакеты и разрешать зависимости для вас.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-125">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="fe1d4-126">Объект `.gitignore` файла, если вы хотите добавить этот проект в системе управления версиями на основе Git.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-126">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="fe1d4-127">Написав некоторый код</span><span class="sxs-lookup"><span data-stu-id="fe1d4-127">Writing some code</span></span>

<span data-ttu-id="fe1d4-128">Откройте *ClassLibraryDemo* папки.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-128">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="fe1d4-129">Вы должны увидеть следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-129">You should see the following files:</span></span>

1. <span data-ttu-id="fe1d4-130">`ClassLibraryDemo.fs`, файле реализации F # с помощью класса, определенного.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-130">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="fe1d4-131">`ClassLibraryDemo.fsproj`, F # файл проекта используется для построения этого проекта.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-131">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="fe1d4-132">`Script.fsx`, в файл скрипта F #, загружающий исходного файла.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-132">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="fe1d4-133">`paket.references`, файл Paket, который задает зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-133">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="fe1d4-134">Откройте `Script.fsx`и добавьте следующий код в конце его:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-134">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="fe1d4-135">Эта функция преобразует слово в форму [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="fe1d4-135">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="fe1d4-136">Далее необходимо оценить с помощью F # интерактивный (FSI).</span><span class="sxs-lookup"><span data-stu-id="fe1d4-136">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="fe1d4-137">Выделите всей функции (должна быть 11 строк).</span><span class="sxs-lookup"><span data-stu-id="fe1d4-137">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="fe1d4-138">Как только он будет выделен, удерживайте **Alt** ключа и нажмите кнопку **ввод**.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-138">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="fe1d4-139">Вы заметите окно, всплывающее окно под, и она должна отобразиться примерно следующее:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-139">You'll notice a window pop up below, and it should show something like this:</span></span>

![Пример F # Interactive выходных данных с помощью Ionide](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="fe1d4-141">Это выполняет три действия:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-141">This did three things:</span></span>

1. <span data-ttu-id="fe1d4-142">Он запущен процесс FSI.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-142">It started the FSI process.</span></span>
2. <span data-ttu-id="fe1d4-143">Над процессом FSI он отправлен выделенный вами код.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-143">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="fe1d4-144">Процесс FSI вычисляется код, который вы отправили по.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-144">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="fe1d4-145">Так как все отправленные через [функция](../language-reference/functions/index.md), теперь можно вызвать этой функции с FSI!</span><span class="sxs-lookup"><span data-stu-id="fe1d4-145">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="fe1d4-146">В интерактивном окне введите следующее:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-146">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="fe1d4-147">Вы должны увидеть следующий результат:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-147">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="fe1d4-148">Теперь давайте попробуем с первой буквой гласных.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-148">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="fe1d4-149">Введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-149">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="fe1d4-150">Вы должны увидеть следующий результат:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-150">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="fe1d4-151">Функция будет работать правильно.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-151">The function appears to be working as expected.</span></span> <span data-ttu-id="fe1d4-152">Поздравляем, вы только что написал свою первую функцию F # в Visual Studio Code и оценки его FSI.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-152">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="fe1d4-153">Как вы могли заметить, строки в FSI завершаются `;;`.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-153">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="fe1d4-154">Это обусловлено FSI позволяет вводить несколько строк.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-154">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="fe1d4-155">`;;` В конце позволяет FSI знать, когда код будет завершено.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-155">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="fe1d4-156">О том, в коде</span><span class="sxs-lookup"><span data-stu-id="fe1d4-156">Explaining the code</span></span>

<span data-ttu-id="fe1d4-157">Если вы не уверены, что фактически выполняет код, вот поэтапные.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-157">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="fe1d4-158">Как вы видите, `toPigLatin` — это функция, которая принимает слова в качестве входных данных и преобразует его в Pig Latin данного слова.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-158">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="fe1d4-159">Правила определены следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-159">The rules for this are as follows:</span></span>

<span data-ttu-id="fe1d4-160">Если первый символ в слово начинается с гласных, добавьте в конец слова «yay».</span><span class="sxs-lookup"><span data-stu-id="fe1d4-160">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="fe1d4-161">Если он не начинается с гласных, переместить первого знака до конца слова и «ay» добавить к нему.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-161">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="fe1d4-162">Можно заметить следующие FSI:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-162">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="fe1d4-163">Это означает, что `toPigLatin` — это функция, которая принимает `string` как входные данные (вызывается `word`) и возвращает другой `string`.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-163">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="fe1d4-164">Этот процесс называется [сигнатура типа функции](https://fsharpforfunandprofit.com/posts/function-signatures/), важнейший элемент F #, который является ключом к пониманию кода F #.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-164">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="fe1d4-165">Можно также заметить при наведении указателя на функцию в Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-165">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="fe1d4-166">В теле функции вы заметите две различные части:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-166">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="fe1d4-167">Внутренняя функция, вызывается `isVowel`, определяющий, если определенный символ (`c`) является гласных путем проверки, если он соответствует одному из шаблонов, предоставленные через [сопоставление шаблонов](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="fe1d4-167">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="fe1d4-168">[ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) Выражение, которое проверяет, если первый символ — гласных и конструкций, возвращаемое значение из входных символов на основе Если первый символ был гласных или нет:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-168">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="fe1d4-169">Поток `toPigLatin` , таким образом:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-169">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="fe1d4-170">Проверьте, является ли первый символ входного слово гласных.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-170">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="fe1d4-171">Если это так, подключите «yay» до конца слова.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-171">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="fe1d4-172">В противном случае переместите первого знака до конца слова и «ay» добавить к нему.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-172">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="fe1d4-173">Имеется заключительную Обратите внимание, что об этом: нет нет явных инструкций для возврата из функции, в отличие от многих других языков.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-173">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="fe1d4-174">Это так, как F # основано на выражении, и последнего выражения в теле функции является возвращаемым значением.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-174">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="fe1d4-175">Так как `if..then..else` сам является выражением, тело `then` блока или в тексте `else` блок будет возвращаться в зависимости от входного значения.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-175">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="fe1d4-176">Перемещение кода скрипта в файле реализации</span><span class="sxs-lookup"><span data-stu-id="fe1d4-176">Moving your script code into the implementation file</span></span>

<span data-ttu-id="fe1d4-177">Предыдущих разделах этой статьи показано распространенных первым шагом в написании кода F #: написание функцию начальной и выполнение его в интерактивном режиме с FSI.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-177">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="fe1d4-178">Этот процесс известен как разработка на основе REPL, где [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) расшифровывается как «Read-Evaluate-Print Loop».</span><span class="sxs-lookup"><span data-stu-id="fe1d4-178">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="fe1d4-179">Это отличный способ поэкспериментировать с функциональными возможностями, пока не получится, что-то работа.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-179">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="fe1d4-180">Следующий шаг в разработки на основе REPL является перемещение рабочий код в файле реализации F #.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-180">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="fe1d4-181">Его можно затем скомпилировать компилятором F # в сборку, которая может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-181">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="fe1d4-182">Для начала работы откройте `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-182">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="fe1d4-183">Вы заметите, что некоторый код уже существует.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-183">You'll notice that some code is already in there.</span></span> <span data-ttu-id="fe1d4-184">Продолжить и удалить определение класса, но не забудьте оставить [ `namespace` ](../language-reference/namespaces.md) объявление вверху.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-184">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="fe1d4-185">Создайте новый [ `module` ](../language-reference/modules.md) вызывается `PigLatin` и скопируйте `toPigLatin` функции в нее таким образом:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-185">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="fe1d4-186">Затем откройте `Script.fsx` файл еще раз и удалить весь `toPigLatin` работать, но не забудьте сохранить следующие две строки в файле:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-186">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="fe1d4-187">Первая строка необходима для сценариев для загрузки FSI `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-187">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span> <span data-ttu-id="fe1d4-188">Вторая строка — это удобный способ: пропуск он необязателен, но вам будет нужно ввести `open ClassLibraryDemo` в окне с FSI, если вы хотите перевести `ToPigLatin` модуль в область действия.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-188">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="fe1d4-189">Затем в окне «FSI» вызовите функцию с `PigLatin` модуль, который вы задали ранее:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-189">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="fe1d4-190">Готово!</span><span class="sxs-lookup"><span data-stu-id="fe1d4-190">Success!</span></span> <span data-ttu-id="fe1d4-191">Вы получите те же результаты, но теперь загружаются из файла реализации F #.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-191">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="fe1d4-192">Основное различие здесь — что файлы исходного кода F #, компилируются в сборки, которые могут быть выполнены в любом месте, не только в FSI.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-192">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="fe1d4-193">Сводка</span><span class="sxs-lookup"><span data-stu-id="fe1d4-193">Summary</span></span>

<span data-ttu-id="fe1d4-194">В этой статье вы узнали:</span><span class="sxs-lookup"><span data-stu-id="fe1d4-194">In this article, you've learned:</span></span>

1. <span data-ttu-id="fe1d4-195">Как настроить Visual Studio Code с помощью Ionide.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-195">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="fe1d4-196">Как создать первый проект F # с помощью Ionide.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-196">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="fe1d4-197">Как использовать скрипт F # для создания первой функции F # на Ionide, а затем выполнить его в FSI.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-197">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="fe1d4-198">Как перенести код сценария для исходного кода F # и затем вызвать этот исходный текст из FSI.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-198">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="fe1d4-199">Вы являетесь теперь есть все необходимое для написания гораздо больше кода F #, с помощью Visual Studio Code и Ionide.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-199">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="fe1d4-200">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="fe1d4-200">Troubleshooting</span></span>

<span data-ttu-id="fe1d4-201">Ниже приведены несколько способов устранения некоторых проблем, которые вы можете столкнуться.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-201">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="fe1d4-202">Чтобы получить возможности редактирования кода среды Ionide, файлы F # должны быть сохранены на диске, а также внутри папки, который открыт в рабочей области Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-202">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="fe1d4-203">Если были внесены изменения в систему или установить необходимые компоненты Ionide с помощью Visual Studio Code откройте, перезапустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-203">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="fe1d4-204">Проверьте, что можно использовать компилятор F # и F # interactive из командной строки без полного пути.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-204">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="fe1d4-205">Это можно сделать, введя `fsc` в командной строки для компилятора F #, и `fsi` или `fsharpi` Visual F # tools на Windows и Mono в Mac/Linux, соответственно.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-205">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="fe1d4-206">Если у вас есть недопустимые символы в каталогах проекта, Ionide может не работать.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-206">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="fe1d4-207">Переименование каталогов проекта, если это так.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-207">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="fe1d4-208">Если ни одна из команд Ionide работаете, проверьте ваши [сочетания клавиш Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) для просмотра, если вы переопределение случайно.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-208">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="fe1d4-209">Если Ionide разбивается на вашем компьютере, и ни один из указанных выше исправил вашу проблему, попробуйте удалить `ionide-fsharp` каталог на компьютере и переустановить suite подключаемого модуля.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-209">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="fe1d4-210">Ionide — проект с открытым исходным кодом создаваемый и используемый средством членами сообщества F #.</span><span class="sxs-lookup"><span data-stu-id="fe1d4-210">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="fe1d4-211">Пожалуйста, сообщить о проблемах и вы можете внести свой вклад в [Ionide VSCode: репозиторий FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="fe1d4-211">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="fe1d4-212">Если у вас проблема к отчету, выполните [инструкции по получению журналы для использования при описании проблемы](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="fe1d4-212">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="fe1d4-213">Также можно задать для получения дополнительных сведений от Ionide разработчиков и сообщества F # в [Ionide Gitter канал](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="fe1d4-213">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe1d4-214">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fe1d4-214">Next steps</span></span>

<span data-ttu-id="fe1d4-215">Дополнительные сведения о F # и возможности языка, извлечение [обзор языка F #](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="fe1d4-215">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
