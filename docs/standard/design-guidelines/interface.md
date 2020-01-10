---
title: Разработка интерфейса
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: 06b2e0d281314f3bd6346a7dbbd8bb56928fe58b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709300"
---
# <a name="interface-design"></a><span data-ttu-id="b1026-102">Разработка интерфейса</span><span class="sxs-lookup"><span data-stu-id="b1026-102">Interface Design</span></span>
<span data-ttu-id="b1026-103">Хотя большинство API-интерфейсов лучше моделировать с помощью классов и структур, существуют случаи, когда интерфейсы более подходят или являются единственным вариантом.</span><span class="sxs-lookup"><span data-stu-id="b1026-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="b1026-104">Среда CLR не поддерживает множественное наследование (т. е. классы CLR не могут наследовать более чем от одного базового класса), но позволяют типам реализовать один или несколько интерфейсов в дополнение к наследованию от базового класса.</span><span class="sxs-lookup"><span data-stu-id="b1026-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="b1026-105">Поэтому интерфейсы часто используются для достижения результата множественного наследования.</span><span class="sxs-lookup"><span data-stu-id="b1026-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="b1026-106">Например, <xref:System.IDisposable> является интерфейсом, который позволяет типам поддерживать возможность уничтожения независимо от любых других иерархий наследования, в которых они хотят участвовать.</span><span class="sxs-lookup"><span data-stu-id="b1026-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="b1026-107">Другая ситуация, при которой необходимо определить интерфейс, заключается в создании общего интерфейса, который может поддерживаться несколькими типами, включая некоторые типы значений.</span><span class="sxs-lookup"><span data-stu-id="b1026-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="b1026-108">Типы значений не могут наследовать от типов, отличных от <xref:System.ValueType>, но они могут реализовывать интерфейсы, поэтому использование интерфейса является единственным вариантом для предоставления общего базового типа.</span><span class="sxs-lookup"><span data-stu-id="b1026-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="b1026-109">**✓ DO** Определите интерфейс, если требуется, чтобы некоторые общий API, которые должны поддерживаться набор типов, который включает типы значений.</span><span class="sxs-lookup"><span data-stu-id="b1026-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="b1026-110">**✓ CONSIDER** определять интерфейс, если необходима поддержка его функциональные возможности для типов, являющихся производными от другого типа.</span><span class="sxs-lookup"><span data-stu-id="b1026-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="b1026-111">**X AVOID** с помощью маркера интерфейсов (интерфейсы без членов).</span><span class="sxs-lookup"><span data-stu-id="b1026-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="b1026-112">Если необходимо пометить класс как имеющий определенную характеристику (маркер), как правило, используйте настраиваемый атрибут, а не интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b1026-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="b1026-113">**✓ DO** укажите по крайней мере один тип, который является реализацией интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b1026-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="b1026-114">Это помогает проверить структуру интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b1026-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="b1026-115">Например, <xref:System.Collections.Generic.List%601> является реализацией интерфейса <xref:System.Collections.Generic.IList%601>.</span><span class="sxs-lookup"><span data-stu-id="b1026-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="b1026-116">**✓ DO** предоставляют по крайней мере один API, использующий каждый из определенных интерфейсов (метод, принимающий интерфейс как параметр или свойство с типом интерфейса).</span><span class="sxs-lookup"><span data-stu-id="b1026-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="b1026-117">Это помогает проверить структуру интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b1026-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="b1026-118">Например, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> использует интерфейс <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b1026-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="b1026-119">**X DO NOT** добавление членов в интерфейс, который был доставлен.</span><span class="sxs-lookup"><span data-stu-id="b1026-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="b1026-120">Это приведет к нарушению реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b1026-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="b1026-121">Чтобы избежать проблем с управлением версиями, необходимо создать новый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b1026-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="b1026-122">За исключением ситуаций, описанных в этих рекомендациях, следует в общем случае выбирать классы вместо интерфейсов при проектировании библиотек с многократным использованием управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b1026-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="b1026-123">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="b1026-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b1026-124">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="b1026-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1026-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1026-125">See also</span></span>

- [<span data-ttu-id="b1026-126">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="b1026-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="b1026-127">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="b1026-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
