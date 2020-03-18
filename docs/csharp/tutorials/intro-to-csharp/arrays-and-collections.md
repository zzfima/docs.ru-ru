---
title: Работа с коллекциями. Вводное руководство по C#
description: Это руководство по C# предоставляет для изучения примере коллекции списков.
ms.date: 10/13/2017
ms.custom: mvc
ms.openlocfilehash: 25d20de2eae8ad1f544fa17553c173a6141ae464
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156693"
---
# <a name="learn-to-manage-data-collections-using-the-generic-list-type"></a>Научитесь управлять коллекциями данных с использованием универсального типа списка

Это вводное руководство содержит общие сведения о языке C# и классе <xref:System.Collections.Generic.List%601>.

Для работы с этим руководством вам потребуется компьютер, который можно использовать для разработки. В руководстве .NET по созданию программы [Hello World за 10 минут](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) содержатся инструкции по настройке локальной среды разработки в macOS, Windows или Linux. Краткий обзор команд, которые будут здесь использоваться, и ссылки на дополнительные сведения представлены в статье [Become familiar with the .NET development tools](local-environment.md) (Знакомство со средствами разработки для .NET).

## <a name="a-basic-list-example"></a>Пример простого списка

Создайте каталог с именем *list-tutorial*. Откройте этот каталог и выполните команду `dotnet new console`.

Откройте *Program.cs* в любом редакторе и замените существующий код следующим:

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
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

Замените `<name>` собственным именем. Сохраните файл *Program.cs*. Введите в окне консоли команду `dotnet run` для тестирования.

Вы создали список строк, добавили в него три имени и вывели имена с преобразованием всех букв в прописные. Для циклического прохода по списку вы примените концепции, которые изучили в предыдущих руководствах.

В коде для отображения имен используется функция [интерполяции строк](../../language-reference/tokens/interpolated.md).  Если перед `string` добавить символ `$`, код C# можно внедрять в объявление строки. Фактическая строка заменяет код C# генерируемым значением. В этом примере она заменяет `{name.ToUpper()}` именами, буквы каждого из которых преобразованы в прописные, так как вызван метод <xref:System.String.ToUpper%2A>.

Продолжим изучение.

## <a name="modify-list-contents"></a>Изменение содержимого списка

В созданной коллекции используется тип <xref:System.Collections.Generic.List%601>. При применении такого типа сохраняются последовательности элементов. Тип элементов указывается в угловых скобках.

Важный аспект типа <xref:System.Collections.Generic.List%601> — возможность увеличения или уменьшения, что позволяет добавлять или удалять элементы. Добавьте следующий код в метод `}` перед закрывающей фигурной скобкой `Main`:

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
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
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

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        static void WorkingWithStrings()
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
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");
            }

            index = names.IndexOf("Not Found");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");

            }

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

foreach (var item in fibonacciNumbers)
    Console.WriteLine(item);
```

Сохраните файл и введите `dotnet run`, чтобы просмотреть результаты.

> [!TIP]
> Для задач этого раздела вы можете закомментировать код, который вызывает `WorkingWithStrings();`. Просто поместите два символа `/` перед вызовом. Например: `// WorkingWithStrings();`.

## <a name="challenge"></a>Задача

Попробуйте объединить некоторые идеи из этого и предыдущих занятий. Расширьте код с числами Фибоначчи, который вы создали. Попробуйте написать код для создания первых 20 чисел в последовательности. Подсказка: 20-е число Фибоначчи — 6765.

## <a name="complete-challenge"></a>Выполнение задачи

Пример решения можно [просмотреть в готовом примере кода на GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23).

При каждой итерации цикла суммируются два последних целых числа в списке. Полученное значение добавляется в список. Цикл повторяется, пока в список не будут добавлены 20 элементов.

Поздравляем! Вы выполнили задачи в руководстве по спискам. Теперь вы можете выполнить задачи [вводного руководства по классам](introduction-to-classes.md) в своей среде разработки.

Дополнительные сведения о работе с типом `List` см. в разделе о [коллекциях](../../../standard/index.md)[руководства по .NET](../../../standard/collections/index.md). Также в нем описаны многие другие типы коллекций.
