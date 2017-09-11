---
title: "Передача параметров (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: 17
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
ms.openlocfilehash: 4b8c0c7f7b8c3820edbafbe90fb961c12da8fc84
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="c1530-102">Передача параметров (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="c1530-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="c1530-103">В C# аргументы могут передаваться параметрам либо по значению, либо по ссылке.</span><span class="sxs-lookup"><span data-stu-id="c1530-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="c1530-104">Передача по ссылке позволяет изменять и сохранять измененные значения параметров членов функций, методов, свойств, индексаторов, операторов и конструкторов в вызывающей среде.</span><span class="sxs-lookup"><span data-stu-id="c1530-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="c1530-105">Для передачи параметра по ссылке используйте ключевое слово `ref` или `out`.</span><span class="sxs-lookup"><span data-stu-id="c1530-105">To pass a parameter by reference, use the `ref` or `out` keyword.</span></span> <span data-ttu-id="c1530-106">Для простоты в этих примерах используется только ключевое слово `ref`.</span><span class="sxs-lookup"><span data-stu-id="c1530-106">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="c1530-107">Дополнительные сведения о различиях между ключевыми словами `ref` и `out` см. в разделах [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) и [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="c1530-107">For more information about the difference between `ref` and `out`, see [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md), and [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="c1530-108">В приведенном ниже примере показано различие между параметрами-значениями и ссылочными параметрами.</span><span class="sxs-lookup"><span data-stu-id="c1530-108">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 <span data-ttu-id="c1530-109">[!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c1530-109">[!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="c1530-110">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c1530-110">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="c1530-111">Передача параметров типа значения</span><span class="sxs-lookup"><span data-stu-id="c1530-111">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="c1530-112">Передача параметров ссылочного типа</span><span class="sxs-lookup"><span data-stu-id="c1530-112">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="c1530-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c1530-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c1530-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c1530-114">See Also</span></span>  
 <span data-ttu-id="c1530-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1530-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="c1530-116">Методы</span><span class="sxs-lookup"><span data-stu-id="c1530-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

