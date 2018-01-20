---
title: "Рекомендации по разработке платформы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c48b3cbaae4155a894ba77263505b2ca85238427
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="ef603-102">Рекомендации по разработке платформы</span><span class="sxs-lookup"><span data-stu-id="ef603-102">Framework Design Guidelines</span></span>
<span data-ttu-id="ef603-103">Этот раздел содержит рекомендации по разработке библиотек, которые расширяют и взаимодействия с платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ef603-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="ef603-104">Цель — помочь разработчикам библиотек гарантировать согласованность API и удобства использования, предоставляя унифицированную модель программирования, не зависящий от языка программирования, который используется для разработки.</span><span class="sxs-lookup"><span data-stu-id="ef603-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="ef603-105">Корпорация Майкрософт рекомендует следовать этим правилам при разработке классов и компонентов, расширяющих возможности .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ef603-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="ef603-106">Несогласованные библиотеки конструктора отрицательно влияет на производительность и не рекомендует внедрения.</span><span class="sxs-lookup"><span data-stu-id="ef603-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="ef603-107">Правила организованы в виде простых рекомендаций, префиксом с условиями `Do`, `Consider`, `Avoid`, и `Do not`.</span><span class="sxs-lookup"><span data-stu-id="ef603-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="ef603-108">Эти рекомендации должны помочь разработчикам библиотек классов понять компромиссы между разными решениями.</span><span class="sxs-lookup"><span data-stu-id="ef603-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="ef603-109">Может возникнуть ситуация, где хорошо спроектированной библиотеки требуется нарушение этим правилам.</span><span class="sxs-lookup"><span data-stu-id="ef603-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="ef603-110">Такие случаи должны быть редкими, и важно, нет причин и привлекательны для такого решения.</span><span class="sxs-lookup"><span data-stu-id="ef603-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="ef603-111">Эти правила являются отрывок из книги *Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание*, Krzysztof Cwalina и Брэд Абрамс.</span><span class="sxs-lookup"><span data-stu-id="ef603-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef603-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ef603-112">In This Section</span></span>  
 [<span data-ttu-id="ef603-113">Правила именования</span><span class="sxs-lookup"><span data-stu-id="ef603-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="ef603-114">Рекомендации по именованию сборок, пространств имен, типов и членов в библиотеках классов.</span><span class="sxs-lookup"><span data-stu-id="ef603-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="ef603-115">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="ef603-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="ef603-116">Инструкции по использованию статических и абстрактных классов, интерфейсов, перечислений, структур и других типов.</span><span class="sxs-lookup"><span data-stu-id="ef603-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="ef603-117">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="ef603-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="ef603-118">Содержит рекомендации по разработке и использовании свойства, методы, конструкторы, поля, события, операторы и параметры.</span><span class="sxs-lookup"><span data-stu-id="ef603-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="ef603-119">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="ef603-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="ef603-120">Описывает механизмы расширяемости, таких как создание подклассов, с помощью событий, виртуальные члены и обратные вызовы и объясняется, как выбрать механизмов, которые лучше всего соответствует требованиям вашей платформы.</span><span class="sxs-lookup"><span data-stu-id="ef603-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="ef603-121">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="ef603-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="ef603-122">Описывает рекомендации по проектированию для разработки, создания и перехвата исключений.</span><span class="sxs-lookup"><span data-stu-id="ef603-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="ef603-123">Правила использования</span><span class="sxs-lookup"><span data-stu-id="ef603-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="ef603-124">Описывает правила использования общих типов, таких как массивы, атрибуты и коллекции, поддерживающих сериализацию и перегрузка операторов равенства.</span><span class="sxs-lookup"><span data-stu-id="ef603-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="ef603-125">Обычные шаблоны разработки</span><span class="sxs-lookup"><span data-stu-id="ef603-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="ef603-126">Рекомендации по выбору и реализации шаблона удаления и свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ef603-126">Provides guidelines for choosing and implementing dependency properties and the dispose pattern.</span></span>  
  
 <span data-ttu-id="ef603-127">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="ef603-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ef603-128">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="ef603-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef603-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ef603-129">See Also</span></span>  
 [<span data-ttu-id="ef603-130">Обзор набора средств Visual Studio для Unity</span><span class="sxs-lookup"><span data-stu-id="ef603-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)  
 [<span data-ttu-id="ef603-131">Стратегия для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ef603-131">Roadmap for the .NET Framework</span></span>](http://msdn.microsoft.com/library/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
 [<span data-ttu-id="ef603-132">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="ef603-132">Development Guide</span></span>](../../../docs/framework/development-guide.md)
