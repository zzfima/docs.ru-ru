---
title: Обычные шаблоны разработки
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- design patterns in class libraries
- class library design guidelines [.NET Framework], design patterns
ms.assetid: f7bd1361-4ab2-4132-972d-a044b8f197e1
ms.openlocfilehash: 2c51b1c9bc970d6ff143fa5986eade4a8b69f25a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709508"
---
# <a name="common-design-patterns"></a><span data-ttu-id="270c5-102">Обычные шаблоны разработки</span><span class="sxs-lookup"><span data-stu-id="270c5-102">Common Design Patterns</span></span>
<span data-ttu-id="270c5-103">Существует множество книг по шаблонам программного обеспечения, языкам шаблонов и антишаблонам, направленным на очень обширную тему шаблонов.</span><span class="sxs-lookup"><span data-stu-id="270c5-103">There are numerous books on software patterns, pattern languages, and antipatterns that address the very broad subject of patterns.</span></span> <span data-ttu-id="270c5-104">Поэтому в этой главе приводятся рекомендации и обсуждение, связанное с очень ограниченным набором шаблонов, которые часто используются в проектировании API-интерфейсов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="270c5-104">Thus, this chapter provides guidelines and discussion related to a very limited set of patterns that are used frequently in the design of the .NET Framework APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="270c5-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="270c5-105">In This Section</span></span>  
 [<span data-ttu-id="270c5-106">Свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="270c5-106">Dependency Properties</span></span>](../../../docs/standard/design-guidelines/dependency-properties.md)  
 [<span data-ttu-id="270c5-107">Шаблон ликвидации</span><span class="sxs-lookup"><span data-stu-id="270c5-107">Dispose Pattern</span></span>](../garbage-collection/implementing-dispose.md)  
 <span data-ttu-id="270c5-108">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="270c5-108">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="270c5-109">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="270c5-109">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="270c5-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="270c5-110">See also</span></span>

- [<span data-ttu-id="270c5-111">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="270c5-111">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
