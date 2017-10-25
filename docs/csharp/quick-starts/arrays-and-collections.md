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
ms.openlocfilehash: 51b190fba32186cb4c52ccd773274d9ae22c8efb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="c-quick-start-collections"></a>Краткое руководство по C#: коллекции #

Это руководство содержит общие сведения о языке C# и классе <xref:System.Collections.Generic.List%601>.

## <a name="a-simple-list-example"></a>Пример простого списка

> [!NOTE]
> Если вы используете код, написанный на платформе [dot.net](https://dot.net/), у вас уже есть фрагмент, представленный в этом разделе. Перейдите к разделу [Изменение содержимого списка](#modify-list-contents).

В этом занятии предполагается, что вы изучили краткие интернет-руководства и установили [пакет SDK для .NET Core](http://dot.net/core) и [Visual Studio Code](https://code.visualstudio.com/). 

Создайте каталог с именем **list-quickstart**. Откройте этот каталог и выполните команду `dotnet new console`.

Откройте **Program.cs** в любом редакторе и замените существующий код следующим:

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

Замените `<name>` собственным именем. Сохраните **Program.cs**. Введите в окне консоли команду `dotnet run` для тестирования.

Вы создали список строк, добавили в него три имени и вывели имена с преобразованием всех букв в прописные. Для циклического прохода по списку используются основные принципы, которые вы изучили в предыдущих кратких руководствах.

В коде для отображения имен используются **интерполированные строки**.  Если перед `string` добавить символ `$`, код C# можно внедрять в объявление строки. Фактическая строка заменяет код C# генерируемым значением. В этом примере она заменяет `{name.ToUpper()}` именами, буквы каждого из которых преобразованы в прописные, так как вызван метод <xref:System.String.ToUpper%2A>.

Продолжим изучение.
    
## <a name="modify-list-contents"></a>Изменение содержимого списка

В созданной коллекции используется тип <xref:System.Collections.Generic.List%601>. При применении такого типа сохраняются последовательности элементов. Тип элементов указывается в угловых скобках.
    
Важный аспект типа <xref:System.Collections.Generic.List%601> — возможность увеличения или уменьшения, что позволяет добавлять или удалять элементы. Добавьте следующий код в метод `Main` перед закрывающей фигурной скобкой `}`:

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

В конец списка добавлены еще два имени. При этом одно имя удалено. Сохраните файл и введите `dotnet run` для тестирования.
    
<xref:System.Collections.Generic.List%601> позволяет добавлять ссылки на отдельные элементы по **индексу**. Поместите индекс между токенами `[` и `]` после имени списка. Для первого индекса в C# используется значение 0. Добавьте следующий код сразу после добавленного фрагмента и протестируйте его:

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

Доступ к индексу за пределами списка получить невозможно. Помните, что индексы начинаются с 0, поэтому максимальный допустимый индекс меньше, чем число элементов в списке. Вы можете проверить, как долго в списке используется свойство <xref:System.Collections.Generic.List%601.Count%2A>. Добавьте следующий код в конец метода Main:

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

Сохраните файл и еще раз введите `dotnet run`, чтобы просмотреть результаты.    

## <a name="search-and-sort-lists"></a>Поиск по спискам и их сортировка
В наших примерах используются сравнительно небольшие списки. Но приложения часто создают списки с гораздо большим количеством элементов, иногда они исчисляются в тысячах. Чтобы найти элементы в таких больших коллекциях, необходимо выполнить поиск различных элементов по списку. Метод <xref:System.Collections.Generic.List%601.IndexOf%2A> выполняет поиск элемента и возвращает его индекс. Добавьте следующий код в конец метода `Main`:

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

Кроме того, можно сортировать элементы в списке. Метод <xref:System.Collections.Generic.List%601.Sort%2A> сортирует все элементы списка в обычном порядке (при использовании строк — в алфавитном порядке). Добавьте следующий код в конец метода `Main`:

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

Сохраните файл и введите `dotnet run`, чтобы протестировать последнюю версию.

Прежде чем перейти к следующему разделу, переместим текущий код в отдельный метод. Это упростит начало работы с новым примером. Переименуйте метод `Main` в `WorkingWithStrings` и запишите новый метод `Main`, который вызывает `WorkingWithStrings`. В результате ваш код должен выглядеть примерно следующим образом:

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

## <a name="lists-of-other-types"></a>Списки других типов

Вы уже использовали в списках тип `string`. Создадим <xref:System.Collections.Generic.List%601> с использованием другого типа. Сначала создадим набор чисел. 

Добавьте следующий код в конец нового метода `Main`:

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

Будет создан список целых чисел. Для первых двух целых чисел будет задано значение 1. Это два первых значения *последовательности Фибоначчи*. Каждое следующее число Фибоначчи — это сумма двух предыдущих чисел. Добавьте этот код:

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

Сохраните файл и введите `dotnet run`, чтобы просмотреть результаты. 

> [!TIP]
> Для задач этого раздела вы можете закомментировать код, который вызывает `WorkingWithStrings();`. Просто поместите два символа `/` перед вызовом. Например: `// WorkingWithStrings();`. 

## <a name="challenge"></a>Задача
Попробуйте объединить некоторые задания из этого и предыдущих занятий. Расширьте код с числами Фибоначчи, который вы создали. Напишите и протестируйте код для создания первых 20 чисел в последовательности.

## <a name="complete-challenge"></a>Выполнение задачи

Пример решения можно [просмотреть в готовом примере кода на GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs).

При каждой итерации цикла суммируются два последних целых числа в списке. Полученное значение добавляется в список. Цикл повторяется, пока в список не будут добавлены 20 элементов.

Поздравляем! Вы выполнили задачи в руководстве по спискам.

Дополнительные сведения о работе с типом `List` см. в разделе о [коллекциях](../../standard/collections/index.md) [руководства по .NET](../../standard/index.md). Также в нем описаны многие другие типы коллекций.
