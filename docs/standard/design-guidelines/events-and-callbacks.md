---
title: "События и обратные вызовы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 217e9eae3540e0a20afd0888d24803285d6352b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="events-and-callbacks"></a><span data-ttu-id="8c9f3-102">События и обратные вызовы</span><span class="sxs-lookup"><span data-stu-id="8c9f3-102">Events and Callbacks</span></span>
<span data-ttu-id="8c9f3-103">Обратные вызовы являются точки расширения, обеспечивающие framework обратный вызов пользовательского кода в делегате.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="8c9f3-104">Эти делегаты обычно передаются в платформе через параметр типа метода.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="8c9f3-105">События представляют собой особый случай обратных вызовов, поддерживает удобный и согласованное синтаксис для задания делегата (обработчиком событий).</span><span class="sxs-lookup"><span data-stu-id="8c9f3-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="8c9f3-106">Кроме того завершение операторов и конструкторов Visual Studio содержат справку с помощью API-интерфейсов на основе событий.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="8c9f3-107">(См. [Разработка событий](../../../docs/standard/design-guidelines/event.md).)</span><span class="sxs-lookup"><span data-stu-id="8c9f3-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="8c9f3-108">**✓ Попробуйте** использования обратных вызовов, чтобы пользователи могли использовать пользовательский код, выполняемый средой.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="8c9f3-109">**✓ Попробуйте** с помощью событий, чтобы разрешить пользователям настраивать поведение .NET framework без необходимости понимания объектно ориентированный проект.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="8c9f3-110">**✓ СДЕЛАТЬ** предпочтение события простых обратных вызовов, поскольку они знакомы более широкому диапазону разработчиков и интегрированы с Visual Studio завершение операторов.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="8c9f3-111">**X ИЗБЕГАЙТЕ** использования обратных вызовов в API, чувствительных к производительности.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="8c9f3-112">**СДЕЛАТЬ ✓** использовать новую `Func<...>`, `Action<...>`, или `Expression<...>` типов вместо пользовательских делегатов, при определении обратными вызовами API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="8c9f3-113">`Func<...>`и `Action<...>` представляют универсальных методов-делегатов.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="8c9f3-114">`Expression<...>`представляет определения функций, которые скомпилированы и впоследствии вызван во время выполнения, но может также быть сериализованы и передаются в удаленных процессов.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="8c9f3-115">**СДЕЛАТЬ ✓** измерять и анализировать проблемы производительности с помощью `Expression<...>`, вместо использования `Func<...>` и `Action<...>` делегатов.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="8c9f3-116">`Expression<...>`типы, в большинстве случаев логически эквивалентно `Func<...>` и `Action<...>` делегатов.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="8c9f3-117">Основное различие между ними является, что делегаты предназначены для использования в сценариях локального процесса; выражения, предназначены для случаев, когда он является полезным и невозможно вычислить значение выражения в удаленном процессе или компьютере.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="8c9f3-118">**✓ СДЕЛАТЬ** понять, что путем вызова делегата, выполнения произвольного кода и который может иметь безопасности, правильность и совместимость.</span><span class="sxs-lookup"><span data-stu-id="8c9f3-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="8c9f3-119">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="8c9f3-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8c9f3-120">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="8c9f3-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c9f3-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8c9f3-121">See Also</span></span>  
 [<span data-ttu-id="8c9f3-122">Разработка для расширяемости</span><span class="sxs-lookup"><span data-stu-id="8c9f3-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="8c9f3-123">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="8c9f3-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
