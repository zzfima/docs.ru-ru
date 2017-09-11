---
title: "Модификаторы доступа (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: 15
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
ms.openlocfilehash: a3ad46580561500d9f011da4997007023a3bc844
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="4c063-102">Модификаторы доступа (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4c063-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="4c063-103">Модификаторы доступа — это ключевые слова, которые задают объявленный уровень доступности члена или типа.</span><span class="sxs-lookup"><span data-stu-id="4c063-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="4c063-104">В этом разделе описываются четыре модификатора доступа:</span><span class="sxs-lookup"><span data-stu-id="4c063-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="4c063-105">public</span><span class="sxs-lookup"><span data-stu-id="4c063-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="4c063-106">protected</span><span class="sxs-lookup"><span data-stu-id="4c063-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="4c063-107">internal</span><span class="sxs-lookup"><span data-stu-id="4c063-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="4c063-108">private</span><span class="sxs-lookup"><span data-stu-id="4c063-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="4c063-109">С помощью этих модификаторов можно задать следующие пять уровней доступа:</span><span class="sxs-lookup"><span data-stu-id="4c063-109">The following five accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="4c063-110">`public`: неограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="4c063-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="4c063-111">`protected`: доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="4c063-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="4c063-112">`Internal`: доступ ограничен текущей сборкой.</span><span class="sxs-lookup"><span data-stu-id="4c063-112">`Internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="4c063-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md): доступ ограничен текущей сборкой или типами, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="4c063-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="4c063-114">`private`: доступ ограничен содержащим типом.</span><span class="sxs-lookup"><span data-stu-id="4c063-114">`private`: Access is limited to the containing type.</span></span>  
  
 <span data-ttu-id="4c063-115">В этом разделе также представлена следующая информация:</span><span class="sxs-lookup"><span data-stu-id="4c063-115">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="4c063-116">[Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md): с помощью четырех модификаторов доступа можно объявить пять уровней доступности.</span><span class="sxs-lookup"><span data-stu-id="4c063-116">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare five levels of accessibility.</span></span>  
  
-   <span data-ttu-id="4c063-117">[Домен доступности](../../../csharp/language-reference/keywords/accessibility-domain.md): определяет, в каких разделах программы может присутствовать ссылка на этот член.</span><span class="sxs-lookup"><span data-stu-id="4c063-117">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="4c063-118">[Ограничения на использование уровней доступности](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): общие сведения об ограничениях на использование объявленных уровней доступности.</span><span class="sxs-lookup"><span data-stu-id="4c063-118">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c063-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4c063-119">See Also</span></span>  
 <span data-ttu-id="4c063-120">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c063-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4c063-121">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c063-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4c063-122">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c063-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4c063-123">[Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="4c063-123">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="4c063-124">[Ключевые слова доступа](../../../csharp/language-reference/keywords/access-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="4c063-124">[Access Keywords](../../../csharp/language-reference/keywords/access-keywords.md) </span></span>  
 [<span data-ttu-id="4c063-125">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="4c063-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

