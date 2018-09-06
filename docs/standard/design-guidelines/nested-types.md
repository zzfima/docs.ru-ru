---
title: Вложенные типы
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2593b85dd4747a3fbe365994c3e5d9beae3e3406
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891544"
---
# <a name="nested-types"></a><span data-ttu-id="e6397-102">Вложенные типы</span><span class="sxs-lookup"><span data-stu-id="e6397-102">Nested Types</span></span>
<span data-ttu-id="e6397-103">Вложенный тип — тип, определенный внутри области другого типа, который называется включающего типа.</span><span class="sxs-lookup"><span data-stu-id="e6397-103">A nested type is a type defined within the scope of another type, which is called the enclosing type.</span></span> <span data-ttu-id="e6397-104">Вложенный тип имеет доступ ко всем членам включающего типа.</span><span class="sxs-lookup"><span data-stu-id="e6397-104">A nested type has access to all members of its enclosing type.</span></span> <span data-ttu-id="e6397-105">Например он имеет доступ к закрытым полям, определенных в включающего типа и защите полей, определенных в всех предков включающего типа.</span><span class="sxs-lookup"><span data-stu-id="e6397-105">For example, it has access to private fields defined in the enclosing type and to protected fields defined in all ascendants of the enclosing type.</span></span>  
  
 <span data-ttu-id="e6397-106">Как правило вложенные типы следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="e6397-106">In general, nested types should be used sparingly.</span></span> <span data-ttu-id="e6397-107">Для этого есть несколько причин.</span><span class="sxs-lookup"><span data-stu-id="e6397-107">There are several reasons for this.</span></span> <span data-ttu-id="e6397-108">Некоторые разработчики не полностью знакомы с этой концепцией.</span><span class="sxs-lookup"><span data-stu-id="e6397-108">Some developers are not fully familiar with the concept.</span></span> <span data-ttu-id="e6397-109">Эти разработчики например, возможно, проблемы с синтаксисом объявления переменных вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="e6397-109">These developers might, for example, have problems with the syntax of declaring variables of nested types.</span></span> <span data-ttu-id="e6397-110">Вложенные типы, которые также очень тесно связаны с их заключенных типов и таким образом, не подходят для типа общего назначения.</span><span class="sxs-lookup"><span data-stu-id="e6397-110">Nested types are also very tightly coupled with their enclosing types, and as such are not suited to be general-purpose types.</span></span>  
  
 <span data-ttu-id="e6397-111">Вложенные типы лучше всего подходят для моделирования сведения о реализации их заключенных типов.</span><span class="sxs-lookup"><span data-stu-id="e6397-111">Nested types are best suited for modeling implementation details of their enclosing types.</span></span> <span data-ttu-id="e6397-112">Конечному пользователю не придется объявлять переменные вложенного типа и практически никогда не должны иметь явно создать экземпляр вложенные типы.</span><span class="sxs-lookup"><span data-stu-id="e6397-112">The end user should rarely have to declare variables of a nested type and almost never should have to explicitly instantiate nested types.</span></span> <span data-ttu-id="e6397-113">Например перечислитель коллекции может быть вложенным типом этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="e6397-113">For example, the enumerator of a collection can be a nested type of that collection.</span></span> <span data-ttu-id="e6397-114">Перечислители обычно создаются с содержащим их типом, а поскольку многие языки поддерживают оператор foreach, перечислитель переменные редко приходится объявляться конечным пользователем.</span><span class="sxs-lookup"><span data-stu-id="e6397-114">Enumerators are usually instantiated by their enclosing type, and because many languages support the foreach statement, enumerator variables rarely have to be declared by the end user.</span></span>  
  
 <span data-ttu-id="e6397-115">**✓ DO** используйте вложенные типы, когда отношения между вложенным типом и его внешним типом таким образом, что желательна семантика доступности члена.</span><span class="sxs-lookup"><span data-stu-id="e6397-115">**✓ DO** use nested types when the relationship between the nested type and its outer type is such that member-accessibility semantics are desirable.</span></span>  
  
 <span data-ttu-id="e6397-116">**X DO NOT** используйте открытые вложенные типы как логическое группирование создания; использовать для данного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e6397-116">**X DO NOT** use public nested types as a logical grouping construct; use namespaces for this.</span></span>  
  
 <span data-ttu-id="e6397-117">**X AVOID** открытым вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="e6397-117">**X AVOID** publicly exposed nested types.</span></span> <span data-ttu-id="e6397-118">Единственным исключением из этого является то, если переменные вложенного типа должны быть объявлены только в редких случаях, таких как работа с подклассами и других сценариев расширенной настройки.</span><span class="sxs-lookup"><span data-stu-id="e6397-118">The only exception to this is if variables of the nested type need to be declared only in rare scenarios such as subclassing or other advanced customization scenarios.</span></span>  
  
 <span data-ttu-id="e6397-119">**X DO NOT** используйте вложенные типы, если тип может ссылаться на за пределами содержащего типа.</span><span class="sxs-lookup"><span data-stu-id="e6397-119">**X DO NOT** use nested types if the type is likely to be referenced outside of the containing type.</span></span>  
  
 <span data-ttu-id="e6397-120">Например передается в метод, определенный в классе перечисления не должны будут определяться как вложенного типа в классе.</span><span class="sxs-lookup"><span data-stu-id="e6397-120">For example, an enum passed to a method defined on a class should not be defined as a nested type in the class.</span></span>  
  
 <span data-ttu-id="e6397-121">**X DO NOT** используйте вложенные типы, если они должны создаваться в клиентском коде.</span><span class="sxs-lookup"><span data-stu-id="e6397-121">**X DO NOT** use nested types if they need to be instantiated by client code.</span></span>  <span data-ttu-id="e6397-122">Если тип имеет открытый конструктор, он скорее всего, не должен быть вложенным.</span><span class="sxs-lookup"><span data-stu-id="e6397-122">If a type has a public constructor, it should probably not be nested.</span></span>  
  
 <span data-ttu-id="e6397-123">Если тип может быть создан, видимо, чтобы указать тип имеет место в framework сама по себе (можно создать ее, работать с ними и уничтожать без когда-либо с помощью внешнего типа) и поэтому не должен быть вложенным.</span><span class="sxs-lookup"><span data-stu-id="e6397-123">If a type can be instantiated, that seems to indicate the type has a place in the framework on its own (you can create it, work with it, and destroy it without ever using the outer type), and thus should not be nested.</span></span> <span data-ttu-id="e6397-124">Внутренние типы не должны широко использоваться за пределами внешнего типа без связи ни при каких обстоятельствах для внешнего типа.</span><span class="sxs-lookup"><span data-stu-id="e6397-124">Inner types should not be widely reused outside of the outer type without any relationship whatsoever to the outer type.</span></span>  
  
 <span data-ttu-id="e6397-125">**X DO NOT** определить вложенный тип в качестве члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e6397-125">**X DO NOT** define a nested type as a member of an interface.</span></span> <span data-ttu-id="e6397-126">Такая конструкция не поддерживают многие языки.</span><span class="sxs-lookup"><span data-stu-id="e6397-126">Many languages do not support such a construct.</span></span>  
  
 <span data-ttu-id="e6397-127">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="e6397-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e6397-128">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e6397-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6397-129">См. также</span><span class="sxs-lookup"><span data-stu-id="e6397-129">See also</span></span>

- [<span data-ttu-id="e6397-130">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="e6397-130">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="e6397-131">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="e6397-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
