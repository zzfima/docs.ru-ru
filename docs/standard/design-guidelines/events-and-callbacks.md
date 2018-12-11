---
title: События и обратные вызовы
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
author: KrzysztofCwalina
ms.openlocfilehash: c9ed52c5a313676baeba66f5cb79c7a56927babb
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154428"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="92191-102">События и обратные вызовы</span><span class="sxs-lookup"><span data-stu-id="92191-102">Events and Callbacks</span></span>
<span data-ttu-id="92191-103">Обратные вызовы являются точки расширения, обеспечивающие framework выполнить обратный вызов пользовательского кода в делегате.</span><span class="sxs-lookup"><span data-stu-id="92191-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="92191-104">Обычно эти делегаты передаются платформы, в качестве параметра метода.</span><span class="sxs-lookup"><span data-stu-id="92191-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="92191-105">События представляют собой особый случай обратных вызовов, который поддерживает удобный и согласованный синтаксис для задания делегата (обработчик события).</span><span class="sxs-lookup"><span data-stu-id="92191-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="92191-106">Кроме того завершение операторов и конструкторы Visual Studio предоставление справки в с помощью интерфейсов API на основе событий.</span><span class="sxs-lookup"><span data-stu-id="92191-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="92191-107">(См. в разделе [Разработка событий](../../../docs/standard/design-guidelines/event.md).)</span><span class="sxs-lookup"><span data-stu-id="92191-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="92191-108">**✓ CONSIDER** использования обратных вызовов, чтобы пользователи могли использовать пользовательский код, выполняемый средой.</span><span class="sxs-lookup"><span data-stu-id="92191-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="92191-109">**✓ CONSIDER** с помощью событий, чтобы разрешить пользователям настраивать поведение .NET framework без необходимости понимания объектно ориентированный проект.</span><span class="sxs-lookup"><span data-stu-id="92191-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="92191-110">**✓ DO** предпочтение события простых обратных вызовов, поскольку они знакомы более широкому диапазону разработчиков и интегрированы с Visual Studio завершение операторов.</span><span class="sxs-lookup"><span data-stu-id="92191-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="92191-111">**X AVOID** использования обратных вызовов в API, чувствительных к производительности.</span><span class="sxs-lookup"><span data-stu-id="92191-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="92191-112">**✓ DO** использовать новую `Func<...>`, `Action<...>`, или `Expression<...>` типов вместо пользовательских делегатов, при определении обратными вызовами API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="92191-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="92191-113">`Func<...>` и `Action<...>` представляют универсальных методах-делегатах.</span><span class="sxs-lookup"><span data-stu-id="92191-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="92191-114">`Expression<...>` представляет определения функций, которые скомпилированы и впоследствии вызван во время выполнения, но может также быть сериализован и передан для удаленных процессов.</span><span class="sxs-lookup"><span data-stu-id="92191-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="92191-115">**✓ DO** измерять и анализировать проблемы производительности с помощью `Expression<...>`, вместо использования `Func<...>` и `Action<...>` делегатов.</span><span class="sxs-lookup"><span data-stu-id="92191-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="92191-116">`Expression<...>` типы находятся в большинстве случаев логически эквивалентен `Func<...>` и `Action<...>` делегатов.</span><span class="sxs-lookup"><span data-stu-id="92191-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="92191-117">Основное различие между ними является, что делегаты предназначены для использования в сценариях локального процесса; выражения предназначены для случаев, когда она является полезным, так и возможность вычислить выражение в удаленном процессе или компьютере.</span><span class="sxs-lookup"><span data-stu-id="92191-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="92191-118">**✓ DO** понять, что путем вызова делегата, выполнения произвольного кода и который может иметь безопасности, правильность и совместимость.</span><span class="sxs-lookup"><span data-stu-id="92191-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="92191-119">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="92191-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="92191-120">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="92191-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92191-121">См. также</span><span class="sxs-lookup"><span data-stu-id="92191-121">See also</span></span>

- [<span data-ttu-id="92191-122">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="92191-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="92191-123">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="92191-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
