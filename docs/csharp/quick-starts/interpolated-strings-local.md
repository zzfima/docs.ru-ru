---
title: "Интерактивное руководство по интерполированным строкам. Краткие руководства по локальной разработке на C#"
description: "В этом кратком руководстве, посвященном интерполированным строкам, вы напишете код C#, чтобы включить результат выражения в строку большего размера."
author: rpetrusha
ms.author: ronpet
ms.date: 01/11/2018
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: b6089b69eb350fce29f86f19f5abeb44acb4b6b4
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="interpolated-strings"></a><span data-ttu-id="4549f-103">Интерполированные строки</span><span class="sxs-lookup"><span data-stu-id="4549f-103">Interpolated strings</span></span>

<span data-ttu-id="4549f-104">Это краткое руководство описывает, как с помощью интерполированных строк в C# вставить значения в одну строку вывода.</span><span class="sxs-lookup"><span data-stu-id="4549f-104">This quickstart teaches you how to use interpolated strings in C# to insert values into a single ouput string.</span></span> <span data-ttu-id="4549f-105">Вы напишете код C# и сможете просмотреть результаты его компиляции и выполнения.</span><span class="sxs-lookup"><span data-stu-id="4549f-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="4549f-106">Это краткое руководство содержит ряд занятий по вставке значений в строки и разнообразному форматированию этих значений.</span><span class="sxs-lookup"><span data-stu-id="4549f-106">The quickstart contains a series of lessons that insert values into strings, and format those values in different ways.</span></span>

<span data-ttu-id="4549f-107">Для работы с этим кратким руководством вам потребуется компьютер, который можно использовать для разработки.</span><span class="sxs-lookup"><span data-stu-id="4549f-107">This quickstart expects that you have a machine you can use for development.</span></span> <span data-ttu-id="4549f-108">В руководстве по [началу работы с .NET за 10 минут](https://www.microsoft.com/net/core) содержатся инструкции по настройке локальной среды разработки на компьютерах Mac, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="4549f-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="4549f-109">Краткий обзор команд, которые будут здесь использоваться, и ссылки на дополнительные сведения представлены в [вводной статье к руководствам по локальной разработке](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4549f-109">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span> 

## <a name="create-an-interpolated-string"></a><span data-ttu-id="4549f-110">Создание интерполированной строки</span><span class="sxs-lookup"><span data-stu-id="4549f-110">Create an interpolated string</span></span>

<span data-ttu-id="4549f-111">Создайте каталог с именем **interpolated-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="4549f-111">Create a directory named **interpolated-quickstart**.</span></span> <span data-ttu-id="4549f-112">Сделайте его текущим, выполнив следующую команду в окне консоли:</span><span class="sxs-lookup"><span data-stu-id="4549f-112">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console -n interpolated -o .
```

<span data-ttu-id="4549f-113">Эта команда создает консольное приложение .NET Core в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4549f-113">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="4549f-114">Откройте файл **Program.cs** в любом редакторе и замените строку `Console.WriteLine("Hello World!");` следующим кодом, указав вместо `<name>` свое имя:</span><span class="sxs-lookup"><span data-stu-id="4549f-114">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```
<span data-ttu-id="4549f-115">Чтобы выполнить этот код, введите `dotnet run` в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="4549f-115">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="4549f-116">При запуске программы отображается одна строка, которая содержит ваше имя в приветствии.</span><span class="sxs-lookup"><span data-stu-id="4549f-116">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="4549f-117">Строка, включенная в вызов метода <xref:System.Console.WriteLine%2A>, является *интерполированной*.</span><span class="sxs-lookup"><span data-stu-id="4549f-117">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="4549f-118">Это похоже на шаблон, позволяющий создать одну строку (называемую *результирующей строкой*) из строки, содержащей внедренный код.</span><span class="sxs-lookup"><span data-stu-id="4549f-118">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="4549f-119">Интерполированные строки особенно удобны при вставке значений в строку или сцеплении (объединении) строк.</span><span class="sxs-lookup"><span data-stu-id="4549f-119">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span> 
    
<span data-ttu-id="4549f-120">Этот простой пример содержит два элемента, обязательные для каждой интерполированной строки:</span><span class="sxs-lookup"><span data-stu-id="4549f-120">This simple example contains the two elements that every interpolated string must have:</span></span> 

- <span data-ttu-id="4549f-121">Строковый литерал, который начинается с символа `$`, стоящего до открывающей кавычки.</span><span class="sxs-lookup"><span data-stu-id="4549f-121">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="4549f-122">Между символом `$` и знаком кавычки не должно быть пробелов.</span><span class="sxs-lookup"><span data-stu-id="4549f-122">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="4549f-123">(Если вы хотите узнать, что при этом случится, вставьте пробел после символа `$`, сохраните файл и снова запустите программу, введя `dotnet run` в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="4549f-123">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="4549f-124">Компилятор C# отображает сообщение "Ошибка CS1056. Непредвиденный знак "$"".)</span><span class="sxs-lookup"><span data-stu-id="4549f-124">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span> 

- <span data-ttu-id="4549f-125">Одно или несколько *интерполированных выражений*.</span><span class="sxs-lookup"><span data-stu-id="4549f-125">One or more *interpolated expressions*.</span></span> <span data-ttu-id="4549f-126">Интерполированное выражение обозначено открывающей и закрывающей фигурной скобкой (`{` и `}`).</span><span class="sxs-lookup"><span data-stu-id="4549f-126">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="4549f-127">Вы можете указать внутри фигурных скобок любое выражение C#, возвращающее значение (включая `null`).</span><span class="sxs-lookup"><span data-stu-id="4549f-127">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span> 

<span data-ttu-id="4549f-128">Давайте рассмотрим еще несколько примеров интерполированных строк с другими типами данных.</span><span class="sxs-lookup"><span data-stu-id="4549f-128">Let's try a few more interpolated string examples with some other data types.</span></span>
    
## <a name="include-different-data-types"></a><span data-ttu-id="4549f-129">Включение разных типов данных</span><span class="sxs-lookup"><span data-stu-id="4549f-129">Include different data types</span></span>

<span data-ttu-id="4549f-130">В предыдущем разделе вы использовали интерполированную строку для вставки одной строки внутрь другой.</span><span class="sxs-lookup"><span data-stu-id="4549f-130">In the previous section, you used an interpolated string to insert one string inside of another.</span></span> <span data-ttu-id="4549f-131">Однако выражение интерполированной строки может относиться к любому типу данных.</span><span class="sxs-lookup"><span data-stu-id="4549f-131">An interpolated string expression can be any data type, though.</span></span> <span data-ttu-id="4549f-132">Давайте рассмотрим интерполированную строку со значениями нескольких типов данных.</span><span class="sxs-lookup"><span data-stu-id="4549f-132">Let's try an interpolated string that has values of multiple data types.</span></span> 
    
<span data-ttu-id="4549f-133">Приведенный ниже пример включает интерполированные выражения с объектом `Vegetable`, членом перечисления `Unit`, значением <xref:System.DateTime> и значением <xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="4549f-133">The following example includes interpolated expressions with a `Vegetable` object, a member of the `Unit` enumeration, a <xref:System.DateTime> value, and a <xref:System.Decimal> value.</span></span> <span data-ttu-id="4549f-134">Замените весь код C# в редакторе следующим кодом, а затем используйте команду `console run`, чтобы запустить его:</span><span class="sxs-lookup"><span data-stu-id="4549f-134">Replace all of the C# code in your editor with the following code, and then use the `console run` command to run it:</span></span>

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Example
{
   public enum Unit { item, pound, ounce, dozen };
   
   public static void Main()
   {
      var item = new Vegetable("eggplant");
      var date = DateTime.Now;
      var price = 1.99m;
      var unit = Unit.item;
      Console.WriteLine($"On {date}, the price of {item} was {price} per {unit}.");
   }
}
```
    
<span data-ttu-id="4549f-135">Обратите внимание, что второе интерполированное выражение включает объект `item` в результирующую строку, которая выводится на консоль. В данном случае в результирующую строку вставляется строка "eggplant" (баклажан).</span><span class="sxs-lookup"><span data-stu-id="4549f-135">Note that the second interpolated expression includes the `item` object in the result string that's displayed to the console, and in this case the string "eggplant" is inserted into the result string.</span></span> <span data-ttu-id="4549f-136">Это вызвано тем, что если тип интерполированного выражения отличается от строки, компилятор C# делает следующее:</span><span class="sxs-lookup"><span data-stu-id="4549f-136">That's because, when the type of an interpolated expression is not a string, the C# compiler does the following:</span></span>

- <span data-ttu-id="4549f-137">Если интерполированное выражение равно `null`, оно возвращает пустую строку ("" или <xref:System.String.Empty?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="4549f-137">If the interpolated expression is `null`, the interpolated expression returns an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>).</span></span>

- <span data-ttu-id="4549f-138">Если интерполированное выражение не равно `null`, вызывается метод `ToString` для типа интерполированного выражения.</span><span class="sxs-lookup"><span data-stu-id="4549f-138">If the interpolated expression is not `null`, the `ToString` method of the type of the interpolated expression is called.</span></span> <span data-ttu-id="4549f-139">Это можно проверить, закомментировав определение метода `Vegetable.ToString` в этом примере, для чего перед ним нужно поставить символ комментария (`//`).</span><span class="sxs-lookup"><span data-stu-id="4549f-139">You can test this by commenting out the definition of the `Vegetable.ToString` method in the example by putting a comment symbol (`//`) in front of it.</span></span> <span data-ttu-id="4549f-140">В выходных данных строка "eggplant" заменяется именем типа "Vegetable" (овощ), что является стандартным поведением метода <xref:System.Object.ToString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4549f-140">In the output, the string "eggplant" is replaced by the type name, "Vegetable", which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span>   

<span data-ttu-id="4549f-141">В выходных данных этого примера дата является слишком точной (цена на баклажаны не меняется каждую секунду), а в значении цены не указана единица измерения валюты.</span><span class="sxs-lookup"><span data-stu-id="4549f-141">In the output from this example, the date is too precise (the price of eggplant does not vary by the second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="4549f-142">В следующем разделе вы узнаете, как устранить эти проблемы, управляя форматом строк, возвращаемых интерполированными выражениями.</span><span class="sxs-lookup"><span data-stu-id="4549f-142">In the next section, you'll learn how to fix those issues by controlling the format of strings returned by interpolated expressions.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="4549f-143">Управление форматированием интерполированных выражений</span><span class="sxs-lookup"><span data-stu-id="4549f-143">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="4549f-144">В предыдущем разделе мы вставили две неправильно отформатированные строки в результирующую строку.</span><span class="sxs-lookup"><span data-stu-id="4549f-144">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="4549f-145">Первая была значением даты и времени, при этом допустимой была только дата.</span><span class="sxs-lookup"><span data-stu-id="4549f-145">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="4549f-146">Вторая была ценой, в которой отсутствовала единица измерения валюты.</span><span class="sxs-lookup"><span data-stu-id="4549f-146">The second was a price that did not indicate its unit of currency.</span></span> <span data-ttu-id="4549f-147">Обе эти проблемы легко решить.</span><span class="sxs-lookup"><span data-stu-id="4549f-147">Both issues are easy to address.</span></span> <span data-ttu-id="4549f-148">Интерполированные выражения могут включать *строки формата*, управляющие форматированием определенных типов.</span><span class="sxs-lookup"><span data-stu-id="4549f-148">Interpolated expressions can include *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="4549f-149">Измените вызов `Console.WriteLine` из предыдущего примера, включив в него описатель формата для полей даты и цены, как показано в следующей строке:</span><span class="sxs-lookup"><span data-stu-id="4549f-149">Modify the call to `Console.WriteLine` from the previous example to include the format specifier for the date and price fields as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```
    
<span data-ttu-id="4549f-150">Задайте строку формата, указав ее после интерполированного выражения через точку с запятой.</span><span class="sxs-lookup"><span data-stu-id="4549f-150">You specify a format string by following the interpolated expression with a colon and the format string.</span></span> <span data-ttu-id="4549f-151">"d" — это [стандартная строка формата для даты и времени](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier), представляющая краткий формат.</span><span class="sxs-lookup"><span data-stu-id="4549f-151">"d" is a [standard date and time format string](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="4549f-152">"C2" — это [стандартная строка числового формата](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier), представляющая число в виде денежной единицы с точностью два знака после запятой.</span><span class="sxs-lookup"><span data-stu-id="4549f-152">"C2" is a  [standard numeric format string](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="4549f-153">Некоторые типы в библиотеках .NET Standard поддерживают предопределенный набор строк формата.</span><span class="sxs-lookup"><span data-stu-id="4549f-153">A number of types in the .NET Standard libraries support a predefined set of format strings.</span></span> <span data-ttu-id="4549f-154">К ним относятся все числовые типы, а также типы даты и времени.</span><span class="sxs-lookup"><span data-stu-id="4549f-154">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="4549f-155">Полный список типов, поддерживающих строки формата, см. в разделе [Строки формата и типы библиотек классов .NET](../../standard/base-types/formatting-types.md#stringRef) статьи [Типы форматирования в .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="4549f-155">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span> <span data-ttu-id="4549f-156">Любой тип может поддерживать набор строк формата, кроме того, можно разрабатывать расширения пользовательского форматирования для существующих типов.</span><span class="sxs-lookup"><span data-stu-id="4549f-156">Any type can support a set of format strings, and you can also develop custom formatting extensions that provide custom formatting for existing types.</span></span> <span data-ttu-id="4549f-157">Сведения о пользовательском форматировании n посредством реализации <xref:System.ICustomFormatter> см. в разделе [Настраиваемое форматирование с использованием интерфейса ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) статьи [Типы форматирования в .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="4549f-157">For information on custom formatting by providing an <xref:System.ICustomFormatter> implementation, see [Custom Formatting with ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="4549f-158">Попробуйте изменить строки формата в текстовом редакторе, возвращаясь в программу после каждого изменения, чтобы узнать, как они влияют на форматирование даты и времени, а также числового значения.</span><span class="sxs-lookup"><span data-stu-id="4549f-158">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="4549f-159">Измените "d" в `{date:d}` на "t" (чтобы отобразить краткий формат времени), "y" (чтобы отобразить год и месяц) и "yyyy" (чтобы отобразить год в виде четырехзначного числа).</span><span class="sxs-lookup"><span data-stu-id="4549f-159">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="4549f-160">Измените "C2" в `{price:C2}` на "e" (для экспоненциального представления) и "F3" (чтобы получить числовое значение с тремя знаками после запятой).</span><span class="sxs-lookup"><span data-stu-id="4549f-160">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="4549f-161">Кроме форматирования, вы можете управлять шириной поля и выравниванием для строк, возвращаемых интерполированным выражением.</span><span class="sxs-lookup"><span data-stu-id="4549f-161">In addition to controlling formatting, you can also control the field width and alignment of the strings returned by an interpolated expression.</span></span> <span data-ttu-id="4549f-162">В следующем разделе вы научитесь это делать.</span><span class="sxs-lookup"><span data-stu-id="4549f-162">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="4549f-163">Управление шириной поля и выравниванием для интерполированных выражений</span><span class="sxs-lookup"><span data-stu-id="4549f-163">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="4549f-164">Как правило, когда строка, возвращаемая интерполированным выражением, включается в результирующую строку, в ней нет начальных или конечных пробелов.</span><span class="sxs-lookup"><span data-stu-id="4549f-164">Ordinarily, when the string returned by an interpolated expression is included in a result string, it has no leading or trailing spaces.</span></span> <span data-ttu-id="4549f-165">Специально для экземпляров, в которых вы работаете с набором данных, интерполированные выражения позволяют задать ширину поля и его выравнивание.</span><span class="sxs-lookup"><span data-stu-id="4549f-165">Particularly for instances in which you are working with a set of data, interpolated expressions let you specify a field width and its alignment.</span></span> <span data-ttu-id="4549f-166">Чтобы увидеть это, замените весь код в текстовом редакторе следующим кодом, а затем введите `console run` для выполнения программы:</span><span class="sxs-lookup"><span data-stu-id="4549f-166">To see this, replace all the code in your text editor with the following code, then type `console run` to execute the program:</span></span>
    
```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>();
      titles.Add("Doyle, Arthur Conan", "Hound of the Baskervilles, The");
      titles.Add("London, Jack", "Call of the Wild, The");
      titles.Add("Shakespeare, William", "Tempest, The");

      Console.WriteLine("Author and Title List");
      Console.WriteLine($"\n{"Author",-25}    {"Title",30}\n");
      foreach (var title in titles)
         Console.WriteLine($"{title.Key,-25}     {title.Value,30}");
   }
}
```
    
<span data-ttu-id="4549f-167">Имена авторов выровнены по левому краю, а названия их произведений — по правому.</span><span class="sxs-lookup"><span data-stu-id="4549f-167">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="4549f-168">Вы можете указать выравнивание, добавив запятую (",") после выражения и назначив ширину поля.</span><span class="sxs-lookup"><span data-stu-id="4549f-168">You specify the alignment by adding a comma (",") after the expression and designating the field width.</span></span> <span data-ttu-id="4549f-169">Если ширина поля является положительным числом, то поле выравнивается по правому краю:</span><span class="sxs-lookup"><span data-stu-id="4549f-169">If the field width is a positive number, the field is right-aligned:</span></span>

```text
{expression, width}
```

<span data-ttu-id="4549f-170">Если ширина поля является отрицательным числом, то поле выравнивается по левому краю:</span><span class="sxs-lookup"><span data-stu-id="4549f-170">If the field width is a negative number, the field is left-aligned:</span></span>

```text
{expression, -width}
```

<span data-ttu-id="4549f-171">Попробуйте удалить знаки "минус" из интерполированных выражений `{"Author",-25}` и `{title.Key,-25}`, а затем снова запустите пример, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="4549f-171">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` interpolated expressions and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"\n{"Author",25}    {"Title",30}\n");
foreach (var title in titles)
   Console.WriteLine($"{title.Key,25}     {title.Value,30}");
```

<span data-ttu-id="4549f-172">На этот раз сведения об авторе выровнены по правому краю.</span><span class="sxs-lookup"><span data-stu-id="4549f-172">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="4549f-173">Вы можете совмещать ширину поля и строку формата в одном интерполированном выражении.</span><span class="sxs-lookup"><span data-stu-id="4549f-173">You can combine a field width and a format string in a single interpolated expression.</span></span> <span data-ttu-id="4549f-174">Сначала идет ширина поля, за которой следует двоеточие, а затем — строка формата.</span><span class="sxs-lookup"><span data-stu-id="4549f-174">The field width comes first, followed by a colon and the format string.</span></span> <span data-ttu-id="4549f-175">Замените весь код внутри метода `Main` приведенным ниже кодом, который отображает три отформатированные строки с заданной шириной поля.</span><span class="sxs-lookup"><span data-stu-id="4549f-175">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="4549f-176">Запустите программу, введя команду `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="4549f-176">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"{DateTime.Now,-20:d} Hour {DateTime.Now,-10:HH} {1063.342,15:N2} feet");
```
<span data-ttu-id="4549f-177">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4549f-177">The output looks something like the following:</span></span>

```console
1/11/2018            Hour 09                1,063.34 feet
```

<span data-ttu-id="4549f-178">Итак, вы закончили работу с кратким руководством по интерполированным строкам.</span><span class="sxs-lookup"><span data-stu-id="4549f-178">You've completed the interpolated strings quickstart.</span></span> 
    
<span data-ttu-id="4549f-179">Теперь вы можете выполнить руководство [Массивы и коллекции](arrays-and-collections.md) в своей среде разработки.</span><span class="sxs-lookup"><span data-stu-id="4549f-179">You can continue with the [Arrays and collections](arrays-and-collections.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="4549f-180">Дополнительные сведения о работе с интерполированными строками см. в разделе [Интерполированные строки](../language-reference/keywords/interpolated-strings.md) справочника по C#.</span><span class="sxs-lookup"><span data-stu-id="4549f-180">You can learn more about working with interpolated strings in the [Interpolated Strings](../language-reference/keywords/interpolated-strings.md) topic in the C# Reference.</span></span>

