---
title: разделяемый (метод) (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 69e16dd8b0fe0055124aca90fea65a36d9e413f3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933689"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="7c6ab-102">разделяемый (метод) (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7c6ab-102">partial (Method) (C# Reference)</span></span>
<span data-ttu-id="7c6ab-103">Сигнатура разделяемого метода определяется в одной части разделяемого типа, а его реализация — в другой части этого типа.</span><span class="sxs-lookup"><span data-stu-id="7c6ab-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="7c6ab-104">С помощью разделяемых методов разработчики классов могут при необходимости реализовывать ловушки методов, которые схожи с обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="7c6ab-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="7c6ab-105">Если реализация не предоставлена, компилятор удаляет сигнатуру во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="7c6ab-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="7c6ab-106">В отношении разделяемых методов применяются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="7c6ab-106">The following conditions apply to partial methods:</span></span>  
  
-   <span data-ttu-id="7c6ab-107">Сигнатуры в обеих частях разделяемого типа должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="7c6ab-107">Signatures in both parts of the partial type must match.</span></span>  
  
-   <span data-ttu-id="7c6ab-108">Метод должен возвращать значение void.</span><span class="sxs-lookup"><span data-stu-id="7c6ab-108">The method must return void.</span></span>  
  
-   <span data-ttu-id="7c6ab-109">Модификаторы доступа не допускаются.</span><span class="sxs-lookup"><span data-stu-id="7c6ab-109">No access modifiers are allowed.</span></span> <span data-ttu-id="7c6ab-110">Разделяемые методы являются неявно частными.</span><span class="sxs-lookup"><span data-stu-id="7c6ab-110">Partial methods are implicitly private.</span></span>  
  
 <span data-ttu-id="7c6ab-111">В следующем примере показан разделяемый метод, определенный в двух частях разделяемого класса:</span><span class="sxs-lookup"><span data-stu-id="7c6ab-111">The following example shows a partial method defined in two parts of a partial class:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 <span data-ttu-id="7c6ab-112">Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="7c6ab-112">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c6ab-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7c6ab-113">See Also</span></span>

- [<span data-ttu-id="7c6ab-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7c6ab-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7c6ab-115">partial (тип)</span><span class="sxs-lookup"><span data-stu-id="7c6ab-115">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)
