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
ms.openlocfilehash: 80c16e29f1d8a0653295ebc3cf25be6fb78b7dc9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709417"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="0bf49-102">События и обратные вызовы</span><span class="sxs-lookup"><span data-stu-id="0bf49-102">Events and Callbacks</span></span>
<span data-ttu-id="0bf49-103">Обратные вызовы — это точки расширения, позволяющие платформе выполнять обратный вызов пользовательского кода через делегат.</span><span class="sxs-lookup"><span data-stu-id="0bf49-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="0bf49-104">Эти делегаты обычно передаются в платформу с помощью параметра метода.</span><span class="sxs-lookup"><span data-stu-id="0bf49-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="0bf49-105">События являются особым случаем обратных вызовов, которые поддерживают удобный и последовательный синтаксис для предоставления делегата (обработчик события).</span><span class="sxs-lookup"><span data-stu-id="0bf49-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="0bf49-106">Кроме того, завершение операторов и конструкторы Visual Studio предоставляют справку по использованию интерфейсов API на основе событий.</span><span class="sxs-lookup"><span data-stu-id="0bf49-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="0bf49-107">(См. раздел [Конструирование событий](../../../docs/standard/design-guidelines/event.md).)</span><span class="sxs-lookup"><span data-stu-id="0bf49-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="0bf49-108">**✓ CONSIDER** использования обратных вызовов, чтобы пользователи могли использовать пользовательский код, выполняемый средой.</span><span class="sxs-lookup"><span data-stu-id="0bf49-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="0bf49-109">**✓ CONSIDER** с помощью событий, чтобы разрешить пользователям настраивать поведение .NET framework без необходимости понимания объектно ориентированный проект.</span><span class="sxs-lookup"><span data-stu-id="0bf49-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="0bf49-110">**✓ DO** предпочтение события простых обратных вызовов, поскольку они знакомы более широкому диапазону разработчиков и интегрированы с Visual Studio завершение операторов.</span><span class="sxs-lookup"><span data-stu-id="0bf49-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="0bf49-111">**X AVOID** использования обратных вызовов в API, чувствительных к производительности.</span><span class="sxs-lookup"><span data-stu-id="0bf49-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="0bf49-112">**✓ DO** использовать новую `Func<...>`, `Action<...>`, или `Expression<...>` типов вместо пользовательских делегатов, при определении обратными вызовами API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="0bf49-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="0bf49-113">`Func<...>` и `Action<...>` представляют универсальные делегаты.</span><span class="sxs-lookup"><span data-stu-id="0bf49-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="0bf49-114">`Expression<...>` представляет определения функций, которые могут быть скомпилированы и впоследствии вызваны во время выполнения, но также могут быть сериализованы и переданы в удаленные процессы.</span><span class="sxs-lookup"><span data-stu-id="0bf49-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="0bf49-115">**✓ DO** измерять и анализировать проблемы производительности с помощью `Expression<...>`, вместо использования `Func<...>` и `Action<...>` делегатов.</span><span class="sxs-lookup"><span data-stu-id="0bf49-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="0bf49-116">типы `Expression<...>` в большинстве случаев логически эквивалентны делегатам `Func<...>` и `Action<...>`.</span><span class="sxs-lookup"><span data-stu-id="0bf49-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="0bf49-117">Основное различие между ними заключается в том, что делегаты предназначены для использования в сценариях локальных процессов; выражения предназначены для случаев, когда полезно и может вычислить выражение в удаленном процессе или на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0bf49-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="0bf49-118">**✓ DO** понять, что путем вызова делегата, выполнения произвольного кода и который может иметь безопасности, правильность и совместимость.</span><span class="sxs-lookup"><span data-stu-id="0bf49-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="0bf49-119">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="0bf49-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0bf49-120">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="0bf49-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf49-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="0bf49-121">See also</span></span>

- [<span data-ttu-id="0bf49-122">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="0bf49-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="0bf49-123">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="0bf49-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
