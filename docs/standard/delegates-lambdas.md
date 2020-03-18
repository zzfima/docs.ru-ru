---
title: Делегаты и лямбда-выражения
description: Сведения о том, как делегаты определяют тип, указывающий конкретную сигнатуру метода, которую можно вызывать напрямую или передать другому методу и вызвать.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: 0abcc73e31eab89c422513acf778bc8bd092e788
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "75345542"
---
# <a name="delegates-and-lambdas"></a>Делегаты и лямбда-выражения

Делегаты определяют тип, указывающий конкретную сигнатуру метода. Метод (статический или экземпляр), удовлетворяющий сигнатуре, можно присвоить переменной этого типа и затем вызвать напрямую (с соответствующими аргументами) или передать в качестве аргумента другому методу и затем вызвать. В следующем примере показано использование делегата.

```csharp
using System;
using System.Linq;

public class Program
{
    public delegate string Reverse(string s);

    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Reverse rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

* В строке `public delegate string Reverse(string s);` создается тип делегата для определенной сигнатуры. В данном случае это метод, принимающий и возвращающий строковый параметр.
* Метод `static string ReverseString(string s)`, имеющий такую же сигнатуру, как и определенный тип делегата, реализует этот делегат.
* Строка `Reverse rev = ReverseString;` показывает, что метод можно назначить переменной соответствующего типа делегата.
* Строка `Console.WriteLine(rev("a string"));` показывает, как использовать переменную типа делегата для вызова этого делегата.

Чтобы упростить процесс разработки, платформа .NET содержит набор типов делегата, которые программисты могут повторно использовать, не создавая новые. Это `Func<>`, `Action<>` и `Predicate<>`, которые можно использовать в различных участках API-интерфейсов .NET без необходимости определения новых типов делегата. Безусловно между ними существуют некоторые различия, которые легко определить по сигнатурам. Это связано с их назначением:

* `Action<>` применяется, когда требуется выполнить действие с использованием аргументов делегата.
* `Func<>` обычно используется при наличии преобразования, то есть когда требуется преобразовать аргументы делегата в другой результат. Хорошим примером этого являются проекции.
* `Predicate<>` используется, когда требуется определить, удовлетворяет ли аргумент условию делегата. Его также можно записать в виде `Func<T, bool>`.

Теперь можно обратиться к приведенному выше примеру и переписать его, используя делегат `Func<>` вместо пользовательского типа. При этом работа программы не изменится.

```csharp
using System;
using System.Linq;

public class Program
{
    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Func<string, string> rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

В этом простом примере определение метода за пределами метода `Main` может показаться излишним. Это вызвано тем, что в .NET Framework 2.0 введена концепция **анонимных делегатов**. С их помощью можно создавать "встроенные" делегаты без указания дополнительного типа или метода. Вы просто встраиваете определение делегата там, где это необходимо.

Например, мы собираемся использовать анонимный делегат, чтобы отфильтровать только четные числа из списка и вывести их на консоль.

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(
          delegate (int no)
          {
              return (no % 2 == 0);
          }
        );

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

Как видно, тело делегата представляет собой набор выражений, как в любом другом делегате. Но вместо использования отдельного определения мы описали его _напрямую_ в нашем вызове метода <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType>.

Однако даже при таком подходе остается довольно много кода, от которого можно избавиться. Как раз для этого и могут пригодиться **лямбда-выражения**.

Впервые лямбда-выражения были введены в C# 3.0 в качестве одного из стандартных блоков LINQ. Они предоставляют более удобный синтаксис для использования делегатов. Они объявляют сигнатуру и тела метода, но не имеют собственного формального удостоверения, пока не будут назначены делегату. В отличие от делегатов их можно напрямую назначать в левой части при регистрации событий, а также в различных предложениях и методах LINQ.

Поскольку лямбда-выражение представляет собой просто еще один способ указания делегата, можно переписать приведенный выше пример, чтобы использовать лямбда-выражение вместо анонимного делегата.

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(i => i % 2 == 0);

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

В предыдущем примере используется лямбда-выражение `i => i % 2 == 0`. Повторим, что это просто **очень** удобный синтаксис для использования делегатов, сам принцип действия аналогичен анонимному делегату.

Лямбда-выражения — это обычные делегаты, поэтому их без проблем можно использовать в качестве обработчика событий, как показано в следующем фрагменте кода.

```csharp
public MainWindow()
{
    InitializeComponent();

    Loaded += (o, e) =>
    {
        this.Title = "Loaded";
    };
}
```

В этом контексте оператор `+=` используется для подписки на [событие](../../docs/csharp/language-reference/keywords/event.md). Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="further-reading-and-resources"></a>Дополнительные сведения и ресурсы

* [Делегаты](../../docs/csharp/programming-guide/delegates/index.md)
* [Анонимные функции](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [Лямбда-выражения](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
