---
title: "Модификаторы доступа (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23f99d0925aefde7ef43888d16e888a0943dfc21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="9861b-102">Модификаторы доступа (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9861b-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="9861b-103">Модификаторы доступа — это ключевые слова, которые задают объявленный уровень доступности члена или типа.</span><span class="sxs-lookup"><span data-stu-id="9861b-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="9861b-104">В этом разделе описываются четыре модификатора доступа:</span><span class="sxs-lookup"><span data-stu-id="9861b-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="9861b-105">public</span><span class="sxs-lookup"><span data-stu-id="9861b-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="9861b-106">protected</span><span class="sxs-lookup"><span data-stu-id="9861b-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="9861b-107">internal</span><span class="sxs-lookup"><span data-stu-id="9861b-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="9861b-108">private</span><span class="sxs-lookup"><span data-stu-id="9861b-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="9861b-109">Можно указать следующие шесть уровней доступности при помощи модификаторов доступа:</span><span class="sxs-lookup"><span data-stu-id="9861b-109">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="9861b-110">`public`: неограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="9861b-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="9861b-111">`protected`: доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="9861b-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="9861b-112">`internal`: доступ ограничен текущей сборкой.</span><span class="sxs-lookup"><span data-stu-id="9861b-112">`internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="9861b-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): Доступ ограничен текущей сборке или типам, производным от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="9861b-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="9861b-114">`private`: доступ ограничен содержащим типом.</span><span class="sxs-lookup"><span data-stu-id="9861b-114">`private`: Access is limited to the containing type.</span></span>  

 <span data-ttu-id="9861b-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md): Доступ ограничен для содержащего класса или типам, производным от содержащего класса в текущей сборке.</span><span class="sxs-lookup"><span data-stu-id="9861b-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="9861b-116">В этом разделе также представлена следующая информация:</span><span class="sxs-lookup"><span data-stu-id="9861b-116">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="9861b-117">[Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md): с помощью четырех модификаторов доступа для объявления шесть уровней доступности.</span><span class="sxs-lookup"><span data-stu-id="9861b-117">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="9861b-118">[Домен доступности](../../../csharp/language-reference/keywords/accessibility-domain.md): определяет, в каких разделах программы может присутствовать ссылка на этот член.</span><span class="sxs-lookup"><span data-stu-id="9861b-118">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="9861b-119">[Ограничения на использование уровней доступности](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): общие сведения об ограничениях на использование объявленных уровней доступности.</span><span class="sxs-lookup"><span data-stu-id="9861b-119">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9861b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9861b-120">See Also</span></span>  
 [<span data-ttu-id="9861b-121">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9861b-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9861b-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9861b-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9861b-123">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="9861b-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="9861b-124">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="9861b-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="9861b-125">Ключевые слова доступа</span><span class="sxs-lookup"><span data-stu-id="9861b-125">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
 [<span data-ttu-id="9861b-126">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="9861b-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
