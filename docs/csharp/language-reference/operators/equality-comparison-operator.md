---
title: "Оператор == (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
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
ms.openlocfilehash: 0e3ba284bc700e943b108adfec89d14aba41851a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="617e5-102">Оператор == (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="617e5-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="617e5-103">Для предопределенных типов значений оператор равенства (`==`) возвращает значение true, если значения его операндов равны, и `false` в любых остальных случаях.</span><span class="sxs-lookup"><span data-stu-id="617e5-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="617e5-104">Для ссылочных типов (кроме [string](../../../csharp/language-reference/keywords/string.md)) оператор `==` возвращает `true`, если оба его операнда ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="617e5-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="617e5-105">Для типа `string` оператор `==` сравнивает значения строк.</span><span class="sxs-lookup"><span data-stu-id="617e5-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="617e5-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="617e5-106">Remarks</span></span>  
 <span data-ttu-id="617e5-107">Определяемые пользователем типы значений могут вызвать перегрузку оператора `==` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="617e5-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="617e5-108">Это справедливо и для определяемых пользователем ссылочных типов, хотя оператор `==` по умолчанию действует описанным выше способом и для предопределенных, и для определяемых пользователем ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="617e5-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="617e5-109">В случае перегрузки `==` также необходимо перегружать [!=](../../../csharp/language-reference/operators/not-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="617e5-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="617e5-110">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="617e5-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="617e5-111">Пример</span><span class="sxs-lookup"><span data-stu-id="617e5-111">Example</span></span>  
 <span data-ttu-id="617e5-112">[!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="617e5-112">[!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="617e5-113">См. также</span><span class="sxs-lookup"><span data-stu-id="617e5-113">See Also</span></span>  
 <span data-ttu-id="617e5-114">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="617e5-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="617e5-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="617e5-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="617e5-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="617e5-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

