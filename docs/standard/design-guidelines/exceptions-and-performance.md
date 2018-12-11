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
author: KrzysztofCwalina
ms.openlocfilehash: ab125117836545b9a2436347375ed0e08c591c7b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153752"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="4f683-102">Исключения и производительность</span><span class="sxs-lookup"><span data-stu-id="4f683-102">Exceptions and Performance</span></span>
<span data-ttu-id="4f683-103">Одна из распространенных проблем, связанных с исключениями том, что если они используются для кода, который регулярно завершается с ошибкой, реализация будет неприемлемо.</span><span class="sxs-lookup"><span data-stu-id="4f683-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="4f683-104">Это обоснованное предположение.</span><span class="sxs-lookup"><span data-stu-id="4f683-104">This is a valid concern.</span></span> <span data-ttu-id="4f683-105">Если член создает исключение, ее производительность может быть порядков медленнее.</span><span class="sxs-lookup"><span data-stu-id="4f683-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="4f683-106">Тем не менее можно добиться высокой производительности, предназначенных исключительно для исключения рекомендации, которые запрещено использовать коды ошибок.</span><span class="sxs-lookup"><span data-stu-id="4f683-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="4f683-107">Два шаблона, описанные в этом разделе предлагают способы сделать это.</span><span class="sxs-lookup"><span data-stu-id="4f683-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="4f683-108">**X DO NOT** использование кодов ошибок из-за проблемы, что исключения могут негативно повлиять на производительность.</span><span class="sxs-lookup"><span data-stu-id="4f683-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="4f683-109">Чтобы повысить производительность, можно использовать шаблон Tester-Doer или шаблон Try-Parse, описанные в следующих двух разделах.</span><span class="sxs-lookup"><span data-stu-id="4f683-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="4f683-110">Tester-Doer-шаблон</span><span class="sxs-lookup"><span data-stu-id="4f683-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="4f683-111">Иногда можно повысить производительности члена исключения, разбив элемента на две части.</span><span class="sxs-lookup"><span data-stu-id="4f683-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="4f683-112">Давайте взглянем на <xref:System.Collections.Generic.ICollection%601.Add%2A> метод <xref:System.Collections.Generic.ICollection%601> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4f683-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="4f683-113">Метод `Add` вызывается, если коллекция доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="4f683-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="4f683-114">Это может быть проблемы с производительностью в сценариях, где должна завершиться ошибкой часто вызова метода.</span><span class="sxs-lookup"><span data-stu-id="4f683-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="4f683-115">Одним из способов, чтобы устранить проблему — проверить, является ли коллекция для записи прежде чем пытаться добавить значение.</span><span class="sxs-lookup"><span data-stu-id="4f683-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="4f683-116">Элемент, используемый для проверки того, который в нашем примере — это свойство `IsReadOnly`, называется тест-инженер.</span><span class="sxs-lookup"><span data-stu-id="4f683-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="4f683-117">Член, используемые для операции потенциально создает исключение, `Add` метод в нашем примере называется doer.</span><span class="sxs-lookup"><span data-stu-id="4f683-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="4f683-118">**✓ CONSIDER** шаблон Tester-Doer для членов, которые могут вызвать исключения общие сценарии, чтобы избежать проблем с производительностью связанных с исключениями.</span><span class="sxs-lookup"><span data-stu-id="4f683-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="4f683-119">Шаблон try-Parse</span><span class="sxs-lookup"><span data-stu-id="4f683-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="4f683-120">Для API-интерфейсов очень важна высокая производительность следует использовать шаблон еще быстрее, чем Tester-Doer-шаблон, описанный в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="4f683-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="4f683-121">Для настройки имя члена для четко определенных проверки случае частью семантику член вызывает шаблон.</span><span class="sxs-lookup"><span data-stu-id="4f683-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="4f683-122">Например <xref:System.DateTime> определяет <xref:System.DateTime.Parse%2A> метод, который создает исключение, если синтаксический анализ строки завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="4f683-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="4f683-123">Он также определяет соответствующий <xref:System.DateTime.TryParse%2A> метод, который пытается выполнить синтаксический анализ, но возвращает false, при анализе завершилась неудачно и возвращает результат успешного синтаксического анализа с помощью `out` параметра.</span><span class="sxs-lookup"><span data-stu-id="4f683-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 <span data-ttu-id="4f683-124">При использовании этого шаблона, очень важно в строгом условия в определении функциональности try.</span><span class="sxs-lookup"><span data-stu-id="4f683-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="4f683-125">При сбое члена по любой причине, кроме четко определенных try, элемент по-прежнему должны вызывать соответствующее исключение.</span><span class="sxs-lookup"><span data-stu-id="4f683-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="4f683-126">**✓ CONSIDER** синтаксического анализа Try шаблон для членов, которые могут вызвать исключения общие сценарии, чтобы избежать проблем с производительностью связанных с исключениями.</span><span class="sxs-lookup"><span data-stu-id="4f683-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="4f683-127">**✓ DO** использовать префикс «Try» и логический тип возвращаемого значения для методов реализации данного шаблона.</span><span class="sxs-lookup"><span data-stu-id="4f683-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="4f683-128">**✓ DO** предоставляют член исключения для каждого элемента, используя шаблон синтаксического анализа Try.</span><span class="sxs-lookup"><span data-stu-id="4f683-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="4f683-129">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="4f683-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4f683-130">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4f683-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f683-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4f683-131">See also</span></span>

- [<span data-ttu-id="4f683-132">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="4f683-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="4f683-133">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="4f683-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
