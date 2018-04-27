---
title: Разработка с обеспечением расширяемости
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b643c33a1418839c8aabf06d681083232e61553a
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="f4981-102">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="f4981-102">Designing for Extensibility</span></span>
<span data-ttu-id="f4981-103">Проектирование платформу одним важным аспектом является обеспечение внимательно изучить расширяемость такой платформы.</span><span class="sxs-lookup"><span data-stu-id="f4981-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="f4981-104">Это требует понимания издержки и прибыль, связанные с различные механизмы расширения.</span><span class="sxs-lookup"><span data-stu-id="f4981-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="f4981-105">В этой главе помогут решить, какой из механизмов расширения — создания подкласса событий, виртуальные члены, обратные вызовы и т. д, соответствуют требованиям вашей платформы.</span><span class="sxs-lookup"><span data-stu-id="f4981-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="f4981-106">Существует множество способов, чтобы разрешить расширяемости платформы.</span><span class="sxs-lookup"><span data-stu-id="f4981-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="f4981-107">Они в диапазоне от менее мощные, но менее затратным до очень мощные, но дорого.</span><span class="sxs-lookup"><span data-stu-id="f4981-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="f4981-108">Для любого заданного расширяемости требования следует выбирать бы дорогостоящих механизм расширяемости, соответствующий требованиям.</span><span class="sxs-lookup"><span data-stu-id="f4981-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="f4981-109">Имейте в виду, что обычно можно позднее добавить дополнительные расширения, но никогда не позволит немедленно без критических изменений.</span><span class="sxs-lookup"><span data-stu-id="f4981-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4981-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f4981-110">In This Section</span></span>  
 [<span data-ttu-id="f4981-111">Незапечатанные классы</span><span class="sxs-lookup"><span data-stu-id="f4981-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="f4981-112">Защищенные члены</span><span class="sxs-lookup"><span data-stu-id="f4981-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="f4981-113">События и обратные вызовы</span><span class="sxs-lookup"><span data-stu-id="f4981-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="f4981-114">Виртуальные члены</span><span class="sxs-lookup"><span data-stu-id="f4981-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="f4981-115">Абстракции (абстрактные типы и интерфейсы)</span><span class="sxs-lookup"><span data-stu-id="f4981-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="f4981-116">Базовые классы для реализации абстракций</span><span class="sxs-lookup"><span data-stu-id="f4981-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="f4981-117">Запечатывание</span><span class="sxs-lookup"><span data-stu-id="f4981-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="f4981-118">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="f4981-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f4981-119">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f4981-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4981-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f4981-120">See Also</span></span>  
 [<span data-ttu-id="f4981-121">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="f4981-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
