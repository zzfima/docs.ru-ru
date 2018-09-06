---
title: Правила разработки типов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7fb9964d0e542c0937c55ae65bd88b3f7149fa8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44036029"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="b0d84-102">Правила разработки типов</span><span class="sxs-lookup"><span data-stu-id="b0d84-102">Type Design Guidelines</span></span>
<span data-ttu-id="b0d84-103">С точки зрения среды CLR, есть только две категории типов — ссылочные типы и типы значений, но для целей обсуждения о разработке платформы, мы разделяем типов в более логические группы, каждая из которых собственные правила по разработке.</span><span class="sxs-lookup"><span data-stu-id="b0d84-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="b0d84-104">Классы являются общем случае ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="b0d84-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="b0d84-105">Они составляют основную часть типов в большинстве платформ.</span><span class="sxs-lookup"><span data-stu-id="b0d84-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="b0d84-106">Классы должны их популярность набор объектно ориентированные функции, которые они поддерживают широкий набор функций и их применимость Общие.</span><span class="sxs-lookup"><span data-stu-id="b0d84-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="b0d84-107">Базовые классы и абстрактные классы представляют собой специальные логические группы, связанные с расширяемости.</span><span class="sxs-lookup"><span data-stu-id="b0d84-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="b0d84-108">Интерфейсы являются типами, которые могут быть реализованы, ссылочные типы и типы значений.</span><span class="sxs-lookup"><span data-stu-id="b0d84-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="b0d84-109">Таким образом их можно использовать в качестве корней полиморфных иерархий ссылочных типов и типов значений.</span><span class="sxs-lookup"><span data-stu-id="b0d84-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="b0d84-110">Кроме того интерфейсы можно использовать для имитации множественное наследование, который изначально не поддерживается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="b0d84-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="b0d84-111">Структуры не выполняется, общие для типов значений и следует зарезервировать для небольшие, простые типы, аналогичную примитивов языка.</span><span class="sxs-lookup"><span data-stu-id="b0d84-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="b0d84-112">Перечисления являются особым случаем типы значений, используемые для определения короткий наборов значений, таких как дни недели, цвета консоли и т. д.</span><span class="sxs-lookup"><span data-stu-id="b0d84-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="b0d84-113">Статические классы являются типами, которые должны быть контейнеры для статических элементов.</span><span class="sxs-lookup"><span data-stu-id="b0d84-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="b0d84-114">Обычно они используются для предоставления ярлыки для других операций.</span><span class="sxs-lookup"><span data-stu-id="b0d84-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="b0d84-115">Делегаты, исключения, атрибуты, массивы и коллекции представляют собой все особые случаи ссылочных типов, предназначенные для конкретных целей и рекомендации по их проектированию и использованию обсуждаются в другом месте в этой книге.</span><span class="sxs-lookup"><span data-stu-id="b0d84-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="b0d84-116">**✓ DO** убедитесь, что каждый тип четко определенный набор связанных элементов не только случайных коллекции другие функции.</span><span class="sxs-lookup"><span data-stu-id="b0d84-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0d84-117">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b0d84-117">In This Section</span></span>  
 [<span data-ttu-id="b0d84-118">Выбор между классом и структурой</span><span class="sxs-lookup"><span data-stu-id="b0d84-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="b0d84-119">Разработка абстрактных классов</span><span class="sxs-lookup"><span data-stu-id="b0d84-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="b0d84-120">Разработка статических классов</span><span class="sxs-lookup"><span data-stu-id="b0d84-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="b0d84-121">Разработка интерфейса</span><span class="sxs-lookup"><span data-stu-id="b0d84-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="b0d84-122">Разработка структур</span><span class="sxs-lookup"><span data-stu-id="b0d84-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="b0d84-123">Разработка перечислений</span><span class="sxs-lookup"><span data-stu-id="b0d84-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="b0d84-124">Вложенные типы</span><span class="sxs-lookup"><span data-stu-id="b0d84-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="b0d84-125">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="b0d84-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b0d84-126">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="b0d84-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0d84-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b0d84-127">See also</span></span>

- [<span data-ttu-id="b0d84-128">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="b0d84-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
