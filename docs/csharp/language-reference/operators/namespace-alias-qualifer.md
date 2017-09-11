---
title: "Оператор :: (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ::_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
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
ms.openlocfilehash: 97b9fa706669244ac579602a107c092e8593567d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="abb14-102">Оператор :: (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="abb14-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="abb14-103">Квалификатор псевдонима пространства имен (`::`) служит для поиска идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="abb14-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="abb14-104">Он всегда размещается между двумя идентификаторами, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="abb14-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 <span data-ttu-id="abb14-105">[!code-cs[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="abb14-105">[!code-cs[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abb14-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="abb14-106">Remarks</span></span>  
 <span data-ttu-id="abb14-107">Квалификатор псевдонима пространства имен может быть `global`.</span><span class="sxs-lookup"><span data-stu-id="abb14-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="abb14-108">Он вызывает поиск в глобальном пространстве имен, а не в пространстве имен с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="abb14-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="abb14-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="abb14-109">For More Information</span></span>  
 <span data-ttu-id="abb14-110">Пример использования оператора `::` см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="abb14-110">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="abb14-111">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="abb14-111">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="abb14-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="abb14-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="abb14-113">См. также</span><span class="sxs-lookup"><span data-stu-id="abb14-113">See Also</span></span>  
 <span data-ttu-id="abb14-114">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="abb14-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="abb14-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="abb14-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="abb14-116">[Операторы в C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="abb14-116">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="abb14-117">[Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="abb14-117">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="abb14-118">[. Оператор](../../../csharp/language-reference/operators/member-access-operator.md) </span><span class="sxs-lookup"><span data-stu-id="abb14-118">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span></span>  
 [<span data-ttu-id="abb14-119">Псевдоним extern</span><span class="sxs-lookup"><span data-stu-id="abb14-119">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)

