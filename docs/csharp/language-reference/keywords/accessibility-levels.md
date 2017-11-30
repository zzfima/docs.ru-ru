---
title: "Уровни доступности (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 77124554d7a0b38414e154e024aceddbfffcfbd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="d8197-102">Уровни доступности (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d8197-102">Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="d8197-103">Модификаторы доступа [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) или [private](../../../csharp/language-reference/keywords/private.md) используются для указания одного из следующих объявленных уровней доступности к членам.</span><span class="sxs-lookup"><span data-stu-id="d8197-103">Use the access modifiers, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md), to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="d8197-104">Объявленная доступность</span><span class="sxs-lookup"><span data-stu-id="d8197-104">Declared accessibility</span></span>|<span data-ttu-id="d8197-105">Значение</span><span class="sxs-lookup"><span data-stu-id="d8197-105">Meaning</span></span>|  
|----------------------------|-------------|  
|`public`|<span data-ttu-id="d8197-106">Неограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="d8197-106">Access is not restricted.</span></span>|  
|`protected`|<span data-ttu-id="d8197-107">Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="d8197-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|`internal`|<span data-ttu-id="d8197-108">Доступ ограничен текущей сборкой.</span><span class="sxs-lookup"><span data-stu-id="d8197-108">Access is limited to the current assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="d8197-109">Доступ ограничен текущей сборкой или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="d8197-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|`private`|<span data-ttu-id="d8197-110">Доступ ограничен содержащим типом.</span><span class="sxs-lookup"><span data-stu-id="d8197-110">Access is limited to the containing type.</span></span>|  
|`private protected`|<span data-ttu-id="d8197-111">Доступ ограничен для содержащего класса или типам, производным от содержащего класса в текущей сборке.</span><span class="sxs-lookup"><span data-stu-id="d8197-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>|  
  
 <span data-ttu-id="d8197-112">Только один модификатор доступа может для элемента или типа, за исключением того, при использовании `protected internal` или `private protected` сочетания.</span><span class="sxs-lookup"><span data-stu-id="d8197-112">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="d8197-113">Модификаторы доступа не могут быть указаны для пространств имен.</span><span class="sxs-lookup"><span data-stu-id="d8197-113">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="d8197-114">Пространства имен не имеют ограничений доступа.</span><span class="sxs-lookup"><span data-stu-id="d8197-114">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="d8197-115">В зависимости от контекста, в котором производится объявление члена, допускаются только некоторые объявленные уровни доступности.</span><span class="sxs-lookup"><span data-stu-id="d8197-115">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="d8197-116">Если модификатор доступа не указывается в объявлении члена, используется доступность по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d8197-116">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="d8197-117">Типы верхнего уровня, не вложенные в другие типы, могут иметь только уровень доступности `internal` или `public`.</span><span class="sxs-lookup"><span data-stu-id="d8197-117">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="d8197-118">Для этих типов уровнем доступности по умолчанию является `internal`.</span><span class="sxs-lookup"><span data-stu-id="d8197-118">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="d8197-119">Вложенные типы, которые являются членами других типов, могут иметь объявленные уровни доступности, как указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d8197-119">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="d8197-120">Члены типа</span><span class="sxs-lookup"><span data-stu-id="d8197-120">Members of</span></span>|<span data-ttu-id="d8197-121">Уровень доступности членов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d8197-121">Default member accessibility</span></span>|<span data-ttu-id="d8197-122">Допустимые объявленные уровни доступности члена</span><span class="sxs-lookup"><span data-stu-id="d8197-122">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="d8197-123">Нет</span><span class="sxs-lookup"><span data-stu-id="d8197-123">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="d8197-124">Нет</span><span class="sxs-lookup"><span data-stu-id="d8197-124">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="d8197-125">Доступность вложенного типа зависит от [домена доступности](../../../csharp/language-reference/keywords/accessibility-domain.md), который определяется объявленным уровнем доступности члена и доменом доступности непосредственно вмещающего его типа.</span><span class="sxs-lookup"><span data-stu-id="d8197-125">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="d8197-126">Однако домен доступности вложенного типа не может выходить за границы домена доступности содержащего его типа.</span><span class="sxs-lookup"><span data-stu-id="d8197-126">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d8197-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d8197-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8197-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d8197-128">See Also</span></span>  
 [<span data-ttu-id="d8197-129">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d8197-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d8197-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d8197-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d8197-131">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d8197-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d8197-132">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="d8197-132">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="d8197-133">Домен доступности</span><span class="sxs-lookup"><span data-stu-id="d8197-133">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [<span data-ttu-id="d8197-134">Ограничения на использование уровней доступности</span><span class="sxs-lookup"><span data-stu-id="d8197-134">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [<span data-ttu-id="d8197-135">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="d8197-135">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="d8197-136">public</span><span class="sxs-lookup"><span data-stu-id="d8197-136">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="d8197-137">private</span><span class="sxs-lookup"><span data-stu-id="d8197-137">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="d8197-138">protected</span><span class="sxs-lookup"><span data-stu-id="d8197-138">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="d8197-139">internal</span><span class="sxs-lookup"><span data-stu-id="d8197-139">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
