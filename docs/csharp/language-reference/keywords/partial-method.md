---
title: "разделяемый (метод) (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- partialmethod_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
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
ms.openlocfilehash: b6f8ecca01ebf681c906b73abefc94e9e45b8700
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="partial-method-c-reference"></a><span data-ttu-id="ca768-102">разделяемый (метод) (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ca768-102">partial (Method) (C# Reference)</span></span>
<span data-ttu-id="ca768-103">Сигнатура разделяемого метода определяется в одной части разделяемого типа, а его реализация — в другой части этого типа.</span><span class="sxs-lookup"><span data-stu-id="ca768-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="ca768-104">С помощью разделяемых методов разработчики классов могут при необходимости реализовывать ловушки методов, которые схожи с обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="ca768-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="ca768-105">Если реализация не предоставлена, компилятор удаляет сигнатуру во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="ca768-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="ca768-106">В отношении разделяемых методов применяются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="ca768-106">The following conditions apply to partial methods:</span></span>  
  
-   <span data-ttu-id="ca768-107">Сигнатуры в обеих частях разделяемого типа должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="ca768-107">Signatures in both parts of the partial type must match.</span></span>  
  
-   <span data-ttu-id="ca768-108">Метод должен возвращать значение void.</span><span class="sxs-lookup"><span data-stu-id="ca768-108">The method must return void.</span></span>  
  
-   <span data-ttu-id="ca768-109">Модификаторы доступа не допускаются.</span><span class="sxs-lookup"><span data-stu-id="ca768-109">No access modifiers are allowed.</span></span> <span data-ttu-id="ca768-110">Разделяемые методы являются неявно частными.</span><span class="sxs-lookup"><span data-stu-id="ca768-110">Partial methods are implicitly private.</span></span>  
  
 <span data-ttu-id="ca768-111">В следующем примере показан разделяемый метод, определенный в двух частях разделяемого класса:</span><span class="sxs-lookup"><span data-stu-id="ca768-111">The following example shows a partial method defined in two parts of a partial class:</span></span>  
  
 <span data-ttu-id="ca768-112">[!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ca768-112">[!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]</span></span>  
  
 <span data-ttu-id="ca768-113">Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="ca768-113">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca768-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ca768-114">See Also</span></span>  
 <span data-ttu-id="ca768-115">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ca768-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="ca768-116">partial (тип)</span><span class="sxs-lookup"><span data-stu-id="ca768-116">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)

