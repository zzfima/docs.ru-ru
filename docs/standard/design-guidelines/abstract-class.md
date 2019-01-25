---
title: Разработка абстрактных классов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: KrzysztofCwalina
ms.openlocfilehash: 6eec3bb4575b89c6476e6c3410050c705141777f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550419"
---
# <a name="abstract-class-design"></a><span data-ttu-id="0465e-102">Разработка абстрактных классов</span><span class="sxs-lookup"><span data-stu-id="0465e-102">Abstract Class Design</span></span>
<span data-ttu-id="0465e-103">**X DO NOT** определение открытого или защищенного внутреннего конструкторов в абстрактных типов.</span><span class="sxs-lookup"><span data-stu-id="0465e-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="0465e-104">Конструкторы должны быть открытым, только в том случае, если пользователи должны будут создавать экземпляры типа.</span><span class="sxs-lookup"><span data-stu-id="0465e-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="0465e-105">Так как нельзя создавать экземпляры абстрактного типа, абстрактный тип с открытым конструктором неправильно спроектированных и вводит в заблуждение пользователей.</span><span class="sxs-lookup"><span data-stu-id="0465e-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="0465e-106">**✓ DO** Определите защищенный или внутренний конструктор в абстрактных классах.</span><span class="sxs-lookup"><span data-stu-id="0465e-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="0465e-107">Защищенный конструктор чаще и просто позволяет базового класса, чтобы сделать свой собственный инициализации при создании подтипов.</span><span class="sxs-lookup"><span data-stu-id="0465e-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="0465e-108">Внутренний конструктор можно использовать для ограничения конкретные реализации абстрактного класса для сборки, определяющей класс.</span><span class="sxs-lookup"><span data-stu-id="0465e-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="0465e-109">**✓ DO** укажите по крайней мере один конкретный тип, наследующий от каждого абстрактный класс, который можно отправить.</span><span class="sxs-lookup"><span data-stu-id="0465e-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="0465e-110">Это помогает проверить архитектуру абстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="0465e-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="0465e-111">Например <xref:System.IO.FileStream?displayProperty=nameWithType> представляет собой реализацию <xref:System.IO.Stream?displayProperty=nameWithType> абстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="0465e-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="0465e-112">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="0465e-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0465e-113">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="0465e-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0465e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0465e-114">See also</span></span>

- [<span data-ttu-id="0465e-115">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="0465e-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="0465e-116">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="0465e-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
