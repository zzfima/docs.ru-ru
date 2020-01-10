---
title: Разработка с обеспечением расширяемости
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: cd5db2d1e299df1b3d0f706ebc507e6855b72505
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709469"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="747df-102">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="747df-102">Designing for Extensibility</span></span>
<span data-ttu-id="747df-103">Одним из важных аспектов разработки платформы является обеспечение тщательного рассмотрения расширяемости платформы.</span><span class="sxs-lookup"><span data-stu-id="747df-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="747df-104">Для этого необходимо понимать затраты и преимущества, связанные с различными механизмами расширения.</span><span class="sxs-lookup"><span data-stu-id="747df-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="747df-105">Эта глава поможет вам решить, какие механизмы расширения (подклассы, события, виртуальные члены, обратные вызовы и т. д.) лучше удовлетворять требованиям вашей инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="747df-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="747df-106">Существует множество способов разрешить расширяемость в платформах.</span><span class="sxs-lookup"><span data-stu-id="747df-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="747df-107">Они находятся в диапазоне от менее мощных, но менее дорогостоящих к очень мощным, но дорогостоящим.</span><span class="sxs-lookup"><span data-stu-id="747df-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="747df-108">Для любого конкретного требования к расширяемости следует выбрать наиболее дорогостоящий механизм расширяемости, соответствующий требованиям.</span><span class="sxs-lookup"><span data-stu-id="747df-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="747df-109">Помните, что обычно можно добавить дополнительную расширяемость, но вы никогда не сможете отказаться от внесения критических изменений.</span><span class="sxs-lookup"><span data-stu-id="747df-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="747df-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="747df-110">In This Section</span></span>  
 [<span data-ttu-id="747df-111">Незапечатанные классы</span><span class="sxs-lookup"><span data-stu-id="747df-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="747df-112">Защищенные члены</span><span class="sxs-lookup"><span data-stu-id="747df-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="747df-113">События и обратные вызовы</span><span class="sxs-lookup"><span data-stu-id="747df-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="747df-114">Виртуальные члены</span><span class="sxs-lookup"><span data-stu-id="747df-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="747df-115">Абстракции (абстрактные типы и интерфейсы)</span><span class="sxs-lookup"><span data-stu-id="747df-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="747df-116">Базовые классы для реализации абстракций</span><span class="sxs-lookup"><span data-stu-id="747df-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="747df-117">Запечатывание</span><span class="sxs-lookup"><span data-stu-id="747df-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="747df-118">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="747df-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="747df-119">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="747df-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="747df-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="747df-120">See also</span></span>

- [<span data-ttu-id="747df-121">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="747df-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
