---
title: Операторы равенства
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b1e5784de277d59c7bc945cbe7b605653eec7bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571021"
---
# <a name="equality-operators"></a><span data-ttu-id="090d1-102">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="090d1-102">Equality Operators</span></span>
<span data-ttu-id="090d1-103">В этом разделе обсуждаются перегрузка операторов равенства и ссылается на `operator==` и `operator!=` как операторы равенства.</span><span class="sxs-lookup"><span data-stu-id="090d1-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="090d1-104">**X DO NOT** перегружать операторы равенства и недоступны в другом.</span><span class="sxs-lookup"><span data-stu-id="090d1-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="090d1-105">**✓ DO** убедитесь, что <xref:System.Object.Equals%2A?displayProperty=nameWithType> и операторы равенства точно совпадает с семантикой и сходными характеристиками производительности.</span><span class="sxs-lookup"><span data-stu-id="090d1-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="090d1-106">Это часто означает, что `Object.Equals` должен переопределяться перегруженного операторов равенства.</span><span class="sxs-lookup"><span data-stu-id="090d1-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="090d1-107">**X AVOID** создание исключений из операторов равенства.</span><span class="sxs-lookup"><span data-stu-id="090d1-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="090d1-108">Например, возвращают значение false, если один из аргументов имеет значение null, а не вызывает `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="090d1-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="090d1-109">Операторы равенства для типов значений</span><span class="sxs-lookup"><span data-stu-id="090d1-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="090d1-110">**✓ DO** перегружать операторы равенства для типов значений, если равенство является значимым.</span><span class="sxs-lookup"><span data-stu-id="090d1-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="090d1-111">В большинстве языков программирования, отсутствует реализация по умолчанию из `operator==` для типов значений.</span><span class="sxs-lookup"><span data-stu-id="090d1-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="090d1-112">Операторы равенства для ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="090d1-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="090d1-113">**X AVOID** перегрузка операторов равенства на изменяемые ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="090d1-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="090d1-114">Многие языки имеют операторы встроенных равенства для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="090d1-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="090d1-115">Встроенных операторов, обычно реализуют равенство ссылок и многие разработчики удивлен, когда поведение по умолчанию изменяется на равенство значений.</span><span class="sxs-lookup"><span data-stu-id="090d1-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="090d1-116">Эта проблема устраняется для неизменяемого ссылочных типов так, как неизменность затруднит Обратите внимание на различие между ссылочным равенством и равенство значений.</span><span class="sxs-lookup"><span data-stu-id="090d1-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="090d1-117">**X AVOID** перегрузка операторов равенства для ссылочных типов, если реализация будет значительно медленнее, чем, равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="090d1-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="090d1-118">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="090d1-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="090d1-119">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="090d1-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="090d1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="090d1-120">See Also</span></span>  
 [<span data-ttu-id="090d1-121">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="090d1-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="090d1-122">Правила использования</span><span class="sxs-lookup"><span data-stu-id="090d1-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
