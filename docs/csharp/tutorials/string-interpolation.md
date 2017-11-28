---
title: "Интерполяция строк. Язык C#"
description: "Узнайте, как работает интерполяция строк в C# 6"
keywords: ".NET, .NET Core, C#, строка"
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.openlocfilehash: ac19d4208da4f8ee6dd3e071ab70dbc41a0cd065
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="string-interpolation-in-c"></a><span data-ttu-id="b8333-104">Интерполяция строк в C#</span><span class="sxs-lookup"><span data-stu-id="b8333-104">String Interpolation in C#</span></span> #

<span data-ttu-id="b8333-105">Интерполяция строк — это процесс замены заполнителей в строке значениями строковой переменной.</span><span class="sxs-lookup"><span data-stu-id="b8333-105">String Interpolation is the way that placeholders in a string are replaced by the value of a string variable.</span></span> <span data-ttu-id="b8333-106">До версии C# 6 для этого приходилось применять метод `System.String.Format`.</span><span class="sxs-lookup"><span data-stu-id="b8333-106">Before C# 6, the way to do this is with `System.String.Format`.</span></span> <span data-ttu-id="b8333-107">Он работает нормально, но использует только нумерованные заполнители, что порой затрудняет восприятие синтаксических конструкций и усложняет их.</span><span class="sxs-lookup"><span data-stu-id="b8333-107">This works okay, but since it uses numbered placeholders, it can be harder to read and more verbose.</span></span>

<span data-ttu-id="b8333-108">В других языках программирования интерполяция строк уже достаточно давно является встроенной возможностью.</span><span class="sxs-lookup"><span data-stu-id="b8333-108">Other programming languages have had string interpolation built into the language for a while.</span></span> <span data-ttu-id="b8333-109">Например, в PHP можно сделать так:</span><span class="sxs-lookup"><span data-stu-id="b8333-109">For instance, in PHP:</span></span>

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

<span data-ttu-id="b8333-110">Наконец, в C# 6 мы тоже может выполнять такую интерполяцию строк.</span><span class="sxs-lookup"><span data-stu-id="b8333-110">In C# 6, we finally have that style of string interpolation.</span></span> <span data-ttu-id="b8333-111">Укажите перед строкой `$`, и все переменные и (или) выражения в ней будут заменены соответствующими значениями.</span><span class="sxs-lookup"><span data-stu-id="b8333-111">You can use a `$` before a string to indicate that it should substitute variables/expressions for their values.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8333-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b8333-112">Prerequisites</span></span>
<span data-ttu-id="b8333-113">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b8333-113">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="b8333-114">Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="b8333-114">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="b8333-115">Это приложение можно запустить в ОС Windows, Ubuntu Linux, macOS или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="b8333-115">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="b8333-116">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="b8333-116">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="b8333-117">В примерах ниже используется кроссплатформенный редактор [Visual Studio Code](https://code.visualstudio.com/) с открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="b8333-117">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="b8333-118">Вы можете заменить его на любое другое средство, с которым вам удобно работать.</span><span class="sxs-lookup"><span data-stu-id="b8333-118">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="b8333-119">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="b8333-119">Create the Application</span></span>

<span data-ttu-id="b8333-120">Теперь, когда вы установили все нужные средства, создайте новое приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b8333-120">Now that you've installed all the tools, create a new .NET Core application.</span></span> <span data-ttu-id="b8333-121">Чтобы использовать генератор командной строки, создайте для проекта каталог, например `interpolated`, и выполните следующую команду в любой удобной оболочке:</span><span class="sxs-lookup"><span data-stu-id="b8333-121">To use the command line generator, create a directory for your project, such as `interpolated`, and execute the following command in your favorite shell:</span></span>

```
dotnet new console
```

<span data-ttu-id="b8333-122">Эта команда создает скелет проекта .NET Core: файл проекта *interpolated.csproj* и файл исходного кода *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="b8333-122">This command will create a barebones .NET core project with a project file, *interpolated.csproj*, and a source code file, *Program.cs*.</span></span> <span data-ttu-id="b8333-123">Нужно также выполнить команду `dotnet restore`, чтобы восстановить зависимости, необходимые для компиляции проекта.</span><span class="sxs-lookup"><span data-stu-id="b8333-123">You will need to execute `dotnet restore` to restore the dependencies needed to compile this project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="b8333-124">Чтобы выполнить программу, используйте `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="b8333-124">To execute the program, use `dotnet run`.</span></span> <span data-ttu-id="b8333-125">Она выведет в консоль сообщение "Hello, World".</span><span class="sxs-lookup"><span data-stu-id="b8333-125">You should see "Hello, World" output to the console.</span></span>



## <a name="intro-to-string-interpolation"></a><span data-ttu-id="b8333-126">Знакомство с интерполяцией строк</span><span class="sxs-lookup"><span data-stu-id="b8333-126">Intro to String Interpolation</span></span>

<span data-ttu-id="b8333-127">При использовании `System.String.Format` в строку включаются специальные местозаполнители, которые заменяются параметрами, переданными вслед за строкой.</span><span class="sxs-lookup"><span data-stu-id="b8333-127">With `System.String.Format`, you specify "placeholders" in a string that are replaced by the parameters following the string.</span></span> <span data-ttu-id="b8333-128">Например:</span><span class="sxs-lookup"><span data-stu-id="b8333-128">For instance:</span></span>

[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

<span data-ttu-id="b8333-129">Этот код выводит строку "My name is Matt Groves".</span><span class="sxs-lookup"><span data-stu-id="b8333-129">That will output "My name is Matt Groves".</span></span>

<span data-ttu-id="b8333-130">В C# 6 вы теперь можете обойтись без `String.Format`. Определите интерполируемую строку, указав перед ней символ `$`, а затем просто используйте переменные прямо в этой строке.</span><span class="sxs-lookup"><span data-stu-id="b8333-130">In C# 6, instead of using `String.Format`, you define an interpolated string by prepending it with the `$` symbol, and then using the variables directly in the string.</span></span> <span data-ttu-id="b8333-131">Например:</span><span class="sxs-lookup"><span data-stu-id="b8333-131">For instance:</span></span>

[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

<span data-ttu-id="b8333-132">Можно использовать не только переменные.</span><span class="sxs-lookup"><span data-stu-id="b8333-132">You don't have to use just variables.</span></span> <span data-ttu-id="b8333-133">В фигурных скобках можно указать любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="b8333-133">You can use any expression within the brackets.</span></span> <span data-ttu-id="b8333-134">Например:</span><span class="sxs-lookup"><span data-stu-id="b8333-134">For instance:</span></span>

[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

<span data-ttu-id="b8333-135">Этот пример кода выведет данные:</span><span class="sxs-lookup"><span data-stu-id="b8333-135">Which would output:</span></span>

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a><span data-ttu-id="b8333-136">Как работает интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="b8333-136">How string interpolation works</span></span>

<span data-ttu-id="b8333-137">Компилятор преобразует синтаксис интерполяции в String.Format.</span><span class="sxs-lookup"><span data-stu-id="b8333-137">Behind the scenes, this string interpolation syntax is translated into String.Format by the compiler.</span></span> <span data-ttu-id="b8333-138">Таким образом, вы можете выполнять [все, что раньше можно было сделать со String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="b8333-138">So, you can do the [same type of stuff you've done before with String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).</span></span>

<span data-ttu-id="b8333-139">Например, можно добавить отбивку и форматирование чисел:</span><span class="sxs-lookup"><span data-stu-id="b8333-139">For instance, you can add padding and numeric formatting:</span></span>

[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

<span data-ttu-id="b8333-140">Приведенный выше пример выведет примерно следующее:</span><span class="sxs-lookup"><span data-stu-id="b8333-140">The above would output something like:</span></span>

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

<span data-ttu-id="b8333-141">Если имя переменной не найдено, создается ошибки времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="b8333-141">If a variable name is not found, then a compile time error will be generated.</span></span>

<span data-ttu-id="b8333-142">Например:</span><span class="sxs-lookup"><span data-stu-id="b8333-142">For instance:</span></span>

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

<span data-ttu-id="b8333-143">При компиляции этого кода, вы получите ошибки:</span><span class="sxs-lookup"><span data-stu-id="b8333-143">If you compile this, you'll get errors:</span></span>
 
* <span data-ttu-id="b8333-144">`Cannot use local variable 'adj' before it is declared` — это значит, что переменная `adj` объявляется *после* интерполируемой строки.</span><span class="sxs-lookup"><span data-stu-id="b8333-144">`Cannot use local variable 'adj' before it is declared` - the `adj` variable wasn't declared until *after* the interpolated string.</span></span>
* <span data-ttu-id="b8333-145">`The name 'otheranimal' does not exist in the current context` — это значит, что переменная с именем `otheranimal` вообще никогда не объявляется.</span><span class="sxs-lookup"><span data-stu-id="b8333-145">`The name 'otheranimal' does not exist in the current context` - a variable called `otheranimal` was never even declared</span></span>

## <a name="localization-and-internationalization"></a><span data-ttu-id="b8333-146">Локализация и интернационализация</span><span class="sxs-lookup"><span data-stu-id="b8333-146">Localization and Internationalization</span></span>

<span data-ttu-id="b8333-147">Интерполируемые строки поддерживают `IFormattable` и `FormattableString`, что можно удачно применять в контексте интернационализации.</span><span class="sxs-lookup"><span data-stu-id="b8333-147">An interpolated string supports `IFormattable` and `FormattableString`, which can be useful for internationalization.</span></span>

<span data-ttu-id="b8333-148">По умолчанию интерполируемая строка использует текущие настройки языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="b8333-148">By default, an interpolated string uses the current culture.</span></span> <span data-ttu-id="b8333-149">Чтобы использовать другие параметры, можно выполнить приведение строки к типу `IFormattable`.</span><span class="sxs-lookup"><span data-stu-id="b8333-149">To use a different culture, you could cast it as `IFormattable`</span></span>

<span data-ttu-id="b8333-150">Например:</span><span class="sxs-lookup"><span data-stu-id="b8333-150">For instance:</span></span>

[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

## <a name="conclusion"></a><span data-ttu-id="b8333-151">Заключение</span><span class="sxs-lookup"><span data-stu-id="b8333-151">Conclusion</span></span> 

<span data-ttu-id="b8333-152">В этом руководстве вы узнали, как использовать функции интерполяции строк в C# 6.</span><span class="sxs-lookup"><span data-stu-id="b8333-152">In this tutorial, you learned how to use string interpolation features of C# 6.</span></span> <span data-ttu-id="b8333-153">По сути это упрощенная запись обычной инструкции `String.Format`, допускающая несколько более сложных вариантов использования.</span><span class="sxs-lookup"><span data-stu-id="b8333-153">It's basically a more concise way of writing simple `String.Format` statements, with some caveats for more advanced uses of it.</span></span>
