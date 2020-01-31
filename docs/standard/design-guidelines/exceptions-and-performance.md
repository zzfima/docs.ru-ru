---
title: Исключения и производительность
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: afa4e748599781a5979823320d8913ff5357d415
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741640"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="8ed97-102">Исключения и производительность</span><span class="sxs-lookup"><span data-stu-id="8ed97-102">Exceptions and Performance</span></span>
<span data-ttu-id="8ed97-103">Одной из распространенных проблем, связанных с исключениями, является то, что если исключения используются для кода, который обычно завершается ошибкой, производительность реализации будет неприемлемой.</span><span class="sxs-lookup"><span data-stu-id="8ed97-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="8ed97-104">Это является действительной проблемой.</span><span class="sxs-lookup"><span data-stu-id="8ed97-104">This is a valid concern.</span></span> <span data-ttu-id="8ed97-105">Когда член создает исключение, его производительность может быть меньше.</span><span class="sxs-lookup"><span data-stu-id="8ed97-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="8ed97-106">Однако можно достичь хорошей производительности, при этом строго придерживаться правил исключения, которые не позволяют использовать коды ошибок.</span><span class="sxs-lookup"><span data-stu-id="8ed97-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="8ed97-107">Два шаблона, описанные в этом разделе, предлагают способы этого.</span><span class="sxs-lookup"><span data-stu-id="8ed97-107">Two patterns described in this section suggest ways to do this.</span></span>

 <span data-ttu-id="8ed97-108">❌ не используют коды ошибок из-за проблем, которые могут негативно сказаться на производительности.</span><span class="sxs-lookup"><span data-stu-id="8ed97-108">❌ DO NOT use error codes because of concerns that exceptions might affect performance negatively.</span></span>

 <span data-ttu-id="8ed97-109">Чтобы повысить производительность, можно использовать шаблон Test-злодея или шаблон Try-Parse, описанный в следующих двух разделах.</span><span class="sxs-lookup"><span data-stu-id="8ed97-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>

## <a name="tester-doer-pattern"></a><span data-ttu-id="8ed97-110">Тест-инженер — шаблон злодея</span><span class="sxs-lookup"><span data-stu-id="8ed97-110">Tester-Doer Pattern</span></span>
 <span data-ttu-id="8ed97-111">Иногда производительность члена, вызывающего исключение, может быть улучшена путем разбиения члена на два.</span><span class="sxs-lookup"><span data-stu-id="8ed97-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="8ed97-112">Рассмотрим метод <xref:System.Collections.Generic.ICollection%601.Add%2A> интерфейса <xref:System.Collections.Generic.ICollection%601>.</span><span class="sxs-lookup"><span data-stu-id="8ed97-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 <span data-ttu-id="8ed97-113">Метод `Add` вызывает исключение, если коллекция доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8ed97-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="8ed97-114">Это может быть проблемой с производительностью в сценариях, когда ожидается, что вызов метода будет выполняться часто.</span><span class="sxs-lookup"><span data-stu-id="8ed97-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="8ed97-115">Один из способов устранения проблемы заключается в том, чтобы проверить, является ли коллекция доступной для записи, прежде чем пытаться добавить значение.</span><span class="sxs-lookup"><span data-stu-id="8ed97-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 <span data-ttu-id="8ed97-116">Элемент, используемый для проверки условия, которое в нашем примере является свойством `IsReadOnly`, называется инженером-тестировщиком.</span><span class="sxs-lookup"><span data-stu-id="8ed97-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="8ed97-117">Элемент, используемый для выполнения потенциального вызова операции, `Add` метод в нашем примере, называется злодея.</span><span class="sxs-lookup"><span data-stu-id="8ed97-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>

 <span data-ttu-id="8ed97-118">✔️ Рассмотрите шаблон Test-злодея для членов, которые могут создавать исключения в распространенных сценариях, чтобы избежать проблем с производительностью, связанных с исключениями.</span><span class="sxs-lookup"><span data-stu-id="8ed97-118">✔️ CONSIDER the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

## <a name="try-parse-pattern"></a><span data-ttu-id="8ed97-119">Шаблон Try-Parse</span><span class="sxs-lookup"><span data-stu-id="8ed97-119">Try-Parse Pattern</span></span>
 <span data-ttu-id="8ed97-120">Для очень чувствительных к производительности интерфейсов API следует использовать еще более быстрый шаблон, чем шаблон Test-злодея, описанный в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="8ed97-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="8ed97-121">Шаблон вызывает метод для настройки имени элемента, чтобы сделать строго определенный тестовый случай частью семантики элемента.</span><span class="sxs-lookup"><span data-stu-id="8ed97-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="8ed97-122">Например, <xref:System.DateTime> определяет метод <xref:System.DateTime.Parse%2A>, который создает исключение, если синтаксический анализ строки завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8ed97-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="8ed97-123">Он также определяет соответствующий метод <xref:System.DateTime.TryParse%2A>, который пытается выполнить синтаксический анализ, но возвращает значение false, если синтаксический анализ завершается неудачно, и возвращает результат успешного синтаксического анализа с помощью параметра `out`.</span><span class="sxs-lookup"><span data-stu-id="8ed97-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 <span data-ttu-id="8ed97-124">При использовании этого шаблона важно определить функциональность Try в условиях ограниченного использования.</span><span class="sxs-lookup"><span data-stu-id="8ed97-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="8ed97-125">Если элемент завершается ошибкой по какой-либо причине, отличной от правильно определенной, член должен по-прежнему вызывать соответствующее исключение.</span><span class="sxs-lookup"><span data-stu-id="8ed97-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>

 <span data-ttu-id="8ed97-126">✔️ РАССМОТРИМ шаблон Try-Parse для членов, которые могут вызывать исключения в распространенных сценариях, чтобы избежать проблем с производительностью, связанных с исключениями.</span><span class="sxs-lookup"><span data-stu-id="8ed97-126">✔️ CONSIDER the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

 <span data-ttu-id="8ed97-127">✔️ использовать префикс "try" и логический тип возвращаемого значения для методов, реализующих этот шаблон.</span><span class="sxs-lookup"><span data-stu-id="8ed97-127">✔️ DO use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>

 <span data-ttu-id="8ed97-128">✔️ предоставить элемент, создающий исключения, для каждого члена с помощью шаблона try-Parse.</span><span class="sxs-lookup"><span data-stu-id="8ed97-128">✔️ DO provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>

 <span data-ttu-id="8ed97-129">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="8ed97-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="8ed97-130">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="8ed97-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="8ed97-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ed97-131">See also</span></span>

- [<span data-ttu-id="8ed97-132">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="8ed97-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="8ed97-133">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="8ed97-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
