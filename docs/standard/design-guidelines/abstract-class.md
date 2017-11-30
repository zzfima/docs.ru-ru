---
title: "Разработка абстрактных классов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d7b680c3377cbfa40734a57f9408d9487dbf3769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="abstract-class-design"></a><span data-ttu-id="be456-102">Разработка абстрактных классов</span><span class="sxs-lookup"><span data-stu-id="be456-102">Abstract Class Design</span></span>
<span data-ttu-id="be456-103">**X не** определение открытого или защищенного внутреннего конструкторов в абстрактных типов.</span><span class="sxs-lookup"><span data-stu-id="be456-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="be456-104">Конструкторы должны быть открытыми, только в том случае, если пользователи должны будут создавать экземпляры типа.</span><span class="sxs-lookup"><span data-stu-id="be456-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="be456-105">Так как невозможно создавать экземпляры абстрактного типа, абстрактный тип с открытым конструктором неправильно предназначена и ввести в заблуждение пользователей.</span><span class="sxs-lookup"><span data-stu-id="be456-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="be456-106">**✓ СДЕЛАТЬ** Определите защищенный или внутренний конструктор в абстрактных классах.</span><span class="sxs-lookup"><span data-stu-id="be456-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="be456-107">Защищенный конструктор, чаще всего и просто позволяет базового класса, чтобы сделать свои собственные инициализации при создании подтипы.</span><span class="sxs-lookup"><span data-stu-id="be456-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="be456-108">Внутренний конструктор используется для ограничения конкретные реализации абстрактного класса для сборки, определяющей класс.</span><span class="sxs-lookup"><span data-stu-id="be456-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="be456-109">**✓ СДЕЛАТЬ** укажите по крайней мере один конкретный тип, наследующий от каждого абстрактный класс, который можно отправить.</span><span class="sxs-lookup"><span data-stu-id="be456-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="be456-110">Это помогает проверить конструктора абстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="be456-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="be456-111">Например <xref:System.IO.FileStream?displayProperty=nameWithType> — это реализация <xref:System.IO.Stream?displayProperty=nameWithType> абстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="be456-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="be456-112">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="be456-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="be456-113">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="be456-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be456-114">См. также</span><span class="sxs-lookup"><span data-stu-id="be456-114">See Also</span></span>  
 [<span data-ttu-id="be456-115">Рекомендации по проектированию типа</span><span class="sxs-lookup"><span data-stu-id="be456-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="be456-116">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="be456-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
