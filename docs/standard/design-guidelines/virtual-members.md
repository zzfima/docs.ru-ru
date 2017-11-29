---
title: "Виртуальные члены"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 56838fc4c1c1e7cb8723beee3f0e6b23515d43f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-members"></a><span data-ttu-id="4a21a-102">Виртуальные члены</span><span class="sxs-lookup"><span data-stu-id="4a21a-102">Virtual Members</span></span>
<span data-ttu-id="4a21a-103">Виртуальные члены могут быть переопределены, таким образом, изменения поведения подкласса.</span><span class="sxs-lookup"><span data-stu-id="4a21a-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="4a21a-104">Они похожи на обратные вызовы с точки зрения расширения, предоставляемых ими, но они являются более высокую производительность выполнения и потребления памяти.</span><span class="sxs-lookup"><span data-stu-id="4a21a-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="4a21a-105">Кроме того виртуальные члены более естественным в случаях, когда требуется создавать специальный вид существующего типа (специализации).</span><span class="sxs-lookup"><span data-stu-id="4a21a-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="4a21a-106">Виртуальные члены работают лучше, чем обратные вызовы и события, но не работают лучше, чем невиртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="4a21a-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="4a21a-107">Главным недостатком виртуальные члены — что поведение виртуальный член может изменяться только во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="4a21a-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="4a21a-108">Поведение обратного вызова можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4a21a-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="4a21a-109">Виртуальные члены, такие как обратные вызовы и может быть несколько обратных вызовов, являются ресурсоемкими для разработки, тестирования и поддерживать, так как каждый вызов виртуальный член может быть переопределен в непредсказуемом виде и могут выполнять произвольный код.</span><span class="sxs-lookup"><span data-stu-id="4a21a-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="4a21a-110">Кроме того четко определить контракт виртуальных членов, поэтому выше стоимость, разработке и документировании их обычно требуется намного больше усилий.</span><span class="sxs-lookup"><span data-stu-id="4a21a-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="4a21a-111">**X не** сделать членами виртуального, если у вас есть веская причина для этого и известно всех расходов, связанных с разработка, тестирование и обслуживание виртуальных членов.</span><span class="sxs-lookup"><span data-stu-id="4a21a-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="4a21a-112">Виртуальные члены являются меньше терпим с точки зрения изменения, которые могут быть выполнены на них без нарушения совместимости.</span><span class="sxs-lookup"><span data-stu-id="4a21a-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="4a21a-113">Кроме того они выполняются медленнее, чем невиртуальные члены, поскольку вызовы виртуальных членов не являются встроенными.</span><span class="sxs-lookup"><span data-stu-id="4a21a-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="4a21a-114">**✓ Попробуйте** ограничение расширяемости для только что это действительно необходимо.</span><span class="sxs-lookup"><span data-stu-id="4a21a-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="4a21a-115">**✓ СДЕЛАТЬ** использовать защищенный открытый доступ для виртуальных членов.</span><span class="sxs-lookup"><span data-stu-id="4a21a-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="4a21a-116">Открытые члены должны предоставлять возможность расширения (если это необходимо), вызывая защищенных виртуальных членов.</span><span class="sxs-lookup"><span data-stu-id="4a21a-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="4a21a-117">Открытые члены класса правильный набор функциональных возможностей обеспечения прямой потребителям этого класса.</span><span class="sxs-lookup"><span data-stu-id="4a21a-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="4a21a-118">Виртуальные члены предназначены для переопределения в подклассах и защищенный является хорошим способом для определения области все расширения виртуального точки, в которых они могут использоваться.</span><span class="sxs-lookup"><span data-stu-id="4a21a-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="4a21a-119">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="4a21a-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4a21a-120">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4a21a-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a21a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="4a21a-121">See Also</span></span>  
 [<span data-ttu-id="4a21a-122">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="4a21a-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="4a21a-123">Разработка для расширяемости</span><span class="sxs-lookup"><span data-stu-id="4a21a-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
