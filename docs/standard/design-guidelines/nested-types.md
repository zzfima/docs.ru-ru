---
title: "Вложенные типы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 389ba73c4509f41f6c2cf86363e59ea720eb3c9f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="nested-types"></a><span data-ttu-id="3dd3b-102">Вложенные типы</span><span class="sxs-lookup"><span data-stu-id="3dd3b-102">Nested Types</span></span>
<span data-ttu-id="3dd3b-103">Вложенный тип — это тип, определенный внутри области другого типа, который называется включающего типа.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-103">A nested type is a type defined within the scope of another type, which is called the enclosing type.</span></span> <span data-ttu-id="3dd3b-104">Вложенный тип имеет доступ ко всем членам включающего типа.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-104">A nested type has access to all members of its enclosing type.</span></span> <span data-ttu-id="3dd3b-105">Например он получает доступ к закрытым полям, определенных в включающего типа и полей, определенных в всех предков этого типа защищены.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-105">For example, it has access to private fields defined in the enclosing type and to protected fields defined in all ascendants of the enclosing type.</span></span>  
  
 <span data-ttu-id="3dd3b-106">Как правило вложенные типы должно использоваться ограниченно.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-106">In general, nested types should be used sparingly.</span></span> <span data-ttu-id="3dd3b-107">Для этого есть несколько причин.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-107">There are several reasons for this.</span></span> <span data-ttu-id="3dd3b-108">Некоторые разработчики не полностью ознакомиться с концепцией.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-108">Some developers are not fully familiar with the concept.</span></span> <span data-ttu-id="3dd3b-109">Эти разработчиков например, возможно, проблемы с синтаксисом объявления переменных вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-109">These developers might, for example, have problems with the syntax of declaring variables of nested types.</span></span> <span data-ttu-id="3dd3b-110">Вложенные типы также очень тесно связана с их заключенных типов и таким образом, не подходят для типов общего назначения.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-110">Nested types are also very tightly coupled with their enclosing types, and as such are not suited to be general-purpose types.</span></span>  
  
 <span data-ttu-id="3dd3b-111">Вложенные типы лучше всего подходят для моделирования детали реализации их заключенных типов.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-111">Nested types are best suited for modeling implementation details of their enclosing types.</span></span> <span data-ttu-id="3dd3b-112">Конечному пользователю не придется объявлять переменные вложенного типа и практически никогда не придется явно создать экземпляр вложенные типы.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-112">The end user should rarely have to declare variables of a nested type and almost never should have to explicitly instantiate nested types.</span></span> <span data-ttu-id="3dd3b-113">Например перечислитель коллекции может быть вложенным типом этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-113">For example, the enumerator of a collection can be a nested type of that collection.</span></span> <span data-ttu-id="3dd3b-114">Перечислители обычно создаются с содержащим их типом, а поскольку многие языки поддерживают оператор foreach, переменные перечислитель редко должны быть объявлены конечным пользователем.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-114">Enumerators are usually instantiated by their enclosing type, and because many languages support the foreach statement, enumerator variables rarely have to be declared by the end user.</span></span>  
  
 <span data-ttu-id="3dd3b-115">**✓ СДЕЛАТЬ** используйте вложенные типы, когда отношения между вложенным типом и его внешним типом таким образом, что желательна семантика доступности члена.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-115">**✓ DO** use nested types when the relationship between the nested type and its outer type is such that member-accessibility semantics are desirable.</span></span>  
  
 <span data-ttu-id="3dd3b-116">**X не** используйте открытые вложенные типы как логическое группирование создания; использовать для данного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-116">**X DO NOT** use public nested types as a logical grouping construct; use namespaces for this.</span></span>  
  
 <span data-ttu-id="3dd3b-117">**X ИЗБЕГАЙТЕ** открытым вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-117">**X AVOID** publicly exposed nested types.</span></span> <span data-ttu-id="3dd3b-118">Единственным исключением является Если переменные вложенного типа должны быть объявлены только в редких случаях, таких как работа с подклассами и расширенными сценариями.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-118">The only exception to this is if variables of the nested type need to be declared only in rare scenarios such as subclassing or other advanced customization scenarios.</span></span>  
  
 <span data-ttu-id="3dd3b-119">**X не** используйте вложенные типы, если тип может ссылаться на за пределами содержащего типа.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-119">**X DO NOT** use nested types if the type is likely to be referenced outside of the containing type.</span></span>  
  
 <span data-ttu-id="3dd3b-120">Например передаваемый в метод, определенный в классе перечисления не должен быть определен как вложенный тип класса.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-120">For example, an enum passed to a method defined on a class should not be defined as a nested type in the class.</span></span>  
  
 <span data-ttu-id="3dd3b-121">**X не** используйте вложенные типы, если они должны создаваться в клиентском коде.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-121">**X DO NOT** use nested types if they need to be instantiated by client code.</span></span>  <span data-ttu-id="3dd3b-122">Если тип имеет открытый конструктор, он, скорее всего, не должен быть вложенным.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-122">If a type has a public constructor, it should probably not be nested.</span></span>  
  
 <span data-ttu-id="3dd3b-123">Если тип может быть создан, видимо, для указания типа есть место в framework сам по себе (можно создать ее, работать с ними и уничтожать без помощи внешнего типа никогда) и поэтому не должен быть вложенным.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-123">If a type can be instantiated, that seems to indicate the type has a place in the framework on its own (you can create it, work with it, and destroy it without ever using the outer type), and thus should not be nested.</span></span> <span data-ttu-id="3dd3b-124">Внутренние типы не должны широко использоваться за пределами внешнего типа без связи никакой для внешнего типа.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-124">Inner types should not be widely reused outside of the outer type without any relationship whatsoever to the outer type.</span></span>  
  
 <span data-ttu-id="3dd3b-125">**X не** определить вложенный тип в качестве члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-125">**X DO NOT** define a nested type as a member of an interface.</span></span> <span data-ttu-id="3dd3b-126">Такая конструкция не поддерживают многие языки.</span><span class="sxs-lookup"><span data-stu-id="3dd3b-126">Many languages do not support such a construct.</span></span>  
  
 <span data-ttu-id="3dd3b-127">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="3dd3b-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3dd3b-128">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="3dd3b-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dd3b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="3dd3b-129">See Also</span></span>  
 [<span data-ttu-id="3dd3b-130">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="3dd3b-130">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="3dd3b-131">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="3dd3b-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
