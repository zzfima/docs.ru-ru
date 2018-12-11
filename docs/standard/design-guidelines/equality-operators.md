---
title: Операторы равенства
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: KrzysztofCwalina
ms.openlocfilehash: ae188fc7cd55dd843e93afccbe1ea05575a9c36d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129081"
---
# <a name="equality-operators"></a><span data-ttu-id="76652-102">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="76652-102">Equality Operators</span></span>
<span data-ttu-id="76652-103">В этом разделе обсуждаются перегрузка операторов равенства и ссылается на `operator==` и `operator!=` как операторы равенства.</span><span class="sxs-lookup"><span data-stu-id="76652-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="76652-104">**X DO NOT** перегружать операторы равенства и недоступны в другом.</span><span class="sxs-lookup"><span data-stu-id="76652-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="76652-105">**✓ DO** убедитесь, что <xref:System.Object.Equals%2A?displayProperty=nameWithType> и операторы равенства точно совпадает с семантикой и сходными характеристиками производительности.</span><span class="sxs-lookup"><span data-stu-id="76652-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="76652-106">Это часто означает, что `Object.Equals` должен быть переопределен, если операторы равенства являются перегруженными.</span><span class="sxs-lookup"><span data-stu-id="76652-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="76652-107">**X AVOID** создание исключений из операторов равенства.</span><span class="sxs-lookup"><span data-stu-id="76652-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="76652-108">Например, возвращают значение false, если один из аргументов имеет значение null, а не вызывает `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="76652-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="76652-109">Операторы равенства для типов значений</span><span class="sxs-lookup"><span data-stu-id="76652-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="76652-110">**✓ DO** перегружать операторы равенства для типов значений, если равенство является значимым.</span><span class="sxs-lookup"><span data-stu-id="76652-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="76652-111">В большинстве языков программирования, имеется реализация по умолчанию не `operator==` для типов значений.</span><span class="sxs-lookup"><span data-stu-id="76652-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="76652-112">Операторы равенства для ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="76652-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="76652-113">**X AVOID** перегрузка операторов равенства на изменяемые ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="76652-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="76652-114">Во многих языках применяются операторы встроенные равенства для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="76652-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="76652-115">Встроенные операторы обычно реализуют равенство ссылок и многие разработчики удивлен, когда поведение по умолчанию изменяется на равенство значений.</span><span class="sxs-lookup"><span data-stu-id="76652-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="76652-116">Эта проблема уменьшается для неизменяемого ссылочных типов, поскольку неизменность затруднит Обратите внимание на различие между ссылочным равенством и равенства значений.</span><span class="sxs-lookup"><span data-stu-id="76652-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="76652-117">**X AVOID** перегрузка операторов равенства для ссылочных типов, если реализация будет значительно медленнее, чем, равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="76652-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="76652-118">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="76652-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="76652-119">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="76652-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76652-120">См. также</span><span class="sxs-lookup"><span data-stu-id="76652-120">See also</span></span>

- [<span data-ttu-id="76652-121">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="76652-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="76652-122">Правила использования</span><span class="sxs-lookup"><span data-stu-id="76652-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
