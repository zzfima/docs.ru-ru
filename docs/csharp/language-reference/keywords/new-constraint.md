---
title: "Ограничение new (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
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
ms.openlocfilehash: 762941794184605f90443ed8f36c88ecfa50aa84
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="f43ff-102">Ограничение new (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f43ff-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="f43ff-103">Ограничение `new` указывает, что аргумент любого типа в объявлении универсального класса должен иметь открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="f43ff-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="f43ff-104">Использовать ограничение new можно только в том случае, если тип не является абстрактным.</span><span class="sxs-lookup"><span data-stu-id="f43ff-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f43ff-105">Пример</span><span class="sxs-lookup"><span data-stu-id="f43ff-105">Example</span></span>  
 <span data-ttu-id="f43ff-106">Примените ограничение `new` к параметру типа, когда общий класс создает новые экземпляры этого типа, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f43ff-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 <span data-ttu-id="f43ff-107">[!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f43ff-107">[!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f43ff-108">Пример</span><span class="sxs-lookup"><span data-stu-id="f43ff-108">Example</span></span>  
 <span data-ttu-id="f43ff-109">При использовании ограничения `new()` с другими ограничениями его необходимо указывать последним:</span><span class="sxs-lookup"><span data-stu-id="f43ff-109">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 <span data-ttu-id="f43ff-110">[!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f43ff-110">[!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]</span></span>  
  
 <span data-ttu-id="f43ff-111">Дополнительные сведения см. в разделе [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f43ff-111">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f43ff-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f43ff-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f43ff-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f43ff-113">See Also</span></span>  
 <span data-ttu-id="f43ff-114"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="f43ff-114"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="f43ff-115">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f43ff-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f43ff-116">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f43ff-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f43ff-117">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f43ff-117">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f43ff-118">[Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="f43ff-118">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 [<span data-ttu-id="f43ff-119">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="f43ff-119">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)

