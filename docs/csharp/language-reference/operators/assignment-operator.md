---
title: "Оператор = (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
caps.latest.revision: 14
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
ms.openlocfilehash: e40b2f221717461443a5d0247b3401eb527a7b5a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="f1322-102">Оператор = (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f1322-102">= Operator (C# Reference)</span></span>
<span data-ttu-id="f1322-103">Оператор присваивания (`=`) сохраняет значение расположенного в правой части операнда в месте хранения, свойстве или индексаторе, которые указаны в операнде слева, после чего возвращает значение в виде результата.</span><span class="sxs-lookup"><span data-stu-id="f1322-103">The assignment operator (`=`) stores the value of its right-hand operand in the storage location, property, or indexer denoted by its left-hand operand and returns the value as its result.</span></span> <span data-ttu-id="f1322-104">Операнды должны иметь один тип (либо операнд справа должен допускать неявное преобразование в тип операнда в левой части).</span><span class="sxs-lookup"><span data-stu-id="f1322-104">The operands must be of the same type (or the right-hand operand must be implicitly convertible to the type of the left-hand operand).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1322-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="f1322-105">Remarks</span></span>  
 <span data-ttu-id="f1322-106">Оператор присваивания нельзя перегружать.</span><span class="sxs-lookup"><span data-stu-id="f1322-106">The assignment operator cannot be overloaded.</span></span> <span data-ttu-id="f1322-107">Тем не менее можно определить операторы неявного преобразования типа, которые позволяют использовать оператор присваивания с этими типами.</span><span class="sxs-lookup"><span data-stu-id="f1322-107">However, you can define implicit conversion operators for a type, which enable you to use the assignment operator with those types.</span></span> <span data-ttu-id="f1322-108">Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="f1322-108">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1322-109">Пример</span><span class="sxs-lookup"><span data-stu-id="f1322-109">Example</span></span>  
 <span data-ttu-id="f1322-110">[!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f1322-110">[!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1322-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f1322-111">See Also</span></span>  
 <span data-ttu-id="f1322-112">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f1322-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f1322-113">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f1322-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f1322-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="f1322-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

