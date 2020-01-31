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
ms.openlocfilehash: 34fc8eef5270369419b76899f0dbe1ace106caf6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741703"
---
# <a name="equality-operators"></a><span data-ttu-id="4f192-102">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="4f192-102">Equality Operators</span></span>
<span data-ttu-id="4f192-103">В этом разделе обсуждаются перегрузки операторов равенства и ссылки на `operator==` и `operator!=` в качестве операторов равенства.</span><span class="sxs-lookup"><span data-stu-id="4f192-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>

 <span data-ttu-id="4f192-104">❌ не перегружать один из операторов равенства, а не другой.</span><span class="sxs-lookup"><span data-stu-id="4f192-104">❌ DO NOT overload one of the equality operators and not the other.</span></span>

 <span data-ttu-id="4f192-105">✔️ Убедитесь, что <xref:System.Object.Equals%2A?displayProperty=nameWithType> и операторы равенства имеют точно такую же семантику и аналогичные характеристики производительности.</span><span class="sxs-lookup"><span data-stu-id="4f192-105">✔️ DO ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>

 <span data-ttu-id="4f192-106">Это часто означает, что `Object.Equals` необходимо переопределить при перегрузке операторов равенства.</span><span class="sxs-lookup"><span data-stu-id="4f192-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>

 <span data-ttu-id="4f192-107">❌ избежать возникновения исключений из операторов равенства.</span><span class="sxs-lookup"><span data-stu-id="4f192-107">❌ AVOID throwing exceptions from equality operators.</span></span>

 <span data-ttu-id="4f192-108">Например, возвращается значение false, если один из аргументов имеет значение null, а не вызывает `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="4f192-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>

## <a name="equality-operators-on-value-types"></a><span data-ttu-id="4f192-109">Операторы равенства для типов значений</span><span class="sxs-lookup"><span data-stu-id="4f192-109">Equality Operators on Value Types</span></span>
 <span data-ttu-id="4f192-110">✔️ ВЫПОЛНИТЬ перегрузку операторов равенства для типов значений, если равенство является осмысленным.</span><span class="sxs-lookup"><span data-stu-id="4f192-110">✔️ DO overload the equality operators on value types, if equality is meaningful.</span></span>

 <span data-ttu-id="4f192-111">В большинстве языков программирования отсутствует стандартная реализация `operator==` для типов значений.</span><span class="sxs-lookup"><span data-stu-id="4f192-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>

## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="4f192-112">Операторы равенства в ссылочных типах</span><span class="sxs-lookup"><span data-stu-id="4f192-112">Equality Operators on Reference Types</span></span>
 <span data-ttu-id="4f192-113">❌ избежать перегрузки операторов равенства для изменяемых ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="4f192-113">❌ AVOID overloading equality operators on mutable reference types.</span></span>

 <span data-ttu-id="4f192-114">Многие языки имеют встроенные операторы равенства для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="4f192-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="4f192-115">Встроенные операторы обычно реализуют равенство ссылок, и многие разработчики удивлены, когда поведение по умолчанию изменяется на равенство значений.</span><span class="sxs-lookup"><span data-stu-id="4f192-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>

 <span data-ttu-id="4f192-116">Эта проблема устранена для неизменяемых ссылочных типов, поскольку неизменность значительно затрудняет заметную разницу между равенством ссылок и равенством значений.</span><span class="sxs-lookup"><span data-stu-id="4f192-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>

 <span data-ttu-id="4f192-117">❌ избежать перегрузки операторов равенства в ссылочных типах, если реализация будет значительно медленнее, чем равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="4f192-117">❌ AVOID overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>

 <span data-ttu-id="4f192-118">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="4f192-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4f192-119">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4f192-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4f192-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f192-120">See also</span></span>

- [<span data-ttu-id="4f192-121">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="4f192-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="4f192-122">Правила использования</span><span class="sxs-lookup"><span data-stu-id="4f192-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
