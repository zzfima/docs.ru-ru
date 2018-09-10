---
title: 'Оператор :: (Справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 077d5835b372897cbe797385271effc5d00bf6e3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43473977"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9cacc-102">Оператор :: (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9cacc-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="9cacc-103">Квалификатор псевдонима пространства имен (`::`) служит для поиска идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="9cacc-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="9cacc-104">Он всегда размещается между двумя идентификаторами, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9cacc-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  

<span data-ttu-id="9cacc-105">Оператор `::` также может использоваться с *директивой псевдонима using*:</span><span class="sxs-lookup"><span data-stu-id="9cacc-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="9cacc-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="9cacc-106">Remarks</span></span>  
 <span data-ttu-id="9cacc-107">Квалификатор псевдонима пространства имен может быть `global`.</span><span class="sxs-lookup"><span data-stu-id="9cacc-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="9cacc-108">Он вызывает поиск в глобальном пространстве имен, а не в пространстве имен с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="9cacc-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="9cacc-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="9cacc-109">For More Information</span></span>  
 <span data-ttu-id="9cacc-110">Пример использования оператора `::` см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="9cacc-110">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="9cacc-111">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="9cacc-111">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="9cacc-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9cacc-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9cacc-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9cacc-113">See Also</span></span>

- [<span data-ttu-id="9cacc-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9cacc-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="9cacc-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9cacc-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9cacc-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="9cacc-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="9cacc-117">Ключевые слова, используемые для пространств имен</span><span class="sxs-lookup"><span data-stu-id="9cacc-117">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="9cacc-118">. Оператор</span><span class="sxs-lookup"><span data-stu-id="9cacc-118">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="9cacc-119">Псевдоним extern</span><span class="sxs-lookup"><span data-stu-id="9cacc-119">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
