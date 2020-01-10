---
title: Рекомендации по разработке платформы
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 623391de63891c1695a63482a424bb76a861deba
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709313"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="e35d6-102">Рекомендации по разработке платформы</span><span class="sxs-lookup"><span data-stu-id="e35d6-102">Framework Design Guidelines</span></span>
<span data-ttu-id="e35d6-103">В этом разделе приводятся рекомендации по проектированию библиотек, которые расширяют и взаимодействуют с .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e35d6-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="e35d6-104">Цель состоит в том, чтобы помочь дизайнерам библиотек обеспечить согласованность и простоту использования API, предоставляя унифицированную модель программирования, которая не зависит от языка программирования, используемого для разработки.</span><span class="sxs-lookup"><span data-stu-id="e35d6-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="e35d6-105">При разработке классов и компонентов, расширяющих .NET Framework, рекомендуется следовать этим рекомендациям по проектированию.</span><span class="sxs-lookup"><span data-stu-id="e35d6-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="e35d6-106">Непоследовательная структура библиотеки негативно влияет на производительность разработки и не дорекомендует внедрения.</span><span class="sxs-lookup"><span data-stu-id="e35d6-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="e35d6-107">Рекомендации организованы в виде простых рекомендаций с префиксами `Do`, `Consider`, `Avoid`и `Do not`.</span><span class="sxs-lookup"><span data-stu-id="e35d6-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="e35d6-108">Эти рекомендации предназначены для того, чтобы помочь дизайнерам библиотек классов понять компромиссы между различными решениями.</span><span class="sxs-lookup"><span data-stu-id="e35d6-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="e35d6-109">Возможны ситуации, когда хорошая структура библиотеки требует соблюдения этих рекомендаций по проектированию.</span><span class="sxs-lookup"><span data-stu-id="e35d6-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="e35d6-110">Такие случаи должны быть редкими, и важно иметь четкие и интересные причины для принятия решения.</span><span class="sxs-lookup"><span data-stu-id="e35d6-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="e35d6-111">Эти рекомендации взяты из *руководства по проектированию для платформы книги: соглашения, идиомы и закономерности для многократно используемых библиотек .NET, 2-го выпуска*, Крзисзтоф Квалина и Михаил Abrams).</span><span class="sxs-lookup"><span data-stu-id="e35d6-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e35d6-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e35d6-112">In This Section</span></span>  
 [<span data-ttu-id="e35d6-113">Правила именования</span><span class="sxs-lookup"><span data-stu-id="e35d6-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="e35d6-114">Содержит рекомендации по именованию сборок, пространств имен, типов и членов в библиотеках классов.</span><span class="sxs-lookup"><span data-stu-id="e35d6-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="e35d6-115">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="e35d6-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="e35d6-116">Содержит рекомендации по использованию статических и абстрактных классов, интерфейсов, перечислений, структур и других типов.</span><span class="sxs-lookup"><span data-stu-id="e35d6-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="e35d6-117">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="e35d6-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="e35d6-118">Содержит рекомендации по проектированию и использованию свойств, методов, конструкторов, полей, событий, операторов и параметров.</span><span class="sxs-lookup"><span data-stu-id="e35d6-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="e35d6-119">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="e35d6-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="e35d6-120">Обсуждаются механизмы расширения, такие как создание подклассов, использование событий, виртуальные члены и обратные вызовы, а также объясняется, как выбрать механизмы, которые наилучшим образом соответствуют требованиям вашей платформы.</span><span class="sxs-lookup"><span data-stu-id="e35d6-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="e35d6-121">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="e35d6-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="e35d6-122">Описывает рекомендации по проектированию, созданию, генерации и перехвату исключений.</span><span class="sxs-lookup"><span data-stu-id="e35d6-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="e35d6-123">Правила использования</span><span class="sxs-lookup"><span data-stu-id="e35d6-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="e35d6-124">Описывает рекомендации по использованию общих типов, таких как массивы, атрибуты и коллекции, поддержка сериализации и перегрузка операторов равенства.</span><span class="sxs-lookup"><span data-stu-id="e35d6-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="e35d6-125">Обычные шаблоны разработки</span><span class="sxs-lookup"><span data-stu-id="e35d6-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="e35d6-126">Содержит рекомендации по выбору и реализации свойств зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e35d6-126">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="e35d6-127">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="e35d6-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e35d6-128">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e35d6-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e35d6-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="e35d6-129">See also</span></span>

- [<span data-ttu-id="e35d6-130">Обзор</span><span class="sxs-lookup"><span data-stu-id="e35d6-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)
- [<span data-ttu-id="e35d6-131">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="e35d6-131">Development Guide</span></span>](../../../docs/framework/development-guide.md)
