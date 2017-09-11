---
title: "Оператор != (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
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
ms.openlocfilehash: 49c5c9668c6b1169220ee4fa0babf167292a9813
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="4eba2-102">Оператор != (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4eba2-102">!= Operator (C# Reference)</span></span>
<span data-ttu-id="4eba2-103">Оператор неравенства (`!=`) возвращает значение false, если его операнды равны. В противном случае возвращается значение true.</span><span class="sxs-lookup"><span data-stu-id="4eba2-103">The inequality operator (`!=`) returns false if its operands are equal, true otherwise.</span></span> <span data-ttu-id="4eba2-104">Операторы неравенства предопределены для всех типов, включая строки и объекты.</span><span class="sxs-lookup"><span data-stu-id="4eba2-104">Inequality operators are predefined for all types, including string and object.</span></span> <span data-ttu-id="4eba2-105">Определяемые пользователем типы могут перегружать оператор `!=`.</span><span class="sxs-lookup"><span data-stu-id="4eba2-105">User-defined types can overload the `!=` operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4eba2-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="4eba2-106">Remarks</span></span>  
 <span data-ttu-id="4eba2-107">Для предопределенных типов значений оператор неравенства (`!=`) возвращает значение true, если значения его операндов отличаются, и false в любых остальных случаях.</span><span class="sxs-lookup"><span data-stu-id="4eba2-107">For predefined value types, the inequality operator (`!=`) returns true if the values of its operands are different, false otherwise.</span></span> <span data-ttu-id="4eba2-108">Для ссылочных типов (кроме `string`) оператор `!=` возвращает значение true, если два его операнда ссылаются на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="4eba2-108">For reference types other than `string`, `!=` returns true if its two operands refer to different objects.</span></span> <span data-ttu-id="4eba2-109">Для типа `string` оператор `!=` сравнивает значения строк.</span><span class="sxs-lookup"><span data-stu-id="4eba2-109">For the `string` type, `!=` compares the values of the strings.</span></span>  
  
 <span data-ttu-id="4eba2-110">Определяемые пользователем типы значений могут вызвать перегрузку оператора `!=` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="4eba2-110">User-defined value types can overload the `!=` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="4eba2-111">Это справедливо и для определяемых пользователем ссылочных типов, хотя оператор `!=` по умолчанию действует описанным выше способом и для предопределенных, и для определяемых пользователем ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="4eba2-111">So can user-defined reference types, although by default `!=` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="4eba2-112">В случае перегрузки `!=` также необходимо перегружать [==](../../../csharp/language-reference/operators/equality-comparison-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4eba2-112">If `!=` is overloaded, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) must also be overloaded.</span></span> <span data-ttu-id="4eba2-113">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="4eba2-113">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4eba2-114">Пример</span><span class="sxs-lookup"><span data-stu-id="4eba2-114">Example</span></span>  
 <span data-ttu-id="4eba2-115">[!code-cs[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4eba2-115">[!code-cs[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eba2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4eba2-116">See Also</span></span>  
 <span data-ttu-id="4eba2-117">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4eba2-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4eba2-118">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4eba2-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="4eba2-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="4eba2-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

