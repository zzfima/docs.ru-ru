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
ms.openlocfilehash: 19482199648a8fb9c4b2c796fb1ab5d62c896abc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709599"
---
# <a name="abstract-class-design"></a><span data-ttu-id="1b6e5-102">Разработка абстрактных классов</span><span class="sxs-lookup"><span data-stu-id="1b6e5-102">Abstract Class Design</span></span>
<span data-ttu-id="1b6e5-103">**X DO NOT** определение открытого или защищенного внутреннего конструкторов в абстрактных типов.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="1b6e5-104">Конструкторы должны быть открытыми только в том случае, если пользователям необходимо создавать экземпляры типа.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="1b6e5-105">Поскольку нельзя создавать экземпляры абстрактного типа, абстрактный тип с открытым конструктором неверно спроектирован и ошибочно ведет себя для пользователей.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="1b6e5-106">**✓ DO** Определите защищенный или внутренний конструктор в абстрактных классах.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="1b6e5-107">Защищенный конструктор является более распространенным и просто позволяет базовому классу выполнять собственную инициализацию при создании подтипов.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="1b6e5-108">Внутренний конструктор можно использовать для ограничения конкретных реализаций абстрактного класса сборкой, определяющей класс.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="1b6e5-109">**✓ DO** укажите по крайней мере один конкретный тип, наследующий от каждого абстрактный класс, который можно отправить.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="1b6e5-110">Это помогает проверить структуру абстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="1b6e5-111">Например, <xref:System.IO.FileStream?displayProperty=nameWithType> является реализацией абстрактного класса <xref:System.IO.Stream?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="1b6e5-112">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="1b6e5-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1b6e5-113">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="1b6e5-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b6e5-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b6e5-114">See also</span></span>

- [<span data-ttu-id="1b6e5-115">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="1b6e5-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="1b6e5-116">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="1b6e5-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
