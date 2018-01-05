---
title: "Базовые классы для реализации абстракций"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 96264456ac6afc569c46caf5faed6c37ea22bc8e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="base-classes-for-implementing-abstractions"></a><span data-ttu-id="9c7b5-102">Базовые классы для реализации абстракций</span><span class="sxs-lookup"><span data-stu-id="9c7b5-102">Base Classes for Implementing Abstractions</span></span>
<span data-ttu-id="9c7b5-103">Строго говоря класс становится базового класса, если другой класс является производным от него.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-103">Strictly speaking, a class becomes a base class when another class is derived from it.</span></span> <span data-ttu-id="9c7b5-104">В данном разделе, базовый класс является предназначен главным образом для предоставления общих абстракции или для других классов, чтобы повторно использовать некоторые наследование по умолчанию реализация хотя класс.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-104">For the purpose of this section, however, a base class is a class designed mainly to provide a common abstraction or for other classes to reuse some default implementation though inheritance.</span></span> <span data-ttu-id="9c7b5-105">Базовые классы обычно располагаются в середине иерархии наследования, между абстракцию в корне иерархии и несколько пользовательских реализаций внизу.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-105">Base classes usually sit in the middle of inheritance hierarchies, between an abstraction at the root of a hierarchy and several custom implementations at the bottom.</span></span>  
  
 <span data-ttu-id="9c7b5-106">Они служат в качестве реализации вспомогательные методы для реализации абстракций.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-106">They serve as implementation helpers for implementing abstractions.</span></span> <span data-ttu-id="9c7b5-107">Например, одним из Framework абстракции для упорядоченных наборов элементов является <xref:System.Collections.Generic.IList%601> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-107">For example, one of the Framework’s abstractions for ordered collections of items is the <xref:System.Collections.Generic.IList%601> interface.</span></span> <span data-ttu-id="9c7b5-108">Реализация <xref:System.Collections.Generic.IList%601> является непростой задачей, и поэтому платформа предоставляет несколько базовых классов, таких как <xref:System.Collections.ObjectModel.Collection%601> и <xref:System.Collections.ObjectModel.KeyedCollection%602>, используемые в качестве вспомогательных методов для реализации настраиваемых коллекций.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-108">Implementing <xref:System.Collections.Generic.IList%601> is not trivial, and therefore the Framework provides several base classes, such as <xref:System.Collections.ObjectModel.Collection%601> and <xref:System.Collections.ObjectModel.KeyedCollection%602>, which serve as helpers for implementing custom collections.</span></span>  
  
 <span data-ttu-id="9c7b5-109">Базовые классы не обычно подходят в качестве абстракции сами по себе, поскольку они содержат слишком много реализацию.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-109">Base classes are usually not suited to serve as abstractions by themselves, because they tend to contain too much implementation.</span></span> <span data-ttu-id="9c7b5-110">Например `Collection<T>` базового класса содержит много реализацию, связанные с тем, что он реализует неуниверсальный `IList` интерфейс (лучше интегрировать неуниверсальных коллекций), и для тот факт, что он является коллекция элементов, хранимых в объем памяти в одном из его полей.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-110">For example, the `Collection<T>` base class contains lots of implementation related to the fact that it implements the nongeneric `IList` interface (to integrate better with nongeneric collections) and to the fact that it is a collection of items stored in memory in one of its fields.</span></span>  
  
 <span data-ttu-id="9c7b5-111">Как отмечалось ранее базовые классы могут реализовывать бесценным справки для пользователей, которые необходимо реализовать абстракции, но в то же время может быть значительно ответственности.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-111">As previously discussed, base classes can provide invaluable help for users who need to implement abstractions, but at the same time they can be a significant liability.</span></span> <span data-ttu-id="9c7b5-112">Они добавляют контактной зоны и увеличить глубину иерархии наследования и поэтому концептуально усложнить платформу.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-112">They add surface area and increase the depth of inheritance hierarchies and so conceptually complicate the framework.</span></span> <span data-ttu-id="9c7b5-113">Таким образом базовые классы можно использовать только в том случае, если они предоставляют значительные усовершенствования пользователям платформы.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-113">Therefore, base classes should be used only if they provide significant value to the users of the framework.</span></span> <span data-ttu-id="9c7b5-114">Их следует избегать, если они предоставляют значение только для реализации платформу, в котором вариантов делегирование внутренней реализации вместо наследования от базового класса следует рассматривать строго.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-114">They should be avoided if they provide value only to the implementers of the framework, in which case delegation to an internal implementation instead of inheritance from a base class should be strongly considered.</span></span>  
  
 <span data-ttu-id="9c7b5-115">**✓ Попробуйте** внесения базовые классы абстрактными, даже если они не содержат абстрактных членов.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-115">**✓ CONSIDER** making base classes abstract even if they don’t contain any abstract members.</span></span> <span data-ttu-id="9c7b5-116">Это явно сообщает пользователям, предназначенное только для наследования от класса.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-116">This clearly communicates to the users that the class is designed solely to be inherited from.</span></span>  
  
 <span data-ttu-id="9c7b5-117">**✓ Попробуйте** размещать базовые классы в отдельном пространстве имен типов основным сценарием.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-117">**✓ CONSIDER** placing base classes in a separate namespace from the mainline scenario types.</span></span> <span data-ttu-id="9c7b5-118">По определению базовые классы предназначены для сложных расширенных сценариев, поэтому не являются интереса для большинства пользователей.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-118">By definition, base classes are intended for advanced extensibility scenarios and therefore are not interesting to the majority of users.</span></span>  
  
 <span data-ttu-id="9c7b5-119">**X ИЗБЕГАЙТЕ** именования базовых классов с суффиксом «Базовый», если класс предназначен для использования в открытых интерфейсах API.</span><span class="sxs-lookup"><span data-stu-id="9c7b5-119">**X AVOID** naming base classes with a "Base" suffix if the class is intended for use in public APIs.</span></span>  
  
 <span data-ttu-id="9c7b5-120">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="9c7b5-120">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9c7b5-121">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="9c7b5-121">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c7b5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="9c7b5-122">See Also</span></span>  
 [<span data-ttu-id="9c7b5-123">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="9c7b5-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="9c7b5-124">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="9c7b5-124">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
