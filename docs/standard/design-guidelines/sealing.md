---
title: "Запечатывание"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 39bb29d36b6d81464b1213ebc0bf7aee6ceb5713
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="sealing"></a><span data-ttu-id="7853d-102">Запечатывание</span><span class="sxs-lookup"><span data-stu-id="7853d-102">Sealing</span></span>
<span data-ttu-id="7853d-103">Одной из функций платформ объектно ориентированного — что разработчики могут расширять и настраивать их способами, непредвиденных конструкторами framework.</span><span class="sxs-lookup"><span data-stu-id="7853d-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="7853d-104">Это возможности и опасность расширяемой архитектуры.</span><span class="sxs-lookup"><span data-stu-id="7853d-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="7853d-105">При проектировании вашей платформы это, поэтому очень важно тщательно разработке для расширяемости его при необходимости и ограничить расширяемости, когда это опасно.</span><span class="sxs-lookup"><span data-stu-id="7853d-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="7853d-106">Мощный механизм, который запрещает расширяемости запечатывания.</span><span class="sxs-lookup"><span data-stu-id="7853d-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="7853d-107">Чтобы запечатать отдельных членов или класса.</span><span class="sxs-lookup"><span data-stu-id="7853d-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="7853d-108">Запечатывание класс запрещает наследование от класса.</span><span class="sxs-lookup"><span data-stu-id="7853d-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="7853d-109">Запечатывание членом запрещает переопределение конкретный член.</span><span class="sxs-lookup"><span data-stu-id="7853d-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="7853d-110">**X не** запечатывайте классы без необходимости веская причина для этого.</span><span class="sxs-lookup"><span data-stu-id="7853d-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="7853d-111">Запечатывание класса, так как не удается представить сценария расширяемости не веская причина.</span><span class="sxs-lookup"><span data-stu-id="7853d-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="7853d-112">Пользователи Framework, такие как наследование от классов по различным причинам nonobvious, такие как добавление членов удобства.</span><span class="sxs-lookup"><span data-stu-id="7853d-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="7853d-113">В разделе [незапечатанных классов](../../../docs/standard/design-guidelines/unsealed-classes.md) примеры nonobvious причинам необходимо наследовать от типа.</span><span class="sxs-lookup"><span data-stu-id="7853d-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="7853d-114">Ниже приведены достаточные основания для запечатывания класса:</span><span class="sxs-lookup"><span data-stu-id="7853d-114">Good reasons for sealing a class include the following:</span></span>  
  
-   <span data-ttu-id="7853d-115">Класс является статическим классом.</span><span class="sxs-lookup"><span data-stu-id="7853d-115">The class is a static class.</span></span> <span data-ttu-id="7853d-116">В разделе [статический класс конструирования](../../../docs/standard/design-guidelines/static-class.md).</span><span class="sxs-lookup"><span data-stu-id="7853d-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
-   <span data-ttu-id="7853d-117">Класс сохраняет конфиденциальные секреты в наследуемые защищенные члены.</span><span class="sxs-lookup"><span data-stu-id="7853d-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
-   <span data-ttu-id="7853d-118">Этот класс наследует многих виртуальных членов и затраты на их по отдельности запечатывание бы превысить оставить незапечатанного класса.</span><span class="sxs-lookup"><span data-stu-id="7853d-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
-   <span data-ttu-id="7853d-119">Класс является атрибут, который требуется очень быстрое время выполнения поиска.</span><span class="sxs-lookup"><span data-stu-id="7853d-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="7853d-120">Запечатанный атрибуты имеют немного более высоких уровней производительности, чем незапечатанный из них.</span><span class="sxs-lookup"><span data-stu-id="7853d-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="7853d-121">в разделе [атрибуты](../../../docs/standard/design-guidelines/attributes.md).</span><span class="sxs-lookup"><span data-stu-id="7853d-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="7853d-122">**X не** объявлять защищенные или виртуальные члены в запечатанных типах.</span><span class="sxs-lookup"><span data-stu-id="7853d-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="7853d-123">По определению наследовать запечатанные типы нельзя из.</span><span class="sxs-lookup"><span data-stu-id="7853d-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="7853d-124">Это означает, что не может вызываться защищенные члены в запечатанных типах и виртуальных методов для запечатанных типов не может быть переопределен.</span><span class="sxs-lookup"><span data-stu-id="7853d-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="7853d-125">**✓ Попробуйте** запечатывание члены, которые можно переопределить.</span><span class="sxs-lookup"><span data-stu-id="7853d-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="7853d-126">Проблемы, которые могут быть результатом Общие сведения о виртуальных членах (описано в [виртуальные члены](../../../docs/standard/design-guidelines/virtual-members.md)) применяются переопределения, хотя и немного меньшую степень.</span><span class="sxs-lookup"><span data-stu-id="7853d-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="7853d-127">Запечатывание переопределение скрывает от вас этих проблем, начиная с этой точки в иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="7853d-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="7853d-128">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="7853d-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="7853d-129">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="7853d-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7853d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="7853d-130">See Also</span></span>  
 [<span data-ttu-id="7853d-131">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="7853d-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="7853d-132">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="7853d-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="7853d-133">Незапечатанные классы</span><span class="sxs-lookup"><span data-stu-id="7853d-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
