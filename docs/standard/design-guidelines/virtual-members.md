---
title: Виртуальные члены
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92b648e7886fb0214238e32eacae2870b470340
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46006332"
---
# <a name="virtual-members"></a><span data-ttu-id="64302-102">Виртуальные члены</span><span class="sxs-lookup"><span data-stu-id="64302-102">Virtual Members</span></span>
<span data-ttu-id="64302-103">Виртуальные члены можно переопределить, таким образом изменение поведения подкласса.</span><span class="sxs-lookup"><span data-stu-id="64302-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="64302-104">Они похожи на обратные вызовы с точки зрения расширяемости, которые они выполняют, но они лучше с точки зрения производительности и потребления памяти.</span><span class="sxs-lookup"><span data-stu-id="64302-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="64302-105">Кроме того виртуальные члены показаться более естественной, в сценариях, когда требуется создавать специальный вид существующего типа (специализации).</span><span class="sxs-lookup"><span data-stu-id="64302-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="64302-106">Виртуальные члены работают лучше, чем обратные вызовы и события, но не работают лучше, чем невиртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="64302-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="64302-107">Главным недостатком виртуальных членов является то, что поведение виртуального члена можно изменить только во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="64302-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="64302-108">Поведение обратного вызова можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="64302-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="64302-109">Виртуальные члены, такие как обратные вызовы (и может быть больше, чем обратных вызовов), довольно сложно проектирование, тестирование и обслуживание, поскольку каждый вызов виртуального члена можно переопределить в непредсказуемом виде и могут выполнять произвольный код.</span><span class="sxs-lookup"><span data-stu-id="64302-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="64302-110">Кроме того гораздо больше усилий обычно требуется четко определить контракт виртуальные члены, поэтому затраты на проектирование и документирование их более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="64302-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="64302-111">**X DO NOT** сделать членами виртуального, если у вас есть веская причина для этого и известно всех расходов, связанных с разработка, тестирование и обслуживание виртуальных членов.</span><span class="sxs-lookup"><span data-stu-id="64302-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="64302-112">Виртуальные члены являются меньше терпим с точки зрения изменения, которые можно применить к ним без риска нарушить совместимость.</span><span class="sxs-lookup"><span data-stu-id="64302-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="64302-113">Кроме того они медленнее, чем невиртуальные члены, главным образом потому, что вызовы виртуальных членов не являются встроенными.</span><span class="sxs-lookup"><span data-stu-id="64302-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="64302-114">**✓ CONSIDER** ограничение расширяемости для только что это действительно необходимо.</span><span class="sxs-lookup"><span data-stu-id="64302-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="64302-115">**✓ DO** использовать защищенный открытый доступ для виртуальных членов.</span><span class="sxs-lookup"><span data-stu-id="64302-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="64302-116">Открытые члены должны предоставлять возможность расширения (при необходимости), вызывая защищенный виртуальный член.</span><span class="sxs-lookup"><span data-stu-id="64302-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="64302-117">Открытые члены класса правильный набор функций обеспечения прямой потребители этого класса.</span><span class="sxs-lookup"><span data-stu-id="64302-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="64302-118">Виртуальные члены предназначены для переопределения в подклассы и защищенный — отличный способ определить область все точки виртуального расширения, где они могут использоваться.</span><span class="sxs-lookup"><span data-stu-id="64302-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="64302-119">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="64302-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="64302-120">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="64302-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64302-121">См. также</span><span class="sxs-lookup"><span data-stu-id="64302-121">See also</span></span>

- [<span data-ttu-id="64302-122">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="64302-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="64302-123">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="64302-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
