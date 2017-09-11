---
title: "Уровни доступности (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 796802a407c486c1df5332d5b4920467f3a1171b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="14b7e-102">Уровни доступности (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="14b7e-102">Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="14b7e-103">Модификаторы доступа [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) или [private](../../../csharp/language-reference/keywords/private.md) используются для указания одного из следующих объявленных уровней доступности к членам.</span><span class="sxs-lookup"><span data-stu-id="14b7e-103">Use the access modifiers, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md), to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="14b7e-104">Объявленная доступность</span><span class="sxs-lookup"><span data-stu-id="14b7e-104">Declared accessibility</span></span>|<span data-ttu-id="14b7e-105">Значение</span><span class="sxs-lookup"><span data-stu-id="14b7e-105">Meaning</span></span>|  
|----------------------------|-------------|  
|`public`|<span data-ttu-id="14b7e-106">Неограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="14b7e-106">Access is not restricted.</span></span>|  
|`protected`|<span data-ttu-id="14b7e-107">Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="14b7e-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|`internal`|<span data-ttu-id="14b7e-108">Доступ ограничен текущей сборкой.</span><span class="sxs-lookup"><span data-stu-id="14b7e-108">Access is limited to the current assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="14b7e-109">Доступ ограничен текущей сборкой или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="14b7e-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|`private`|<span data-ttu-id="14b7e-110">Доступ ограничен содержащим типом.</span><span class="sxs-lookup"><span data-stu-id="14b7e-110">Access is limited to the containing type.</span></span>|  
  
 <span data-ttu-id="14b7e-111">Только один модификатор доступа может быть указан для члена или типа, за исключением случая, когда используется сочетание `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="14b7e-111">Only one access modifier is allowed for a member or type, except when you use the `protected internal` combination.</span></span>  
  
 <span data-ttu-id="14b7e-112">Модификаторы доступа не могут быть указаны для пространств имен.</span><span class="sxs-lookup"><span data-stu-id="14b7e-112">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="14b7e-113">Пространства имен не имеют ограничений доступа.</span><span class="sxs-lookup"><span data-stu-id="14b7e-113">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="14b7e-114">В зависимости от контекста, в котором производится объявление члена, допускаются только некоторые объявленные уровни доступности.</span><span class="sxs-lookup"><span data-stu-id="14b7e-114">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="14b7e-115">Если модификатор доступа не указывается в объявлении члена, используется доступность по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="14b7e-115">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="14b7e-116">Типы верхнего уровня, не вложенные в другие типы, могут иметь только уровень доступности `internal` или `public`.</span><span class="sxs-lookup"><span data-stu-id="14b7e-116">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="14b7e-117">Для этих типов уровнем доступности по умолчанию является `internal`.</span><span class="sxs-lookup"><span data-stu-id="14b7e-117">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="14b7e-118">Вложенные типы, которые являются членами других типов, могут иметь объявленные уровни доступности, как указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="14b7e-118">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="14b7e-119">Члены типа</span><span class="sxs-lookup"><span data-stu-id="14b7e-119">Members of</span></span>|<span data-ttu-id="14b7e-120">Уровень доступности членов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="14b7e-120">Default member accessibility</span></span>|<span data-ttu-id="14b7e-121">Допустимые объявленные уровни доступности члена</span><span class="sxs-lookup"><span data-stu-id="14b7e-121">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="14b7e-122">Нет</span><span class="sxs-lookup"><span data-stu-id="14b7e-122">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal`|  
|`interface`|`public`|<span data-ttu-id="14b7e-123">Нет</span><span class="sxs-lookup"><span data-stu-id="14b7e-123">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="14b7e-124">Доступность вложенного типа зависит от [домена доступности](../../../csharp/language-reference/keywords/accessibility-domain.md), который определяется объявленным уровнем доступности члена и доменом доступности непосредственно вмещающего его типа.</span><span class="sxs-lookup"><span data-stu-id="14b7e-124">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="14b7e-125">Однако домен доступности вложенного типа не может выходить за границы домена доступности содержащего его типа.</span><span class="sxs-lookup"><span data-stu-id="14b7e-125">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="14b7e-126">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="14b7e-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="14b7e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="14b7e-127">See Also</span></span>  
 <span data-ttu-id="14b7e-128">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="14b7e-128">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="14b7e-129">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="14b7e-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="14b7e-130">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="14b7e-130">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="14b7e-131">[Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="14b7e-131">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="14b7e-132">[Домен доступности](../../../csharp/language-reference/keywords/accessibility-domain.md) </span><span class="sxs-lookup"><span data-stu-id="14b7e-132">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md) </span></span>  
 <span data-ttu-id="14b7e-133">[Ограничения на использование уровней доступности](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="14b7e-133">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span></span>  
 <span data-ttu-id="14b7e-134">[Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="14b7e-134">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="14b7e-135">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="14b7e-135">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="14b7e-136">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="14b7e-136">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="14b7e-137">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="14b7e-137">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="14b7e-138">internal</span><span class="sxs-lookup"><span data-stu-id="14b7e-138">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

