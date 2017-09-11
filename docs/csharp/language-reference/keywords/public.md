---
title: "public (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- public
- public_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
caps.latest.revision: 21
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
ms.openlocfilehash: ae19bf9a33a9860a8960cde5dd4402e10418a094
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="public-c-reference"></a><span data-ttu-id="1aa2a-102">public (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1aa2a-102">public (C# Reference)</span></span>
<span data-ttu-id="1aa2a-103">Ключевое слово `public` является модификатором доступа для типов и членов типов.</span><span class="sxs-lookup"><span data-stu-id="1aa2a-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="1aa2a-104">Общий доступ является уровнем доступа с максимальными правами.</span><span class="sxs-lookup"><span data-stu-id="1aa2a-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="1aa2a-105">Ограничений доступа к общим членам не существует, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1aa2a-105">There are no restrictions on accessing public members, as in this example:</span></span>  
  
```  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 <span data-ttu-id="1aa2a-106">Дополнительные сведения см. в разделах [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) и [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1aa2a-106">See [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1aa2a-107">Пример</span><span class="sxs-lookup"><span data-stu-id="1aa2a-107">Example</span></span>  
 <span data-ttu-id="1aa2a-108">В следующем примере объявляются два класса: `PointTest` и `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="1aa2a-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="1aa2a-109">Доступ к открытым членам `x` и `y` класса `PointTest` осуществляется непосредственно из класса `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="1aa2a-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>  
  
 <span data-ttu-id="1aa2a-110">[!code-cs[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1aa2a-110">[!code-cs[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]</span></span>  
  
 <span data-ttu-id="1aa2a-111">Если уровень доступа `public` изменить на [private](../../../csharp/language-reference/keywords/private.md) или [protected](../../../csharp/language-reference/keywords/protected.md), будет выводится следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="1aa2a-111">If you change the `public` access level to [private](../../../csharp/language-reference/keywords/private.md) or [protected](../../../csharp/language-reference/keywords/protected.md), you will get the error message:</span></span>  
  
 <span data-ttu-id="1aa2a-112">"PointTest.y" недоступен из-за его уровня защиты.</span><span class="sxs-lookup"><span data-stu-id="1aa2a-112">'PointTest.y' is inaccessible due to its protection level.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1aa2a-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="1aa2a-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1aa2a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1aa2a-114">See Also</span></span>  
 <span data-ttu-id="1aa2a-115">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1aa2a-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1aa2a-116">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1aa2a-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1aa2a-117">[Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="1aa2a-117">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="1aa2a-118">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="1aa2a-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="1aa2a-119">[Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="1aa2a-119">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="1aa2a-120">[Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="1aa2a-120">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="1aa2a-121">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="1aa2a-121">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="1aa2a-122">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="1aa2a-122">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="1aa2a-123">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="1aa2a-123">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="1aa2a-124">internal</span><span class="sxs-lookup"><span data-stu-id="1aa2a-124">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

