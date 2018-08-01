---
title: Разработка интерфейса
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dea5877f952869d5c84d6019617fcdc52d8ee0a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573043"
---
# <a name="interface-design"></a><span data-ttu-id="d417c-102">Разработка интерфейса</span><span class="sxs-lookup"><span data-stu-id="d417c-102">Interface Design</span></span>
<span data-ttu-id="d417c-103">Несмотря на то, что большинство интерфейсов API, лучше всего моделируются с помощью классов и структур, существуют случаи, когда интерфейсы больше подходят или могут использоваться только.</span><span class="sxs-lookup"><span data-stu-id="d417c-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="d417c-104">Среда CLR не поддерживает множественное наследование (т. е. классов CLR, не может наследовать от более чем одного базового класса), но разрешает типы реализовать один или несколько интерфейсов, помимо наследование от базового класса.</span><span class="sxs-lookup"><span data-stu-id="d417c-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="d417c-105">Таким образом интерфейсы часто используются для создания эффекта множественного наследования.</span><span class="sxs-lookup"><span data-stu-id="d417c-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="d417c-106">Например <xref:System.IDisposable> — это интерфейс, позволяющий типы для поддержки disposability независимо от других иерархии наследования, в которой хотите участвовать.</span><span class="sxs-lookup"><span data-stu-id="d417c-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="d417c-107">Ситуации, в какой определение подходит интерфейс находится в создании общий интерфейс, который поддерживает несколько типов, включая некоторые типы значений.</span><span class="sxs-lookup"><span data-stu-id="d417c-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="d417c-108">Типы значений не может наследовать от типов, отличных от <xref:System.ValueType>, но они могут реализовывать интерфейсы, с помощью интерфейса — единственный доступный вариант, чтобы обеспечить общий базовый тип.</span><span class="sxs-lookup"><span data-stu-id="d417c-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="d417c-109">**✓ DO** Определите интерфейс, если требуется, чтобы некоторые общий API, которые должны поддерживаться набор типов, который включает типы значений.</span><span class="sxs-lookup"><span data-stu-id="d417c-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="d417c-110">**✓ CONSIDER** определять интерфейс, если необходима поддержка его функциональные возможности для типов, являющихся производными от другого типа.</span><span class="sxs-lookup"><span data-stu-id="d417c-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="d417c-111">**X AVOID** с помощью маркера интерфейсов (интерфейсы без членов).</span><span class="sxs-lookup"><span data-stu-id="d417c-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="d417c-112">Если необходимо пометить класс как имеющий определенных характеристик (маркер), как правило, используйте настраиваемый атрибут, а не интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d417c-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="d417c-113">**✓ DO** укажите по крайней мере один тип, который является реализацией интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d417c-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="d417c-114">Это помогает проверить дизайн интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d417c-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="d417c-115">Например <xref:System.Collections.Generic.List%601> — это реализация <xref:System.Collections.Generic.IList%601> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d417c-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="d417c-116">**✓ DO** предоставляют по крайней мере один API, использующий каждый из определенных интерфейсов (метод, принимающий интерфейс как параметр или свойство с типом интерфейса).</span><span class="sxs-lookup"><span data-stu-id="d417c-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="d417c-117">Это помогает проверить дизайн интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d417c-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="d417c-118">Например <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> использует <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d417c-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="d417c-119">**X DO NOT** добавление членов в интерфейс, который был доставлен.</span><span class="sxs-lookup"><span data-stu-id="d417c-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="d417c-120">Это может нарушить реализаций интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d417c-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="d417c-121">Чтобы избежать проблемы управления версиями следует создать новый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d417c-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="d417c-122">За исключением ситуаций, описанных в следующих рекомендаций как правило, выберите классы, а не интерфейсов в разработке повторно используемых библиотек управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="d417c-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="d417c-123">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="d417c-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d417c-124">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="d417c-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d417c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d417c-125">See Also</span></span>  
 [<span data-ttu-id="d417c-126">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="d417c-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="d417c-127">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="d417c-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
