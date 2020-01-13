---
title: Справочник по C#. Уровни доступности
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 26fbc2a6d86aead537465c304146630f8bcd3ad4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713818"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="fce94-102">Уровни доступности (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="fce94-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="fce94-103">Модификаторы доступа `public`, `protected`, `internal` или `private` используются для указания одного из следующих объявленных уровней доступности к членам.</span><span class="sxs-lookup"><span data-stu-id="fce94-103">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="fce94-104">Объявленная доступность</span><span class="sxs-lookup"><span data-stu-id="fce94-104">Declared accessibility</span></span>|<span data-ttu-id="fce94-105">Значение</span><span class="sxs-lookup"><span data-stu-id="fce94-105">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="fce94-106">Неограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="fce94-106">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="fce94-107">Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="fce94-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="fce94-108">Доступ ограничен текущей сборкой.</span><span class="sxs-lookup"><span data-stu-id="fce94-108">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="fce94-109">Доступ ограничен текущей сборкой или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="fce94-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="fce94-110">Доступ ограничен содержащим типом.</span><span class="sxs-lookup"><span data-stu-id="fce94-110">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="fce94-111">Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса в текущей сборке.</span><span class="sxs-lookup"><span data-stu-id="fce94-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="fce94-112">Доступно с версии C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="fce94-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="fce94-113">Вы можете указать для члена или типа только один модификатор доступа, за исключением случаев использования сочетаний `protected internal` или `private protected`.</span><span class="sxs-lookup"><span data-stu-id="fce94-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="fce94-114">Модификаторы доступа не могут быть указаны для пространств имен.</span><span class="sxs-lookup"><span data-stu-id="fce94-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="fce94-115">Пространства имен не имеют ограничений доступа.</span><span class="sxs-lookup"><span data-stu-id="fce94-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="fce94-116">В зависимости от контекста, в котором производится объявление члена, допускаются только некоторые объявленные уровни доступности.</span><span class="sxs-lookup"><span data-stu-id="fce94-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="fce94-117">Если модификатор доступа не указывается в объявлении члена, используется доступность по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fce94-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="fce94-118">Типы верхнего уровня, не вложенные в другие типы, могут иметь только уровень доступности `internal` или `public`.</span><span class="sxs-lookup"><span data-stu-id="fce94-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="fce94-119">Для этих типов уровнем доступности по умолчанию является `internal`.</span><span class="sxs-lookup"><span data-stu-id="fce94-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="fce94-120">Вложенные типы, которые являются членами других типов, могут иметь объявленные уровни доступности, как указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="fce94-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="fce94-121">Члены типа</span><span class="sxs-lookup"><span data-stu-id="fce94-121">Members of</span></span>|<span data-ttu-id="fce94-122">Уровень доступности членов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fce94-122">Default member accessibility</span></span>|<span data-ttu-id="fce94-123">Допустимые объявленные уровни доступности члена</span><span class="sxs-lookup"><span data-stu-id="fce94-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="fce94-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="fce94-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="fce94-125">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="fce94-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="fce94-126">Доступность вложенного типа зависит от [домена доступности](./accessibility-domain.md), который определяется объявленным уровнем доступности члена и доменом доступности непосредственно вмещающего его типа.</span><span class="sxs-lookup"><span data-stu-id="fce94-126">The accessibility of a nested type depends on its [accessibility domain](./accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="fce94-127">Однако домен доступности вложенного типа не может выходить за границы домена доступности содержащего его типа.</span><span class="sxs-lookup"><span data-stu-id="fce94-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fce94-128">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="fce94-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fce94-129">См. также</span><span class="sxs-lookup"><span data-stu-id="fce94-129">See also</span></span>

- [<span data-ttu-id="fce94-130">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="fce94-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fce94-131">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fce94-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fce94-132">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="fce94-132">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="fce94-133">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="fce94-133">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="fce94-134">Домен доступности</span><span class="sxs-lookup"><span data-stu-id="fce94-134">Accessibility Domain</span></span>](./accessibility-domain.md)
- [<span data-ttu-id="fce94-135">Ограничения на использование уровней доступности</span><span class="sxs-lookup"><span data-stu-id="fce94-135">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="fce94-136">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="fce94-136">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="fce94-137">public</span><span class="sxs-lookup"><span data-stu-id="fce94-137">public</span></span>](./public.md)
- [<span data-ttu-id="fce94-138">private</span><span class="sxs-lookup"><span data-stu-id="fce94-138">private</span></span>](./private.md)
- [<span data-ttu-id="fce94-139">protected</span><span class="sxs-lookup"><span data-stu-id="fce94-139">protected</span></span>](./protected.md)
- [<span data-ttu-id="fce94-140">internal</span><span class="sxs-lookup"><span data-stu-id="fce94-140">internal</span></span>](./internal.md)
