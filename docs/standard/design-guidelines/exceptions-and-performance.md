---
title: "Исключения и производительность"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9a876a818086e0d54251f53a1e8f83cc74a574ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="d74e9-102">Исключения и производительность</span><span class="sxs-lookup"><span data-stu-id="d74e9-102">Exceptions and Performance</span></span>
<span data-ttu-id="d74e9-103">Одна из распространенных проблем, связанных с исключениями установлено, если они используются для кода, который регулярно завершается с ошибкой, производительность реализации неприемлемо.</span><span class="sxs-lookup"><span data-stu-id="d74e9-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="d74e9-104">Это обоснованное предположение.</span><span class="sxs-lookup"><span data-stu-id="d74e9-104">This is a valid concern.</span></span> <span data-ttu-id="d74e9-105">При создании исключения члена, ее производительность может быть порядков медленнее.</span><span class="sxs-lookup"><span data-stu-id="d74e9-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="d74e9-106">Тем не менее можно добиться оптимальной производительности, предназначенных только для исключение рекомендации, которые запрещено использовать коды ошибок.</span><span class="sxs-lookup"><span data-stu-id="d74e9-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="d74e9-107">Два шаблона, описанные в этом разделе касаются способов это сделать.</span><span class="sxs-lookup"><span data-stu-id="d74e9-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="d74e9-108">**X не** использование кодов ошибок из-за проблемы, что исключения могут негативно повлиять на производительность.</span><span class="sxs-lookup"><span data-stu-id="d74e9-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="d74e9-109">Чтобы повысить производительность, можно использовать шаблон Tester-Doer или шаблоне синтаксического анализа Try, описанные в следующих двух разделах.</span><span class="sxs-lookup"><span data-stu-id="d74e9-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="d74e9-110">Шаблон Tester-Doer</span><span class="sxs-lookup"><span data-stu-id="d74e9-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="d74e9-111">Иногда производительность члена исключения можно повысить, разбив на два элемента.</span><span class="sxs-lookup"><span data-stu-id="d74e9-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="d74e9-112">Давайте рассмотрим <xref:System.Collections.Generic.ICollection%601.Add%2A> метод <xref:System.Collections.Generic.ICollection%601> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d74e9-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="d74e9-113">Метод `Add` создает исключение, если коллекция доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d74e9-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="d74e9-114">Это может вызвать проблемы производительности в сценариях, где метод должен завершиться ошибкой; часто.</span><span class="sxs-lookup"><span data-stu-id="d74e9-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="d74e9-115">Один из способов устранения проблемы заключается в проверке ли коллекция доступна для записи, прежде чем пытаться добавить значение.</span><span class="sxs-lookup"><span data-stu-id="d74e9-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="d74e9-116">Элемент, используемый для проверки того, в данном примере которого является свойство `IsReadOnly`, называется тест-инженер.</span><span class="sxs-lookup"><span data-stu-id="d74e9-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="d74e9-117">Элемент, использованный для выполнения потенциально возникло исключение операции `Add` метод в нашем примере называется doer.</span><span class="sxs-lookup"><span data-stu-id="d74e9-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="d74e9-118">**✓ Попробуйте** шаблон Tester-Doer для членов, которые могут вызвать исключения общие сценарии, чтобы избежать проблем с производительностью связанных с исключениями.</span><span class="sxs-lookup"><span data-stu-id="d74e9-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="d74e9-119">Шаблон синтаксического анализа try</span><span class="sxs-lookup"><span data-stu-id="d74e9-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="d74e9-120">Для API-интерфейсов важна высокая производительность следует использовать шаблон еще быстрее, чем шаблон Tester-Doer, описанные в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="d74e9-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="d74e9-121">Шаблон полезна корректировка имя члена, чтобы четко определенный тест случае часть семантику члена.</span><span class="sxs-lookup"><span data-stu-id="d74e9-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="d74e9-122">Например <xref:System.DateTime> определяет <xref:System.DateTime.Parse%2A> метод, который вызывает исключение, если происходит сбой синтаксического анализа строки.</span><span class="sxs-lookup"><span data-stu-id="d74e9-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="d74e9-123">Он также определяет соответствующий <xref:System.DateTime.TryParse%2A> метод, который пытается выполнить синтаксический анализ, но возвращает значение false, если синтаксический анализ завершается неудачно и возвращает результат успешного синтаксического анализа с помощью `out` параметра.</span><span class="sxs-lookup"><span data-stu-id="d74e9-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
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
  
 <span data-ttu-id="d74e9-124">При использовании этого шаблона, важно определить функциональные возможности попробуйте в strict условия.</span><span class="sxs-lookup"><span data-stu-id="d74e9-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="d74e9-125">При сбое члена по любой причине, кроме try четко определенный элемент по-прежнему должно быть соответствующее исключение.</span><span class="sxs-lookup"><span data-stu-id="d74e9-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="d74e9-126">**✓ Попробуйте** синтаксического анализа Try шаблон для членов, которые могут вызвать исключения общие сценарии, чтобы избежать проблем с производительностью связанных с исключениями.</span><span class="sxs-lookup"><span data-stu-id="d74e9-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="d74e9-127">**✓ СДЕЛАТЬ** использовать префикс «Try» и логический тип возвращаемого значения для методов реализации данного шаблона.</span><span class="sxs-lookup"><span data-stu-id="d74e9-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="d74e9-128">**✓ СДЕЛАТЬ** предоставляют член исключения для каждого элемента, используя шаблон синтаксического анализа Try.</span><span class="sxs-lookup"><span data-stu-id="d74e9-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="d74e9-129">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="d74e9-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d74e9-130">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="d74e9-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74e9-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d74e9-131">See Also</span></span>  
 [<span data-ttu-id="d74e9-132">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="d74e9-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="d74e9-133">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="d74e9-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
