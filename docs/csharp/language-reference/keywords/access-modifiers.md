---
title: Модификаторы доступа (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: 9629b1727fc210025256724db8db82b13b63b7db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="ff342-102">Модификаторы доступа (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ff342-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="ff342-103">Модификаторы доступа — это ключевые слова, которые задают объявленный уровень доступности члена или типа.</span><span class="sxs-lookup"><span data-stu-id="ff342-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="ff342-104">В этом разделе описываются четыре модификатора доступа:</span><span class="sxs-lookup"><span data-stu-id="ff342-104">This section introduces the four access modifiers:</span></span>  
  
-   `public`
-   `protected`
-   `internal`
-   `private`
  
 <span data-ttu-id="ff342-105">С помощью этих модификаторов можно задать следующие шесть уровней доступа:</span><span class="sxs-lookup"><span data-stu-id="ff342-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="ff342-106">[`public`](public.md): неограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="ff342-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="ff342-107">[`protected`](protected.md): доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="ff342-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="ff342-108">[`internal`](internal.md): доступ ограничен текущей сборкой.</span><span class="sxs-lookup"><span data-stu-id="ff342-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="ff342-109">[`protected internal`](protected-internal.md): доступ ограничен текущей сборкой или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="ff342-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="ff342-110">[`private`](private.md): доступ ограничен содержащим типом.</span><span class="sxs-lookup"><span data-stu-id="ff342-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="ff342-111">[`private protected`](private-protected.md): Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса в текущей сборке.</span><span class="sxs-lookup"><span data-stu-id="ff342-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="ff342-112">В этом разделе также представлена следующая информация:</span><span class="sxs-lookup"><span data-stu-id="ff342-112">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="ff342-113">[Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md): с помощью четырех модификаторов доступа можно объявить шесть уровней доступности.</span><span class="sxs-lookup"><span data-stu-id="ff342-113">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="ff342-114">[Домен доступности](../../../csharp/language-reference/keywords/accessibility-domain.md): определяет, в каких разделах программы может присутствовать ссылка на этот член.</span><span class="sxs-lookup"><span data-stu-id="ff342-114">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="ff342-115">[Ограничения на использование уровней доступности](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): общие сведения об ограничениях на использование объявленных уровней доступности.</span><span class="sxs-lookup"><span data-stu-id="ff342-115">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff342-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ff342-116">See Also</span></span>  
 [<span data-ttu-id="ff342-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ff342-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ff342-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ff342-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ff342-119">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ff342-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ff342-120">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="ff342-120">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="ff342-121">Ключевые слова доступа</span><span class="sxs-lookup"><span data-stu-id="ff342-121">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
 [<span data-ttu-id="ff342-122">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="ff342-122">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
