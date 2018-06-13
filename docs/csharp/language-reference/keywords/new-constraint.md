---
title: Ограничение new (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 77c955102ba9cede831c85838a6a7e57025ad35b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269000"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="9011b-102">Ограничение new (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9011b-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="9011b-103">Ограничение `new` указывает, что аргумент любого типа в объявлении универсального класса должен иметь открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="9011b-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="9011b-104">Использовать ограничение new можно только в том случае, если тип не является абстрактным.</span><span class="sxs-lookup"><span data-stu-id="9011b-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9011b-105">Пример</span><span class="sxs-lookup"><span data-stu-id="9011b-105">Example</span></span>  
 <span data-ttu-id="9011b-106">Примените ограничение `new` к параметру типа, когда общий класс создает новые экземпляры этого типа, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9011b-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="9011b-107">Пример</span><span class="sxs-lookup"><span data-stu-id="9011b-107">Example</span></span>  
 <span data-ttu-id="9011b-108">При использовании ограничения `new()` с другими ограничениями его необходимо указывать последним:</span><span class="sxs-lookup"><span data-stu-id="9011b-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 <span data-ttu-id="9011b-109">Дополнительные сведения см. в разделе [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="9011b-109">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9011b-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9011b-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9011b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9011b-111">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="9011b-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9011b-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9011b-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9011b-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9011b-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="9011b-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="9011b-115">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="9011b-115">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="9011b-116">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="9011b-116">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
