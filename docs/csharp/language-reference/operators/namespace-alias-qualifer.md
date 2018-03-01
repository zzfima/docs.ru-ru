---
title: "Оператор :: (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6b4f1683e1250ed745e15ced88203ca942c75ff8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="14ae3-102">Оператор :: (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="14ae3-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="14ae3-103">Квалификатор псевдонима пространства имен (`::`) служит для поиска идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="14ae3-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="14ae3-104">Он всегда размещается между двумя идентификаторами, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="14ae3-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="14ae3-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="14ae3-105">Remarks</span></span>  
 <span data-ttu-id="14ae3-106">Квалификатор псевдонима пространства имен может быть `global`.</span><span class="sxs-lookup"><span data-stu-id="14ae3-106">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="14ae3-107">Он вызывает поиск в глобальном пространстве имен, а не в пространстве имен с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="14ae3-107">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="14ae3-108">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="14ae3-108">For More Information</span></span>  
 <span data-ttu-id="14ae3-109">Пример использования оператора `::` см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="14ae3-109">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="14ae3-110">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="14ae3-110">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="14ae3-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="14ae3-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="14ae3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="14ae3-112">See Also</span></span>  
 [<span data-ttu-id="14ae3-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="14ae3-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="14ae3-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="14ae3-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="14ae3-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="14ae3-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="14ae3-116">Ключевые слова, используемые для пространств имен</span><span class="sxs-lookup"><span data-stu-id="14ae3-116">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="14ae3-117">. Оператор</span><span class="sxs-lookup"><span data-stu-id="14ae3-117">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
 [<span data-ttu-id="14ae3-118">Псевдоним extern</span><span class="sxs-lookup"><span data-stu-id="14ae3-118">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
