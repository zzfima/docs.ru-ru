---
title: "Краткое руководство по работе с коллекциями с использованием C#"
description: "Изучите C# на примере коллекции списков в этом кратком руководстве."
keywords: C#, Get Started, tutorial, collections, List
author: billwagner
ms.author: wiwagn
ms.date: 10/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 6f559c7a3290e7db2266e10ec792c283394fb904
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2017
---
# <a name="c-quick-start-collections"></a><span data-ttu-id="7108d-104">Краткое руководство по C#: коллекции</span><span class="sxs-lookup"><span data-stu-id="7108d-104">C# Quick start: Collections</span></span> #

<span data-ttu-id="7108d-105">Это краткое руководство содержит общие сведения о языке C# и классе <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="7108d-105">This quick start provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

<span data-ttu-id="7108d-106">Для работы с этим кратким руководством вам потребуется компьютер, который можно использовать для разработки.</span><span class="sxs-lookup"><span data-stu-id="7108d-106">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="7108d-107">В руководстве по [началу работы с .NET за 10 минут](https://www.microsoft.com/net/core) содержатся инструкции по настройке локальной среды разработки на компьютерах Mac, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="7108d-107">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="7108d-108">Краткий обзор команд, которые будут использоваться, и ссылки на дополнительные сведения представлены в [вводной статье к руководствам по локальным средам](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7108d-108">A quick overview of the commands you'll use is in the [introduction to the local quick starts](local-environment.md) with links to more details.</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="7108d-109">Пример простого списка</span><span class="sxs-lookup"><span data-stu-id="7108d-109">A basic list example.</span></span>

<span data-ttu-id="7108d-110">Создайте каталог с именем **list-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="7108d-110">Create a directory named **list-quickstart**.</span></span> <span data-ttu-id="7108d-111">Откройте этот каталог и выполните команду `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="7108d-111">Make that the current directory and run `dotnet new console`.</span></span>

> [!NOTE]
> <span data-ttu-id="7108d-112">Если вы выполнили инструкции из руководства по [началу работы с .NET за 10 минут](https://www.microsoft.com/net), вы можете продолжать использовать только что созданное приложение myApp.</span><span class="sxs-lookup"><span data-stu-id="7108d-112">If you just completed [Get started with .NET in 10 minutes](https://www.microsoft.com/net), you can keep using the myApp application that you just created.</span></span>
 
<span data-ttu-id="7108d-113">Откройте **Program.cs** в любом редакторе и замените существующий код следующим:</span><span class="sxs-lookup"><span data-stu-id="7108d-113">Open **Program.cs** in your favorite editor, and replace the existing code with the following:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

<span data-ttu-id="7108d-114">Замените `<name>` собственным именем.</span><span class="sxs-lookup"><span data-stu-id="7108d-114">Replace `<name>` with your name.</span></span> <span data-ttu-id="7108d-115">Сохраните **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="7108d-115">Save **Program.cs**.</span></span> <span data-ttu-id="7108d-116">Введите в окне консоли команду `dotnet run` для тестирования.</span><span class="sxs-lookup"><span data-stu-id="7108d-116">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="7108d-117">Вы создали список строк, добавили в него три имени и вывели имена с преобразованием всех букв в прописные.</span><span class="sxs-lookup"><span data-stu-id="7108d-117">You've just created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="7108d-118">Для циклического прохода по списку используются основные принципы, которые вы изучили в предыдущих кратких руководствах.</span><span class="sxs-lookup"><span data-stu-id="7108d-118">You're using concepts that you've learned in earlier quick starts to loop through the list.</span></span>

<span data-ttu-id="7108d-119">В коде для отображения имен используются **интерполированные строки**.</span><span class="sxs-lookup"><span data-stu-id="7108d-119">The code to display names makes use of **interpolated strings**.</span></span>  <span data-ttu-id="7108d-120">Если перед `string` добавить символ `$`, код C# можно внедрять в объявление строки.</span><span class="sxs-lookup"><span data-stu-id="7108d-120">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="7108d-121">Фактическая строка заменяет код C# генерируемым значением.</span><span class="sxs-lookup"><span data-stu-id="7108d-121">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="7108d-122">В этом примере она заменяет `{name.ToUpper()}` именами, буквы каждого из которых преобразованы в прописные, так как вызван метод <xref:System.String.ToUpper%2A>.</span><span class="sxs-lookup"><span data-stu-id="7108d-122">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="7108d-123">Продолжим изучение.</span><span class="sxs-lookup"><span data-stu-id="7108d-123">Let's keep exploring.</span></span>
    
## <a name="modify-list-contents"></a><span data-ttu-id="7108d-124">Изменение содержимого списка</span><span class="sxs-lookup"><span data-stu-id="7108d-124">Modify list contents</span></span>

<span data-ttu-id="7108d-125">В созданной коллекции используется тип <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="7108d-125">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="7108d-126">При применении такого типа сохраняются последовательности элементов.</span><span class="sxs-lookup"><span data-stu-id="7108d-126">This type stores sequences of elements.</span></span> <span data-ttu-id="7108d-127">Тип элементов указывается в угловых скобках.</span><span class="sxs-lookup"><span data-stu-id="7108d-127">You specify the type of the elements between the angle brackets.</span></span>
    
<span data-ttu-id="7108d-128">Важный аспект типа <xref:System.Collections.Generic.List%601> — возможность увеличения или уменьшения, что позволяет добавлять или удалять элементы.</span><span class="sxs-lookup"><span data-stu-id="7108d-128">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="7108d-129">Добавьте следующий код в метод `Main` перед закрывающей фигурной скобкой `}`:</span><span class="sxs-lookup"><span data-stu-id="7108d-129">Add this code before the closing `}` in the `Main` method:</span></span>

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="7108d-130">В конец списка добавлены еще два имени.</span><span class="sxs-lookup"><span data-stu-id="7108d-130">You've added two more names to the end of the list.</span></span> <span data-ttu-id="7108d-131">При этом одно имя удалено.</span><span class="sxs-lookup"><span data-stu-id="7108d-131">You've also removed one as well.</span></span> <span data-ttu-id="7108d-132">Сохраните файл и введите `dotnet run` для тестирования.</span><span class="sxs-lookup"><span data-stu-id="7108d-132">Save the file, and type `dotnet run` to try it.</span></span>
    
<span data-ttu-id="7108d-133"><xref:System.Collections.Generic.List%601> позволяет добавлять ссылки на отдельные элементы по **индексу**.</span><span class="sxs-lookup"><span data-stu-id="7108d-133">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="7108d-134">Поместите индекс между токенами `[` и `]` после имени списка.</span><span class="sxs-lookup"><span data-stu-id="7108d-134">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="7108d-135">Для первого индекса в C# используется значение 0.</span><span class="sxs-lookup"><span data-stu-id="7108d-135">C# uses 0 for the first index.</span></span> <span data-ttu-id="7108d-136">Добавьте следующий код сразу после добавленного фрагмента и протестируйте его:</span><span class="sxs-lookup"><span data-stu-id="7108d-136">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="7108d-137">Доступ к индексу за пределами списка получить невозможно.</span><span class="sxs-lookup"><span data-stu-id="7108d-137">You cannot access an index beyond the end of the list.</span></span> <span data-ttu-id="7108d-138">Помните, что индексы начинаются с 0, поэтому максимальный допустимый индекс меньше, чем число элементов в списке.</span><span class="sxs-lookup"><span data-stu-id="7108d-138">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="7108d-139">Вы можете проверить, как долго в списке используется свойство <xref:System.Collections.Generic.List%601.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="7108d-139">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="7108d-140">Добавьте следующий код в конец метода Main:</span><span class="sxs-lookup"><span data-stu-id="7108d-140">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="7108d-141">Сохраните файл и еще раз введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="7108d-141">Save the file, and type `dotnet run` again to see the results.</span></span>    

## <a name="search-and-sort-lists"></a><span data-ttu-id="7108d-142">Поиск по спискам и их сортировка</span><span class="sxs-lookup"><span data-stu-id="7108d-142">Search and sort lists</span></span>
<span data-ttu-id="7108d-143">В наших примерах используются сравнительно небольшие списки. Но приложения часто создают списки с гораздо большим количеством элементов, иногда они исчисляются в тысячах.</span><span class="sxs-lookup"><span data-stu-id="7108d-143">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="7108d-144">Чтобы найти элементы в таких больших коллекциях, необходимо выполнить поиск различных элементов по списку.</span><span class="sxs-lookup"><span data-stu-id="7108d-144">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="7108d-145">Метод <xref:System.Collections.Generic.List%601.IndexOf%2A> выполняет поиск элемента и возвращает его индекс.</span><span class="sxs-lookup"><span data-stu-id="7108d-145">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="7108d-146">Добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="7108d-146">Add this code to the bottom of your `Main` method:</span></span>

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
    
}
```

<span data-ttu-id="7108d-147">Кроме того, можно сортировать элементы в списке.</span><span class="sxs-lookup"><span data-stu-id="7108d-147">The items in your list can be sorted as well.</span></span> <span data-ttu-id="7108d-148">Метод <xref:System.Collections.Generic.List%601.Sort%2A> сортирует все элементы списка в обычном порядке (при использовании строк — в алфавитном порядке).</span><span class="sxs-lookup"><span data-stu-id="7108d-148">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically in the case of strings).</span></span> <span data-ttu-id="7108d-149">Добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="7108d-149">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="7108d-150">Сохраните файл и введите `dotnet run`, чтобы протестировать последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="7108d-150">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="7108d-151">Прежде чем перейти к следующему разделу, переместим текущий код в отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="7108d-151">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="7108d-152">Это упростит начало работы с новым примером.</span><span class="sxs-lookup"><span data-stu-id="7108d-152">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="7108d-153">Переименуйте метод `Main` в `WorkingWithStrings` и запишите новый метод `Main`, который вызывает `WorkingWithStrings`.</span><span class="sxs-lookup"><span data-stu-id="7108d-153">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="7108d-154">В результате ваш код должен выглядеть примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7108d-154">When you have finished, your code should look like this:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        public static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            Console.WriteLine($"The name {names[index]} is at index {index}");

            var notFound = names.IndexOf("Not Found");
            Console.WriteLine($"When an item is not found, IndexOf returns {notFound}");

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a><span data-ttu-id="7108d-155">Списки других типов</span><span class="sxs-lookup"><span data-stu-id="7108d-155">Lists of other types</span></span>

<span data-ttu-id="7108d-156">Вы уже использовали в списках тип `string`.</span><span class="sxs-lookup"><span data-stu-id="7108d-156">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="7108d-157">Создадим <xref:System.Collections.Generic.List%601> с использованием другого типа.</span><span class="sxs-lookup"><span data-stu-id="7108d-157">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="7108d-158">Сначала создадим набор чисел.</span><span class="sxs-lookup"><span data-stu-id="7108d-158">Let's build a set of numbers.</span></span> 

<span data-ttu-id="7108d-159">Добавьте следующий код в конец нового метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="7108d-159">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="7108d-160">Будет создан список целых чисел. Для первых двух целых чисел будет задано значение 1.</span><span class="sxs-lookup"><span data-stu-id="7108d-160">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="7108d-161">Это два первых значения *последовательности Фибоначчи*.</span><span class="sxs-lookup"><span data-stu-id="7108d-161">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="7108d-162">Каждое следующее число Фибоначчи — это сумма двух предыдущих чисел.</span><span class="sxs-lookup"><span data-stu-id="7108d-162">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="7108d-163">Добавьте этот код:</span><span class="sxs-lookup"><span data-stu-id="7108d-163">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="7108d-164">Сохраните файл и введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="7108d-164">Save the file and type `dotnet run` to see the results.</span></span> 

> [!TIP]
> <span data-ttu-id="7108d-165">Для задач этого раздела вы можете закомментировать код, который вызывает `WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="7108d-165">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="7108d-166">Просто поместите два символа `/` перед вызовом. Например: `// WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="7108d-166">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span> 

## <a name="challenge"></a><span data-ttu-id="7108d-167">Задача</span><span class="sxs-lookup"><span data-stu-id="7108d-167">Challenge</span></span>
<span data-ttu-id="7108d-168">Попробуйте объединить некоторые идеи из этого и предыдущих занятий.</span><span class="sxs-lookup"><span data-stu-id="7108d-168">See if you can put together some of the concepts from this and earlier lessons.</span></span> <span data-ttu-id="7108d-169">Расширьте код с числами Фибоначчи, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="7108d-169">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="7108d-170">Попробуйте написать код для создания первых 20 чисел в последовательности.</span><span class="sxs-lookup"><span data-stu-id="7108d-170">Try to write the code to generate the first 20 numbers in the sequence.</span></span> <span data-ttu-id="7108d-171">Подсказка: 20-е число Фибоначчи — 6765.</span><span class="sxs-lookup"><span data-stu-id="7108d-171">(As a hint, the 20th Fibonacci number is 6765.)</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="7108d-172">Выполнение задачи</span><span class="sxs-lookup"><span data-stu-id="7108d-172">Complete challenge</span></span>

<span data-ttu-id="7108d-173">Пример решения можно [просмотреть в готовом примере кода на GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs#L13-L23).</span><span class="sxs-lookup"><span data-stu-id="7108d-173">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs#L13-L23)</span></span>

<span data-ttu-id="7108d-174">При каждой итерации цикла суммируются два последних целых числа в списке. Полученное значение добавляется в список.</span><span class="sxs-lookup"><span data-stu-id="7108d-174">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="7108d-175">Цикл повторяется, пока в список не будут добавлены 20 элементов.</span><span class="sxs-lookup"><span data-stu-id="7108d-175">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="7108d-176">Поздравляем! Вы выполнили задачи из краткого руководства по спискам.</span><span class="sxs-lookup"><span data-stu-id="7108d-176">Congratulations, you've completed the list quick start.</span></span> <span data-ttu-id="7108d-177">Можете продолжить обучение в своей среде разработки и перейти к краткому руководству с [общими сведениями о классах](introduction-to-classes.md).</span><span class="sxs-lookup"><span data-stu-id="7108d-177">You can continue with the [Introduction to classes](introduction-to-classes.md) quick start in your own development environment.</span></span>

<span data-ttu-id="7108d-178">Дополнительные сведения о работе с типом `List` см. в разделе о [коллекциях](../../standard/collections/index.md) [руководства по .NET](../../standard/index.md).</span><span class="sxs-lookup"><span data-stu-id="7108d-178">You can learn more about working with the `List` type in the [.NET Guide](../../standard/index.md) topic on [collections](../../standard/collections/index.md).</span></span> <span data-ttu-id="7108d-179">Также в нем описаны многие другие типы коллекций.</span><span class="sxs-lookup"><span data-stu-id="7108d-179">You'll also learn about many other collection types.</span></span>
