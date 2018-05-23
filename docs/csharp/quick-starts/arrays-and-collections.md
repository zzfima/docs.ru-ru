---
title: Руководство по коллекциям. Краткие руководства по локальной разработке на C#
description: Это руководство по C# предоставляет для изучения примере коллекции списков.
ms.date: 10/13/2017
ms.custom: mvc
ms.openlocfilehash: 51e8ce47165cd4ce22a72ed78138b36d15a97156
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="c-quickstart-collections"></a><span data-ttu-id="c6933-103">Краткое руководство по C#: коллекции</span><span class="sxs-lookup"><span data-stu-id="c6933-103">C# Quickstart: Collections</span></span>

<span data-ttu-id="c6933-104">Это краткое руководство содержит общие сведения о языке C# и классе <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="c6933-104">This quickstart provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

<span data-ttu-id="c6933-105">Для работы с этим кратким руководством вам потребуется компьютер, который можно использовать для разработки.</span><span class="sxs-lookup"><span data-stu-id="c6933-105">This quickstart expects you to have a machine you can use for development.</span></span> <span data-ttu-id="c6933-106">В руководстве по [началу работы с .NET за 10 минут](https://www.microsoft.com/net/core) содержатся инструкции по настройке локальной среды разработки на компьютерах Mac, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="c6933-106">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="c6933-107">Краткий обзор команд, которые будут здесь использоваться, и ссылки на дополнительные сведения представлены в [вводной статье к руководствам по локальной разработке](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c6933-107">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="c6933-108">Пример простого списка</span><span class="sxs-lookup"><span data-stu-id="c6933-108">A basic list example</span></span>

<span data-ttu-id="c6933-109">Создайте каталог с именем **list-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="c6933-109">Create a directory named **list-quickstart**.</span></span> <span data-ttu-id="c6933-110">Откройте этот каталог и выполните команду `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="c6933-110">Make that the current directory and run `dotnet new console`.</span></span>

> [!NOTE]
> <span data-ttu-id="c6933-111">Если вы выполнили инструкции из руководства по [началу работы с .NET за 10 минут](https://www.microsoft.com/net), вы можете продолжать использовать только что созданное приложение myApp.</span><span class="sxs-lookup"><span data-stu-id="c6933-111">If you just completed [Get started with .NET in 10 minutes](https://www.microsoft.com/net), you can keep using the myApp application that you just created.</span></span>

<span data-ttu-id="c6933-112">Откройте **Program.cs** в любом редакторе и замените существующий код следующим:</span><span class="sxs-lookup"><span data-stu-id="c6933-112">Open **Program.cs** in your favorite editor, and replace the existing code with the following:</span></span>

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

<span data-ttu-id="c6933-113">Замените `<name>` собственным именем.</span><span class="sxs-lookup"><span data-stu-id="c6933-113">Replace `<name>` with your name.</span></span> <span data-ttu-id="c6933-114">Сохраните **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="c6933-114">Save **Program.cs**.</span></span> <span data-ttu-id="c6933-115">Введите в окне консоли команду `dotnet run` для тестирования.</span><span class="sxs-lookup"><span data-stu-id="c6933-115">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="c6933-116">Вы создали список строк, добавили в него три имени и вывели имена с преобразованием всех букв в прописные.</span><span class="sxs-lookup"><span data-stu-id="c6933-116">You've just created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="c6933-117">Для циклического прохода по списку вы примените концепции, которые изучили в предыдущих кратких руководствах.</span><span class="sxs-lookup"><span data-stu-id="c6933-117">You're using concepts that you've learned in earlier quickstarts to loop through the list.</span></span>

<span data-ttu-id="c6933-118">В коде для отображения имен используется функция [интерполяции строк](../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="c6933-118">The code to display names makes use of the [string interpolation](../language-reference/tokens/interpolated.md) feature.</span></span>  <span data-ttu-id="c6933-119">Если перед `string` добавить символ `$`, код C# можно внедрять в объявление строки.</span><span class="sxs-lookup"><span data-stu-id="c6933-119">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="c6933-120">Фактическая строка заменяет код C# генерируемым значением.</span><span class="sxs-lookup"><span data-stu-id="c6933-120">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="c6933-121">В этом примере она заменяет `{name.ToUpper()}` именами, буквы каждого из которых преобразованы в прописные, так как вызван метод <xref:System.String.ToUpper%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6933-121">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="c6933-122">Продолжим изучение.</span><span class="sxs-lookup"><span data-stu-id="c6933-122">Let's keep exploring.</span></span>

## <a name="modify-list-contents"></a><span data-ttu-id="c6933-123">Изменение содержимого списка</span><span class="sxs-lookup"><span data-stu-id="c6933-123">Modify list contents</span></span>

<span data-ttu-id="c6933-124">В созданной коллекции используется тип <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="c6933-124">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="c6933-125">При применении такого типа сохраняются последовательности элементов.</span><span class="sxs-lookup"><span data-stu-id="c6933-125">This type stores sequences of elements.</span></span> <span data-ttu-id="c6933-126">Тип элементов указывается в угловых скобках.</span><span class="sxs-lookup"><span data-stu-id="c6933-126">You specify the type of the elements between the angle brackets.</span></span>

<span data-ttu-id="c6933-127">Важный аспект типа <xref:System.Collections.Generic.List%601> — возможность увеличения или уменьшения, что позволяет добавлять или удалять элементы.</span><span class="sxs-lookup"><span data-stu-id="c6933-127">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="c6933-128">Добавьте следующий код в метод `Main` перед закрывающей фигурной скобкой `}`:</span><span class="sxs-lookup"><span data-stu-id="c6933-128">Add this code before the closing `}` in the `Main` method:</span></span>

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

<span data-ttu-id="c6933-129">В конец списка добавлены еще два имени.</span><span class="sxs-lookup"><span data-stu-id="c6933-129">You've added two more names to the end of the list.</span></span> <span data-ttu-id="c6933-130">При этом одно имя удалено.</span><span class="sxs-lookup"><span data-stu-id="c6933-130">You've also removed one as well.</span></span> <span data-ttu-id="c6933-131">Сохраните файл и введите `dotnet run` для тестирования.</span><span class="sxs-lookup"><span data-stu-id="c6933-131">Save the file, and type `dotnet run` to try it.</span></span>

<span data-ttu-id="c6933-132"><xref:System.Collections.Generic.List%601> позволяет добавлять ссылки на отдельные элементы по **индексу**.</span><span class="sxs-lookup"><span data-stu-id="c6933-132">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="c6933-133">Поместите индекс между токенами `[` и `]` после имени списка.</span><span class="sxs-lookup"><span data-stu-id="c6933-133">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="c6933-134">Для первого индекса в C# используется значение 0.</span><span class="sxs-lookup"><span data-stu-id="c6933-134">C# uses 0 for the first index.</span></span> <span data-ttu-id="c6933-135">Добавьте следующий код сразу после добавленного фрагмента и протестируйте его:</span><span class="sxs-lookup"><span data-stu-id="c6933-135">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="c6933-136">Доступ к индексу за пределами списка получить невозможно.</span><span class="sxs-lookup"><span data-stu-id="c6933-136">You cannot access an index beyond the end of the list.</span></span> <span data-ttu-id="c6933-137">Помните, что индексы начинаются с 0, поэтому максимальный допустимый индекс меньше, чем число элементов в списке.</span><span class="sxs-lookup"><span data-stu-id="c6933-137">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="c6933-138">Вы можете проверить, как долго в списке используется свойство <xref:System.Collections.Generic.List%601.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6933-138">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="c6933-139">Добавьте следующий код в конец метода Main:</span><span class="sxs-lookup"><span data-stu-id="c6933-139">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="c6933-140">Сохраните файл и еще раз введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="c6933-140">Save the file, and type `dotnet run` again to see the results.</span></span>

## <a name="search-and-sort-lists"></a><span data-ttu-id="c6933-141">Поиск по спискам и их сортировка</span><span class="sxs-lookup"><span data-stu-id="c6933-141">Search and sort lists</span></span>

<span data-ttu-id="c6933-142">В наших примерах используются сравнительно небольшие списки. Но приложения часто создают списки с гораздо большим количеством элементов, иногда они исчисляются в тысячах.</span><span class="sxs-lookup"><span data-stu-id="c6933-142">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="c6933-143">Чтобы найти элементы в таких больших коллекциях, необходимо выполнить поиск различных элементов по списку.</span><span class="sxs-lookup"><span data-stu-id="c6933-143">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="c6933-144">Метод <xref:System.Collections.Generic.List%601.IndexOf%2A> выполняет поиск элемента и возвращает его индекс.</span><span class="sxs-lookup"><span data-stu-id="c6933-144">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="c6933-145">Добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="c6933-145">Add this code to the bottom of your `Main` method:</span></span>

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

<span data-ttu-id="c6933-146">Кроме того, можно сортировать элементы в списке.</span><span class="sxs-lookup"><span data-stu-id="c6933-146">The items in your list can be sorted as well.</span></span> <span data-ttu-id="c6933-147">Метод <xref:System.Collections.Generic.List%601.Sort%2A> сортирует все элементы списка в обычном порядке (при использовании строк — в алфавитном порядке).</span><span class="sxs-lookup"><span data-stu-id="c6933-147">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically in the case of strings).</span></span> <span data-ttu-id="c6933-148">Добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="c6933-148">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="c6933-149">Сохраните файл и введите `dotnet run`, чтобы протестировать последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="c6933-149">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="c6933-150">Прежде чем перейти к следующему разделу, переместим текущий код в отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="c6933-150">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="c6933-151">Это упростит начало работы с новым примером.</span><span class="sxs-lookup"><span data-stu-id="c6933-151">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="c6933-152">Переименуйте метод `Main` в `WorkingWithStrings` и запишите новый метод `Main`, который вызывает `WorkingWithStrings`.</span><span class="sxs-lookup"><span data-stu-id="c6933-152">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="c6933-153">В результате ваш код должен выглядеть примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c6933-153">When you have finished, your code should look like this:</span></span>

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

## <a name="lists-of-other-types"></a><span data-ttu-id="c6933-154">Списки других типов</span><span class="sxs-lookup"><span data-stu-id="c6933-154">Lists of other types</span></span>

<span data-ttu-id="c6933-155">Вы уже использовали в списках тип `string`.</span><span class="sxs-lookup"><span data-stu-id="c6933-155">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="c6933-156">Создадим <xref:System.Collections.Generic.List%601> с использованием другого типа.</span><span class="sxs-lookup"><span data-stu-id="c6933-156">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="c6933-157">Сначала создадим набор чисел.</span><span class="sxs-lookup"><span data-stu-id="c6933-157">Let's build a set of numbers.</span></span>

<span data-ttu-id="c6933-158">Добавьте следующий код в конец нового метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="c6933-158">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="c6933-159">Будет создан список целых чисел. Для первых двух целых чисел будет задано значение 1.</span><span class="sxs-lookup"><span data-stu-id="c6933-159">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="c6933-160">Это два первых значения *последовательности Фибоначчи*.</span><span class="sxs-lookup"><span data-stu-id="c6933-160">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="c6933-161">Каждое следующее число Фибоначчи — это сумма двух предыдущих чисел.</span><span class="sxs-lookup"><span data-stu-id="c6933-161">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="c6933-162">Добавьте этот код:</span><span class="sxs-lookup"><span data-stu-id="c6933-162">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="c6933-163">Сохраните файл и введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="c6933-163">Save the file and type `dotnet run` to see the results.</span></span>

> [!TIP]
> <span data-ttu-id="c6933-164">Для задач этого раздела вы можете закомментировать код, который вызывает `WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="c6933-164">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="c6933-165">Просто поместите два символа `/` перед вызовом. Например: `// WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="c6933-165">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span>

## <a name="challenge"></a><span data-ttu-id="c6933-166">Задача</span><span class="sxs-lookup"><span data-stu-id="c6933-166">Challenge</span></span>

<span data-ttu-id="c6933-167">Попробуйте объединить некоторые идеи из этого и предыдущих занятий.</span><span class="sxs-lookup"><span data-stu-id="c6933-167">See if you can put together some of the concepts from this and earlier lessons.</span></span> <span data-ttu-id="c6933-168">Расширьте код с числами Фибоначчи, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="c6933-168">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="c6933-169">Попробуйте написать код для создания первых 20 чисел в последовательности.</span><span class="sxs-lookup"><span data-stu-id="c6933-169">Try to write the code to generate the first 20 numbers in the sequence.</span></span> <span data-ttu-id="c6933-170">Подсказка: 20-е число Фибоначчи — 6765.</span><span class="sxs-lookup"><span data-stu-id="c6933-170">(As a hint, the 20th Fibonacci number is 6765.)</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="c6933-171">Выполнение задачи</span><span class="sxs-lookup"><span data-stu-id="c6933-171">Complete challenge</span></span>

<span data-ttu-id="c6933-172">Пример решения можно [просмотреть в готовом примере кода на GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23).</span><span class="sxs-lookup"><span data-stu-id="c6933-172">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23)</span></span>

<span data-ttu-id="c6933-173">При каждой итерации цикла суммируются два последних целых числа в списке. Полученное значение добавляется в список.</span><span class="sxs-lookup"><span data-stu-id="c6933-173">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="c6933-174">Цикл повторяется, пока в список не будут добавлены 20 элементов.</span><span class="sxs-lookup"><span data-stu-id="c6933-174">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="c6933-175">Поздравляем! Вы выполнили задачи из краткого руководства по спискам.</span><span class="sxs-lookup"><span data-stu-id="c6933-175">Congratulations, you've completed the list quickstart.</span></span> <span data-ttu-id="c6933-176">Теперь вы можете выполнить руководство [Введение в классы](introduction-to-classes.md) в своей среде разработки.</span><span class="sxs-lookup"><span data-stu-id="c6933-176">You can continue with the [Introduction to classes](introduction-to-classes.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="c6933-177">Дополнительные сведения о работе с типом `List` см. в разделе о [коллекциях](../../standard/collections/index.md) [руководства по .NET](../../standard/index.md).</span><span class="sxs-lookup"><span data-stu-id="c6933-177">You can learn more about working with the `List` type in the [.NET Guide](../../standard/index.md) topic on [collections](../../standard/collections/index.md).</span></span> <span data-ttu-id="c6933-178">Также в нем описаны многие другие типы коллекций.</span><span class="sxs-lookup"><span data-stu-id="c6933-178">You'll also learn about many other collection types.</span></span>