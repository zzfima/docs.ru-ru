---
title: "Правила разработки типов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6b02abef0180b6de82e26837863849cce35c994f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="type-design-guidelines"></a><span data-ttu-id="0c4e5-102">Правила разработки типов</span><span class="sxs-lookup"><span data-stu-id="0c4e5-102">Type Design Guidelines</span></span>
<span data-ttu-id="0c4e5-103">С точки зрения среды CLR, есть только две категории типов — ссылочные типы и типы значений, но с целью обсуждение разработки решений, типы разделен на несколько логических групп, каждая из которых собственные правила по разработке.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="0c4e5-104">Классы являются общем случае ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="0c4e5-105">Они составляют большую часть типов в большинстве платформ.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="0c4e5-106">Классы причитающихся их популярность набор объектно ориентированные возможности, которые они поддерживают широкий набор функций и их общие применимости.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="0c4e5-107">Базовые классы и абстрактные классы представляют собой специальные логические группы, относящиеся к расширяемости.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="0c4e5-108">Интерфейсы — это типы, которые могут быть реализованы, ссылочные типы и типы значений.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="0c4e5-109">Таким образом они могут служить корни полиморфного иерархий ссылочных типов и типов значений.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="0c4e5-110">Кроме того интерфейсы могут использоваться для моделирования множественное наследование, который изначально не поддерживается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="0c4e5-111">Структуры являются общем случае, когда типы значений и следует зарезервировать для маленькие, простые типы, аналогично примитивы языка.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="0c4e5-112">Перечисления являются особым случаем типы значений, используемые для определения наборов коротких значений, таких как дни недели, цвета консоли и т. д.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="0c4e5-113">Статические классы являются типами, которые предполагается использовать контейнеры для статических элементов.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="0c4e5-114">Обычно они используются для предоставления ярлыки для других операций.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="0c4e5-115">Делегаты, исключения, атрибуты, массивы и коллекции являются все особых случаях ссылочных типов, предназначенных для конкретных целей, и рекомендации по их проектированию и использованию обсуждаются в другом месте в этой книге.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="0c4e5-116">**✓ СДЕЛАТЬ** убедитесь, что каждый тип четко определенный набор связанных элементов не только случайных коллекции другие функции.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0c4e5-117">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0c4e5-117">In This Section</span></span>  
 [<span data-ttu-id="0c4e5-118">Выбор между классом и структурой</span><span class="sxs-lookup"><span data-stu-id="0c4e5-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="0c4e5-119">Разработка абстрактных классов</span><span class="sxs-lookup"><span data-stu-id="0c4e5-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="0c4e5-120">Разработка статических классов</span><span class="sxs-lookup"><span data-stu-id="0c4e5-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="0c4e5-121">Разработка интерфейса</span><span class="sxs-lookup"><span data-stu-id="0c4e5-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="0c4e5-122">Разработка структур</span><span class="sxs-lookup"><span data-stu-id="0c4e5-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="0c4e5-123">Разработка перечислений</span><span class="sxs-lookup"><span data-stu-id="0c4e5-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="0c4e5-124">Вложенные типы</span><span class="sxs-lookup"><span data-stu-id="0c4e5-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="0c4e5-125">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="0c4e5-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0c4e5-126">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="0c4e5-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c4e5-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0c4e5-127">See Also</span></span>  
 [<span data-ttu-id="0c4e5-128">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="0c4e5-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
