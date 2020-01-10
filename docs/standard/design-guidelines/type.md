---
title: Правила разработки типов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
ms.openlocfilehash: 3e2fe7168bd0029d8f0e8f69a136c9089032973f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709027"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="428fb-102">Правила разработки типов</span><span class="sxs-lookup"><span data-stu-id="428fb-102">Type Design Guidelines</span></span>
<span data-ttu-id="428fb-103">С точки зрения среды CLR существует только две категории типов — ссылочные типы и типы значений, но в целях обсуждения структуры платформы мы разделены на несколько логических групп, каждый из которых имеет собственные собственные правила проектирования.</span><span class="sxs-lookup"><span data-stu-id="428fb-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="428fb-104">Классы являются общими вариантами ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="428fb-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="428fb-105">Они составляют большую часть типов в большинстве платформ.</span><span class="sxs-lookup"><span data-stu-id="428fb-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="428fb-106">Классы заменяют популярность до обширного набора объектно-ориентированных функций, которые они поддерживают, и их общей применимости.</span><span class="sxs-lookup"><span data-stu-id="428fb-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="428fb-107">Базовые классы и абстрактные классы — это специальные логические группы, связанные с расширяемостью.</span><span class="sxs-lookup"><span data-stu-id="428fb-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="428fb-108">Интерфейсы — это типы, которые могут быть реализованы как ссылочными типами, так и типами значений.</span><span class="sxs-lookup"><span data-stu-id="428fb-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="428fb-109">Таким образом, они служат в качестве корней для однозначных иерархий ссылочных типов и типов значений.</span><span class="sxs-lookup"><span data-stu-id="428fb-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="428fb-110">Кроме того, интерфейсы можно использовать для моделирования множественного наследования, которое изначально не поддерживается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="428fb-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="428fb-111">Структуры являются общими вариантами типов значений и должны быть зарезервированы для небольших простых типов, аналогичных примитивам языка.</span><span class="sxs-lookup"><span data-stu-id="428fb-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="428fb-112">Перечисления — это особый случай типов значений, используемых для определения коротких наборов значений, таких как дни недели, цвета консоли и т. д.</span><span class="sxs-lookup"><span data-stu-id="428fb-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="428fb-113">Статические классы — это типы, предназначенные для контейнеров для статических членов.</span><span class="sxs-lookup"><span data-stu-id="428fb-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="428fb-114">Они обычно используются для предоставления сочетаний клавиш для других операций.</span><span class="sxs-lookup"><span data-stu-id="428fb-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="428fb-115">Делегаты, исключения, атрибуты, массивы и коллекции являются специальными вариантами ссылочных типов, предназначенных для определенных целей, а рекомендации по их проектированию и использованию обсуждаются в других местах этой книги.</span><span class="sxs-lookup"><span data-stu-id="428fb-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="428fb-116">**✓ DO** убедитесь, что каждый тип четко определенный набор связанных элементов не только случайных коллекции другие функции.</span><span class="sxs-lookup"><span data-stu-id="428fb-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="428fb-117">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="428fb-117">In This Section</span></span>  
 [<span data-ttu-id="428fb-118">Выбор между классом и структурой</span><span class="sxs-lookup"><span data-stu-id="428fb-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="428fb-119">Разработка абстрактных классов</span><span class="sxs-lookup"><span data-stu-id="428fb-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="428fb-120">Разработка статических классов</span><span class="sxs-lookup"><span data-stu-id="428fb-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="428fb-121">Разработка интерфейса</span><span class="sxs-lookup"><span data-stu-id="428fb-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="428fb-122">Разработка структур</span><span class="sxs-lookup"><span data-stu-id="428fb-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="428fb-123">Разработка перечислений</span><span class="sxs-lookup"><span data-stu-id="428fb-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="428fb-124">Вложенные типы</span><span class="sxs-lookup"><span data-stu-id="428fb-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="428fb-125">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="428fb-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="428fb-126">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="428fb-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="428fb-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="428fb-127">See also</span></span>

- [<span data-ttu-id="428fb-128">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="428fb-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
