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
ms.openlocfilehash: 480ed224d1994dac926dfc78d59e227c8d1e8f36
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934999"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ca867-102">Оператор :: (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ca867-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="ca867-103">Квалификатор псевдонима пространства имен (`::`) служит для поиска идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="ca867-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="ca867-104">Он всегда размещается между двумя идентификаторами, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ca867-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="ca867-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="ca867-105">Remarks</span></span>  
 <span data-ttu-id="ca867-106">Квалификатор псевдонима пространства имен может быть `global`.</span><span class="sxs-lookup"><span data-stu-id="ca867-106">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="ca867-107">Он вызывает поиск в глобальном пространстве имен, а не в пространстве имен с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="ca867-107">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="ca867-108">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ca867-108">For More Information</span></span>  
 <span data-ttu-id="ca867-109">Пример использования оператора `::` см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="ca867-109">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="ca867-110">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="ca867-110">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="ca867-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ca867-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ca867-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ca867-112">See Also</span></span>

- [<span data-ttu-id="ca867-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ca867-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ca867-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ca867-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ca867-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="ca867-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="ca867-116">Ключевые слова, используемые для пространств имен</span><span class="sxs-lookup"><span data-stu-id="ca867-116">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="ca867-117">. Оператор</span><span class="sxs-lookup"><span data-stu-id="ca867-117">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="ca867-118">Псевдоним extern</span><span class="sxs-lookup"><span data-stu-id="ca867-118">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
