---
title: Делегаты и лямбда-выражения
description: Сведения о том, как делегаты определяют тип, указывающий конкретную сигнатуру метода, которую можно вызывать напрямую или передать другому методу и вызвать.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: 0abcc73e31eab89c422513acf778bc8bd092e788
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345542"
---
# <a name="delegates-and-lambdas"></a><span data-ttu-id="66f59-103">Делегаты и лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="66f59-103">Delegates and lambdas</span></span>

<span data-ttu-id="66f59-104">Делегаты определяют тип, указывающий конкретную сигнатуру метода.</span><span class="sxs-lookup"><span data-stu-id="66f59-104">Delegates define a type, which specify a particular method signature.</span></span> <span data-ttu-id="66f59-105">Метод (статический или экземпляр), удовлетворяющий сигнатуре, можно присвоить переменной этого типа и затем вызвать напрямую (с соответствующими аргументами) или передать в качестве аргумента другому методу и затем вызвать.</span><span class="sxs-lookup"><span data-stu-id="66f59-105">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="66f59-106">В следующем примере показано использование делегата.</span><span class="sxs-lookup"><span data-stu-id="66f59-106">The following example demonstrates delegate use.</span></span>

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

* <span data-ttu-id="66f59-107">В строке `public delegate string Reverse(string s);` создается тип делегата для определенной сигнатуры. В данном случае это метод, принимающий и возвращающий строковый параметр.</span><span class="sxs-lookup"><span data-stu-id="66f59-107">The `public delegate string Reverse(string s);` line creates a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
* <span data-ttu-id="66f59-108">Метод `static string ReverseString(string s)`, имеющий такую же сигнатуру, как и определенный тип делегата, реализует этот делегат.</span><span class="sxs-lookup"><span data-stu-id="66f59-108">The `static string ReverseString(string s)` method, which has the exact same signature as the defined delegate type, implements the delegate.</span></span>
* <span data-ttu-id="66f59-109">Строка `Reverse rev = ReverseString;` показывает, что метод можно назначить переменной соответствующего типа делегата.</span><span class="sxs-lookup"><span data-stu-id="66f59-109">The `Reverse rev = ReverseString;` line shows that you can assign a method to a variable of the corresponding delegate type.</span></span>
* <span data-ttu-id="66f59-110">Строка `Console.WriteLine(rev("a string"));` показывает, как использовать переменную типа делегата для вызова этого делегата.</span><span class="sxs-lookup"><span data-stu-id="66f59-110">The `Console.WriteLine(rev("a string"));` line demonstrates how to use a variable of a delegate type to invoke the delegate.</span></span>

<span data-ttu-id="66f59-111">Чтобы упростить процесс разработки, платформа .NET содержит набор типов делегата, которые программисты могут повторно использовать, не создавая новые.</span><span class="sxs-lookup"><span data-stu-id="66f59-111">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="66f59-112">Это `Func<>`, `Action<>` и `Predicate<>`, которые можно использовать в различных участках API-интерфейсов .NET без необходимости определения новых типов делегата.</span><span class="sxs-lookup"><span data-stu-id="66f59-112">These are `Func<>`, `Action<>` and `Predicate<>`, and they can be used in various places throughout the .NET APIs without the need to define new delegate types.</span></span> <span data-ttu-id="66f59-113">Безусловно между ними существуют некоторые различия, которые легко определить по сигнатурам. Это связано с их назначением:</span><span class="sxs-lookup"><span data-stu-id="66f59-113">Of course, there are some differences between the three as you will see in their signatures which mostly have to do with the way they were meant to be used:</span></span>

* <span data-ttu-id="66f59-114">`Action<>` применяется, когда требуется выполнить действие с использованием аргументов делегата.</span><span class="sxs-lookup"><span data-stu-id="66f59-114">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span>
* <span data-ttu-id="66f59-115">`Func<>` обычно используется при наличии преобразования, то есть когда требуется преобразовать аргументы делегата в другой результат.</span><span class="sxs-lookup"><span data-stu-id="66f59-115">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="66f59-116">Хорошим примером этого являются проекции.</span><span class="sxs-lookup"><span data-stu-id="66f59-116">Projections are a prime example of this.</span></span>
* <span data-ttu-id="66f59-117">`Predicate<>` используется, когда требуется определить, удовлетворяет ли аргумент условию делегата.</span><span class="sxs-lookup"><span data-stu-id="66f59-117">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="66f59-118">Его также можно записать в виде `Func<T, bool>`.</span><span class="sxs-lookup"><span data-stu-id="66f59-118">It can also be written as a `Func<T, bool>`.</span></span>

<span data-ttu-id="66f59-119">Теперь можно обратиться к приведенному выше примеру и переписать его, используя делегат `Func<>` вместо пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="66f59-119">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="66f59-120">При этом работа программы не изменится.</span><span class="sxs-lookup"><span data-stu-id="66f59-120">The program will continue running exactly the same.</span></span>

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

<span data-ttu-id="66f59-121">В этом простом примере определение метода за пределами метода `Main` может показаться излишним.</span><span class="sxs-lookup"><span data-stu-id="66f59-121">For this simple example, having a method defined outside of the `Main` method seems a bit superfluous.</span></span> <span data-ttu-id="66f59-122">Это вызвано тем, что в .NET Framework 2.0 введена концепция **анонимных делегатов**.</span><span class="sxs-lookup"><span data-stu-id="66f59-122">It is because of this that .NET Framework 2.0 introduced the concept of **anonymous delegates**.</span></span> <span data-ttu-id="66f59-123">С их помощью можно создавать "встроенные" делегаты без указания дополнительного типа или метода.</span><span class="sxs-lookup"><span data-stu-id="66f59-123">With their support you are able to create "inline" delegates without having to specify any additional type or method.</span></span> <span data-ttu-id="66f59-124">Вы просто встраиваете определение делегата там, где это необходимо.</span><span class="sxs-lookup"><span data-stu-id="66f59-124">You simply inline the definition of the delegate where you need it.</span></span>

<span data-ttu-id="66f59-125">Например, мы собираемся использовать анонимный делегат, чтобы отфильтровать только четные числа из списка и вывести их на консоль.</span><span class="sxs-lookup"><span data-stu-id="66f59-125">For an example, we are going to switch it up and use our anonymous delegate to filter out a list of only even numbers and then print them to the console.</span></span>

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

<span data-ttu-id="66f59-126">Как видно, тело делегата представляет собой набор выражений, как в любом другом делегате.</span><span class="sxs-lookup"><span data-stu-id="66f59-126">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="66f59-127">Но вместо использования отдельного определения мы описали его _напрямую_ в нашем вызове метода <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="66f59-127">But instead of it being a separate definition, we’ve introduced it _ad hoc_ in our call to the <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="66f59-128">Однако даже при таком подходе остается довольно много кода, от которого можно избавиться.</span><span class="sxs-lookup"><span data-stu-id="66f59-128">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="66f59-129">Как раз для этого и могут пригодиться **лямбда-выражения**.</span><span class="sxs-lookup"><span data-stu-id="66f59-129">This is where **lambda expressions** come into play.</span></span>

<span data-ttu-id="66f59-130">Впервые лямбда-выражения были введены в C# 3.0 в качестве одного из стандартных блоков LINQ.</span><span class="sxs-lookup"><span data-stu-id="66f59-130">Lambda expressions, or just "lambdas" for short, were introduced first in C# 3.0, as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="66f59-131">Они предоставляют более удобный синтаксис для использования делегатов.</span><span class="sxs-lookup"><span data-stu-id="66f59-131">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="66f59-132">Они объявляют сигнатуру и тела метода, но не имеют собственного формального удостоверения, пока не будут назначены делегату.</span><span class="sxs-lookup"><span data-stu-id="66f59-132">They declare a signature and a method body, but don’t have an formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="66f59-133">В отличие от делегатов их можно напрямую назначать в левой части при регистрации событий, а также в различных предложениях и методах LINQ.</span><span class="sxs-lookup"><span data-stu-id="66f59-133">Unlike delegates, they can be directly assigned as the left-hand side of event registration or in various LINQ clauses and methods.</span></span>

<span data-ttu-id="66f59-134">Поскольку лямбда-выражение представляет собой просто еще один способ указания делегата, можно переписать приведенный выше пример, чтобы использовать лямбда-выражение вместо анонимного делегата.</span><span class="sxs-lookup"><span data-stu-id="66f59-134">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

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

<span data-ttu-id="66f59-135">В предыдущем примере используется лямбда-выражение `i => i % 2 == 0`.</span><span class="sxs-lookup"><span data-stu-id="66f59-135">In the preceding example, the lambda expression used is `i => i % 2 == 0`.</span></span> <span data-ttu-id="66f59-136">Повторим, что это просто **очень** удобный синтаксис для использования делегатов, сам принцип действия аналогичен анонимному делегату.</span><span class="sxs-lookup"><span data-stu-id="66f59-136">Again, it is just a **very** convenient syntax for using delegates, so what happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="66f59-137">Лямбда-выражения — это обычные делегаты, поэтому их без проблем можно использовать в качестве обработчика событий, как показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="66f59-137">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

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

<span data-ttu-id="66f59-138">В этом контексте оператор `+=` используется для подписки на [событие](../../docs/csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="66f59-138">The `+=` operator in this context is used to subscribe to an [event](../../docs/csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="66f59-139">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="66f59-139">For more information, see [How to subscribe to and unsubscribe from events](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="66f59-140">Дополнительные сведения и ресурсы</span><span class="sxs-lookup"><span data-stu-id="66f59-140">Further reading and resources</span></span>

* [<span data-ttu-id="66f59-141">Делегаты</span><span class="sxs-lookup"><span data-stu-id="66f59-141">Delegates</span></span>](../../docs/csharp/programming-guide/delegates/index.md)
* [<span data-ttu-id="66f59-142">Анонимные функции</span><span class="sxs-lookup"><span data-stu-id="66f59-142">Anonymous Functions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [<span data-ttu-id="66f59-143">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="66f59-143">Lambda expressions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
