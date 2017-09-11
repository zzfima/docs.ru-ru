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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: de8f77e44319731f87f00d227a5373a78bf40e32
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="string-interpolation-in-c"></a><span data-ttu-id="2fad2-104">Интерполяция строк в C#</span><span class="sxs-lookup"><span data-stu-id="2fad2-104">String Interpolation in C#</span></span> #

<span data-ttu-id="2fad2-105">Интерполяция строк — это процесс замены заполнителей в строке значениями строковой переменной.</span><span class="sxs-lookup"><span data-stu-id="2fad2-105">String Interpolation is the way that placeholders in a string are replaced by the value of a string variable.</span></span> <span data-ttu-id="2fad2-106">До версии C# 6 для этого приходилось применять метод `System.String.Format`.</span><span class="sxs-lookup"><span data-stu-id="2fad2-106">Before C# 6, the way to do this is with `System.String.Format`.</span></span> <span data-ttu-id="2fad2-107">Он работает нормально, но использует только нумерованные заполнители, что порой затрудняет восприятие синтаксических конструкций и усложняет их.</span><span class="sxs-lookup"><span data-stu-id="2fad2-107">This works okay, but since it uses numbered placeholders, it can be harder to read and more verbose.</span></span>

<span data-ttu-id="2fad2-108">В других языках программирования интерполяция строк уже достаточно давно является встроенной возможностью.</span><span class="sxs-lookup"><span data-stu-id="2fad2-108">Other programming languages have had string interpolation built into the language for a while.</span></span> <span data-ttu-id="2fad2-109">Например, в PHP можно сделать так:</span><span class="sxs-lookup"><span data-stu-id="2fad2-109">For instance, in PHP:</span></span>

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

<span data-ttu-id="2fad2-110">Наконец, в C# 6 мы тоже может выполнять такую интерполяцию строк.</span><span class="sxs-lookup"><span data-stu-id="2fad2-110">In C# 6, we finally have that style of string interpolation.</span></span> <span data-ttu-id="2fad2-111">Укажите перед строкой `$`, и все переменные и (или) выражения в ней будут заменены соответствующими значениями.</span><span class="sxs-lookup"><span data-stu-id="2fad2-111">You can use a `$` before a string to indicate that it should substitute variables/expressions for their values.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2fad2-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2fad2-112">Prerequisites</span></span>
<span data-ttu-id="2fad2-113">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fad2-113">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="2fad2-114">Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="2fad2-114">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="2fad2-115">Это приложение можно запустить в ОС Windows, Ubuntu Linux, macOS или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="2fad2-115">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="2fad2-116">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="2fad2-116">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="2fad2-117">В примерах ниже используется кроссплатформенный редактор [Visual Studio Code](https://code.visualstudio.com/) с открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="2fad2-117">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="2fad2-118">Вы можете заменить его на любое другое средство, с которым вам удобно работать.</span><span class="sxs-lookup"><span data-stu-id="2fad2-118">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="2fad2-119">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="2fad2-119">Create the Application</span></span>

<span data-ttu-id="2fad2-120">Теперь, когда вы установили все нужные средства, создайте новое приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fad2-120">Now that you've installed all the tools, create a new .NET Core application.</span></span> <span data-ttu-id="2fad2-121">Чтобы использовать генератор командной строки, создайте для проекта каталог, например `interpolated`, и выполните следующую команду в любой удобной оболочке:</span><span class="sxs-lookup"><span data-stu-id="2fad2-121">To use the command line generator, create a directory for your project, such as `interpolated`, and execute the following command in your favorite shell:</span></span>

```
dotnet new console
```

<span data-ttu-id="2fad2-122">Эта команда создает скелет проекта .NET Core: файл проекта *interpolated.csproj* и файл исходного кода *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="2fad2-122">This command will create a barebones .NET core project with a project file, *interpolated.csproj*, and a source code file, *Program.cs*.</span></span> <span data-ttu-id="2fad2-123">Нужно также выполнить команду `dotnet restore`, чтобы восстановить зависимости, необходимые для компиляции проекта.</span><span class="sxs-lookup"><span data-stu-id="2fad2-123">You will need to execute `dotnet restore` to restore the dependencies needed to compile this project.</span></span>

<span data-ttu-id="2fad2-124">Чтобы выполнить программу, используйте `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="2fad2-124">To execute the program, use `dotnet run`.</span></span> <span data-ttu-id="2fad2-125">Она выведет в консоль сообщение "Hello, World".</span><span class="sxs-lookup"><span data-stu-id="2fad2-125">You should see "Hello, World" output to the console.</span></span>

## <a name="intro-to-string-interpolation"></a><span data-ttu-id="2fad2-126">Знакомство с интерполяцией строк</span><span class="sxs-lookup"><span data-stu-id="2fad2-126">Intro to String Interpolation</span></span>

<span data-ttu-id="2fad2-127">При использовании `System.String.Format` в строку включаются специальные местозаполнители, которые заменяются параметрами, переданными вслед за строкой.</span><span class="sxs-lookup"><span data-stu-id="2fad2-127">With `System.String.Format`, you specify "placeholders" in a string that are replaced by the parameters following the string.</span></span> <span data-ttu-id="2fad2-128">Например:</span><span class="sxs-lookup"><span data-stu-id="2fad2-128">For instance:</span></span>

<span data-ttu-id="2fad2-129">[!code-csharp[Пример использования метода String.Format](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]</span><span class="sxs-lookup"><span data-stu-id="2fad2-129">[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]</span></span>  

<span data-ttu-id="2fad2-130">Этот код выводит строку "My name is Matt Groves".</span><span class="sxs-lookup"><span data-stu-id="2fad2-130">That will output "My name is Matt Groves".</span></span>

<span data-ttu-id="2fad2-131">В C# 6 вы теперь можете обойтись без `String.Format`. Определите интерполируемую строку, указав перед ней символ `$`, а затем просто используйте переменные прямо в этой строке.</span><span class="sxs-lookup"><span data-stu-id="2fad2-131">In C# 6, instead of using `String.Format`, you define an interpolated string by prepending it with the `$` symbol, and then using the variables directly in the string.</span></span> <span data-ttu-id="2fad2-132">Например:</span><span class="sxs-lookup"><span data-stu-id="2fad2-132">For instance:</span></span>

<span data-ttu-id="2fad2-133">[!code-csharp[Пример интерполяции](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]</span><span class="sxs-lookup"><span data-stu-id="2fad2-133">[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]</span></span>  

<span data-ttu-id="2fad2-134">Можно использовать не только переменные.</span><span class="sxs-lookup"><span data-stu-id="2fad2-134">You don't have to use just variables.</span></span> <span data-ttu-id="2fad2-135">В фигурных скобках можно указать любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="2fad2-135">You can use any expression within the brackets.</span></span> <span data-ttu-id="2fad2-136">Например:</span><span class="sxs-lookup"><span data-stu-id="2fad2-136">For instance:</span></span>

<span data-ttu-id="2fad2-137">[!code-csharp[Пример выражения в интерполяции](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]</span><span class="sxs-lookup"><span data-stu-id="2fad2-137">[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]</span></span>  

<span data-ttu-id="2fad2-138">Этот пример кода выведет данные:</span><span class="sxs-lookup"><span data-stu-id="2fad2-138">Which would output:</span></span>

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a><span data-ttu-id="2fad2-139">Как работает интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="2fad2-139">How string interpolation works</span></span>

<span data-ttu-id="2fad2-140">Компилятор преобразует синтаксис интерполяции в String.Format.</span><span class="sxs-lookup"><span data-stu-id="2fad2-140">Behind the scenes, this string interpolation syntax is translated into String.Format by the compiler.</span></span> <span data-ttu-id="2fad2-141">Таким образом, вы можете выполнять [все, что раньше можно было сделать со String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="2fad2-141">So, you can do the [same type of stuff you've done before with String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).</span></span>

<span data-ttu-id="2fad2-142">Например, можно добавить отбивку и форматирование чисел:</span><span class="sxs-lookup"><span data-stu-id="2fad2-142">For instance, you can add padding and numeric formatting:</span></span>

<span data-ttu-id="2fad2-143">[!code-csharp[Пример интерполяции с форматированием](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]</span><span class="sxs-lookup"><span data-stu-id="2fad2-143">[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]</span></span>  

<span data-ttu-id="2fad2-144">Приведенный выше пример выведет примерно следующее:</span><span class="sxs-lookup"><span data-stu-id="2fad2-144">The above would output something like:</span></span>

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

<span data-ttu-id="2fad2-145">Если имя переменной не найдено, создается ошибки времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="2fad2-145">If a variable name is not found, then a compile time error will be generated.</span></span>

<span data-ttu-id="2fad2-146">Например:</span><span class="sxs-lookup"><span data-stu-id="2fad2-146">For instance:</span></span>

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

<span data-ttu-id="2fad2-147">При компиляции этого кода, вы получите ошибки:</span><span class="sxs-lookup"><span data-stu-id="2fad2-147">If you compile this, you'll get errors:</span></span>
 
* <span data-ttu-id="2fad2-148">`Cannot use local variable 'adj' before it is declared` — это значит, что переменная `adj` объявляется *после* интерполируемой строки.</span><span class="sxs-lookup"><span data-stu-id="2fad2-148">`Cannot use local variable 'adj' before it is declared` - the `adj` variable wasn't declared until *after* the interpolated string.</span></span>
* <span data-ttu-id="2fad2-149">`The name 'otheranimal' does not exist in the current context` — это значит, что переменная с именем `otheranimal` вообще никогда не объявляется.</span><span class="sxs-lookup"><span data-stu-id="2fad2-149">`The name 'otheranimal' does not exist in the current context` - a variable called `otheranimal` was never even declared</span></span>

## <a name="localization-and-internationalization"></a><span data-ttu-id="2fad2-150">Локализация и интернационализация</span><span class="sxs-lookup"><span data-stu-id="2fad2-150">Localization and Internationalization</span></span>

<span data-ttu-id="2fad2-151">Интерполируемые строки поддерживают `IFormattable` и `FormattableString`, что можно удачно применять в контексте интернационализации.</span><span class="sxs-lookup"><span data-stu-id="2fad2-151">An interpolated string supports `IFormattable` and `FormattableString`, which can be useful for internationalization.</span></span>

<span data-ttu-id="2fad2-152">По умолчанию интерполируемая строка использует текущие настройки языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="2fad2-152">By default, an interpolated string uses the current culture.</span></span> <span data-ttu-id="2fad2-153">Чтобы использовать другие параметры, можно выполнить приведение строки к типу `IFormattable`.</span><span class="sxs-lookup"><span data-stu-id="2fad2-153">To use a different culture, you could cast it as `IFormattable`</span></span>

<span data-ttu-id="2fad2-154">Например:</span><span class="sxs-lookup"><span data-stu-id="2fad2-154">For instance:</span></span>

<span data-ttu-id="2fad2-155">[!code-csharp[Пример интерполяции с интернационализацией](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]</span><span class="sxs-lookup"><span data-stu-id="2fad2-155">[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]</span></span>  

## <a name="conclusion"></a><span data-ttu-id="2fad2-156">Заключение</span><span class="sxs-lookup"><span data-stu-id="2fad2-156">Conclusion</span></span> 

<span data-ttu-id="2fad2-157">В этом руководстве вы узнали, как использовать функции интерполяции строк в C# 6.</span><span class="sxs-lookup"><span data-stu-id="2fad2-157">In this tutorial, you learned how to use string interpolation features of C# 6.</span></span> <span data-ttu-id="2fad2-158">По сути это упрощенная запись обычной инструкции `String.Format`, допускающая несколько более сложных вариантов использования.</span><span class="sxs-lookup"><span data-stu-id="2fad2-158">It's basically a more concise way of writing simple `String.Format` statements, with some caveats for more advanced uses of it.</span></span>

