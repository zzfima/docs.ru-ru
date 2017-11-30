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
ms.openlocfilehash: 228a9dd88d0a511492ccb8b70e0231278969acbe
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2017
---
# <a name="c-quick-start-collections"></a><span data-ttu-id="3d4ac-104">Краткое руководство по C#: коллекции</span><span class="sxs-lookup"><span data-stu-id="3d4ac-104">C# Quick start: Collections</span></span> #

<span data-ttu-id="3d4ac-105">В этом кратком руководстве представляет собой введение в языке C# и основы <xref:System.Collections.Generic.List%601> класса.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-105">This quick start provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

<span data-ttu-id="3d4ac-106">В этом кратком руководстве предполагается, что вы машины, которые можно использовать для разработки приложений.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-106">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="3d4ac-107">В разделе .NET [приступить к работе в течение 10 минут](https://www.microsoft.com/net/core) содержит инструкции по настройке в локальной среде разработки на Mac, ПК или Linux.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-107">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="3d4ac-108">Пример для базового списка.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-108">A basic list example.</span></span>

<span data-ttu-id="3d4ac-109">Создайте каталог с именем **list-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-109">Create a directory named **list-quickstart**.</span></span> <span data-ttu-id="3d4ac-110">Откройте этот каталог и выполните команду `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-110">Make that the current directory and run `dotnet new console`.</span></span>

> [!NOTE]
> <span data-ttu-id="3d4ac-111">Если вы выполнили [начало работы с .NET через 10 минут](https://www.microsoft.com/net), вы можете продолжать использовать приложения myApp, которую вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-111">If you just completed [Get started with .NET in 10 minutes](https://www.microsoft.com/net), you can keep using the myApp application that you just created.</span></span>
 
<span data-ttu-id="3d4ac-112">Откройте **Program.cs** в любом редакторе и замените существующий код следующим:</span><span class="sxs-lookup"><span data-stu-id="3d4ac-112">Open **Program.cs** in your favorite editor, and replace the existing code with the following:</span></span>

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

<span data-ttu-id="3d4ac-113">Замените `<name>` собственным именем.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-113">Replace `<name>` with your name.</span></span> <span data-ttu-id="3d4ac-114">Сохраните **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-114">Save **Program.cs**.</span></span> <span data-ttu-id="3d4ac-115">Введите в окне консоли команду `dotnet run` для тестирования.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-115">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="3d4ac-116">Вы создали список строк, добавили в него три имени и вывели имена с преобразованием всех букв в прописные.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-116">You've just created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="3d4ac-117">Для циклического прохода по списку используются основные принципы, которые вы изучили в предыдущих кратких руководствах.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-117">You're using concepts that you've learned in earlier quick starts to loop through the list.</span></span>

<span data-ttu-id="3d4ac-118">В коде для отображения имен используются **интерполированные строки**.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-118">The code to display names makes use of **interpolated strings**.</span></span>  <span data-ttu-id="3d4ac-119">Если перед `string` добавить символ `$`, код C# можно внедрять в объявление строки.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-119">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="3d4ac-120">Фактическая строка заменяет код C# генерируемым значением.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-120">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="3d4ac-121">В этом примере она заменяет `{name.ToUpper()}` именами, буквы каждого из которых преобразованы в прописные, так как вызван метод <xref:System.String.ToUpper%2A>.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-121">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="3d4ac-122">Продолжим изучение.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-122">Let's keep exploring.</span></span>
    
## <a name="modify-list-contents"></a><span data-ttu-id="3d4ac-123">Изменение содержимого списка</span><span class="sxs-lookup"><span data-stu-id="3d4ac-123">Modify list contents</span></span>

<span data-ttu-id="3d4ac-124">В созданной коллекции используется тип <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-124">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="3d4ac-125">При применении такого типа сохраняются последовательности элементов.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-125">This type stores sequences of elements.</span></span> <span data-ttu-id="3d4ac-126">Тип элементов указывается в угловых скобках.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-126">You specify the type of the elements between the angle brackets.</span></span>
    
<span data-ttu-id="3d4ac-127">Важный аспект типа <xref:System.Collections.Generic.List%601> — возможность увеличения или уменьшения, что позволяет добавлять или удалять элементы.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-127">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="3d4ac-128">Добавьте следующий код в метод `Main` перед закрывающей фигурной скобкой `}`:</span><span class="sxs-lookup"><span data-stu-id="3d4ac-128">Add this code before the closing `}` in the `Main` method:</span></span>

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

<span data-ttu-id="3d4ac-129">В конец списка добавлены еще два имени.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-129">You've added two more names to the end of the list.</span></span> <span data-ttu-id="3d4ac-130">При этом одно имя удалено.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-130">You've also removed one as well.</span></span> <span data-ttu-id="3d4ac-131">Сохраните файл и введите `dotnet run` для тестирования.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-131">Save the file, and type `dotnet run` to try it.</span></span>
    
<span data-ttu-id="3d4ac-132"><xref:System.Collections.Generic.List%601> позволяет добавлять ссылки на отдельные элементы по **индексу**.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-132">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="3d4ac-133">Поместите индекс между токенами `[` и `]` после имени списка.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-133">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="3d4ac-134">Для первого индекса в C# используется значение 0.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-134">C# uses 0 for the first index.</span></span> <span data-ttu-id="3d4ac-135">Добавьте следующий код сразу после добавленного фрагмента и протестируйте его:</span><span class="sxs-lookup"><span data-stu-id="3d4ac-135">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="3d4ac-136">Доступ к индексу за пределами списка получить невозможно.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-136">You cannot access an index beyond the end of the list.</span></span> <span data-ttu-id="3d4ac-137">Помните, что индексы начинаются с 0, поэтому максимальный допустимый индекс меньше, чем число элементов в списке.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-137">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="3d4ac-138">Вы можете проверить, как долго в списке используется свойство <xref:System.Collections.Generic.List%601.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-138">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="3d4ac-139">Добавьте следующий код в конец метода Main:</span><span class="sxs-lookup"><span data-stu-id="3d4ac-139">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="3d4ac-140">Сохраните файл и еще раз введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-140">Save the file, and type `dotnet run` again to see the results.</span></span>    

## <a name="search-and-sort-lists"></a><span data-ttu-id="3d4ac-141">Поиск по спискам и их сортировка</span><span class="sxs-lookup"><span data-stu-id="3d4ac-141">Search and sort lists</span></span>
<span data-ttu-id="3d4ac-142">В наших примерах используются сравнительно небольшие списки. Но приложения часто создают списки с гораздо большим количеством элементов, иногда они исчисляются в тысячах.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-142">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="3d4ac-143">Чтобы найти элементы в таких больших коллекциях, необходимо выполнить поиск различных элементов по списку.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-143">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="3d4ac-144">Метод <xref:System.Collections.Generic.List%601.IndexOf%2A> выполняет поиск элемента и возвращает его индекс.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-144">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="3d4ac-145">Добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="3d4ac-145">Add this code to the bottom of your `Main` method:</span></span>

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

<span data-ttu-id="3d4ac-146">Кроме того, можно сортировать элементы в списке.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-146">The items in your list can be sorted as well.</span></span> <span data-ttu-id="3d4ac-147">Метод <xref:System.Collections.Generic.List%601.Sort%2A> сортирует все элементы списка в обычном порядке (при использовании строк — в алфавитном порядке).</span><span class="sxs-lookup"><span data-stu-id="3d4ac-147">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically in the case of strings).</span></span> <span data-ttu-id="3d4ac-148">Добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="3d4ac-148">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="3d4ac-149">Сохраните файл и введите `dotnet run`, чтобы протестировать последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-149">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="3d4ac-150">Прежде чем перейти к следующему разделу, переместим текущий код в отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-150">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="3d4ac-151">Это упростит начало работы с новым примером.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-151">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="3d4ac-152">Переименуйте метод `Main` в `WorkingWithStrings` и запишите новый метод `Main`, который вызывает `WorkingWithStrings`.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-152">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="3d4ac-153">В результате ваш код должен выглядеть примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3d4ac-153">When you have finished, your code should look like this:</span></span>

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

## <a name="lists-of-other-types"></a><span data-ttu-id="3d4ac-154">Списки других типов</span><span class="sxs-lookup"><span data-stu-id="3d4ac-154">Lists of other types</span></span>

<span data-ttu-id="3d4ac-155">Вы уже использовали в списках тип `string`.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-155">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="3d4ac-156">Создадим <xref:System.Collections.Generic.List%601> с использованием другого типа.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-156">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="3d4ac-157">Сначала создадим набор чисел.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-157">Let's build a set of numbers.</span></span> 

<span data-ttu-id="3d4ac-158">Добавьте следующий код в конец нового метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="3d4ac-158">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="3d4ac-159">Будет создан список целых чисел. Для первых двух целых чисел будет задано значение 1.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-159">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="3d4ac-160">Это два первых значения *последовательности Фибоначчи*.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-160">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="3d4ac-161">Каждое следующее число Фибоначчи — это сумма двух предыдущих чисел.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-161">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="3d4ac-162">Добавьте этот код:</span><span class="sxs-lookup"><span data-stu-id="3d4ac-162">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="3d4ac-163">Сохраните файл и введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-163">Save the file and type `dotnet run` to see the results.</span></span> 

> [!TIP]
> <span data-ttu-id="3d4ac-164">Для задач этого раздела вы можете закомментировать код, который вызывает `WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-164">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="3d4ac-165">Просто поместите два символа `/` перед вызовом. Например: `// WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-165">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span> 

## <a name="challenge"></a><span data-ttu-id="3d4ac-166">Задача</span><span class="sxs-lookup"><span data-stu-id="3d4ac-166">Challenge</span></span>
<span data-ttu-id="3d4ac-167">Попробуйте объединить некоторые задания из этого и предыдущих занятий.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-167">See if you can put together some of the lessons from this and earlier lessons.</span></span> <span data-ttu-id="3d4ac-168">Расширьте код с числами Фибоначчи, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-168">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="3d4ac-169">Напишите и протестируйте код для создания первых 20 чисел в последовательности.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-169">Try and write the code to generate the first 20 numbers in the sequence.</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="3d4ac-170">Выполнение задачи</span><span class="sxs-lookup"><span data-stu-id="3d4ac-170">Complete challenge</span></span>

<span data-ttu-id="3d4ac-171">Пример решения можно [просмотреть в готовом примере кода на GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs#L13-L23).</span><span class="sxs-lookup"><span data-stu-id="3d4ac-171">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs#L13-L23)</span></span>

<span data-ttu-id="3d4ac-172">При каждой итерации цикла суммируются два последних целых числа в списке. Полученное значение добавляется в список.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-172">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="3d4ac-173">Цикл повторяется, пока в список не будут добавлены 20 элементов.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-173">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="3d4ac-174">Поздравляем, вы выполнили краткого списка.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-174">Congratulations, you've completed the list quick start.</span></span> <span data-ttu-id="3d4ac-175">Можно продолжить [Общие сведения о классах](introduction-to-classes.md) быстрый запуск в среде разработки.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-175">You can continue with the [Introduction to classes](introduction-to-classes.md) quick start in your own development environment.</span></span>

<span data-ttu-id="3d4ac-176">Дополнительные сведения о работе с типом `List` см. в разделе о [коллекциях](../../standard/collections/index.md) [руководства по .NET](../../standard/index.md).</span><span class="sxs-lookup"><span data-stu-id="3d4ac-176">You can learn more about working with the `List` type in the [.NET Guide](../../standard/index.md) topic on [collections](../../standard/collections/index.md).</span></span> <span data-ttu-id="3d4ac-177">Также в нем описаны многие другие типы коллекций.</span><span class="sxs-lookup"><span data-stu-id="3d4ac-177">You'll also learn about many other collection types.</span></span>
