---
title: Оператор != (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: e974ffb1b25944e24fca23864dc7e932ec1876d5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44192019"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="931dc-102">Оператор != (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="931dc-102">!= Operator (C# Reference)</span></span>
<span data-ttu-id="931dc-103">Оператор неравенства (`!=`) возвращает значение false, если его операнды равны. В противном случае возвращается значение true.</span><span class="sxs-lookup"><span data-stu-id="931dc-103">The inequality operator (`!=`) returns false if its operands are equal, true otherwise.</span></span> <span data-ttu-id="931dc-104">Операторы неравенства предопределены для всех типов, включая строки и объекты.</span><span class="sxs-lookup"><span data-stu-id="931dc-104">Inequality operators are predefined for all types, including string and object.</span></span> <span data-ttu-id="931dc-105">Определяемые пользователем типы могут перегружать оператор `!=`.</span><span class="sxs-lookup"><span data-stu-id="931dc-105">User-defined types can overload the `!=` operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="931dc-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="931dc-106">Remarks</span></span>  
 <span data-ttu-id="931dc-107">Для предопределенных типов значений оператор неравенства (`!=`) возвращает значение true, если значения его операндов отличаются, и false в любых остальных случаях.</span><span class="sxs-lookup"><span data-stu-id="931dc-107">For predefined value types, the inequality operator (`!=`) returns true if the values of its operands are different, false otherwise.</span></span> <span data-ttu-id="931dc-108">Для ссылочных типов (кроме `string`) оператор `!=` возвращает значение true, если два его операнда ссылаются на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="931dc-108">For reference types other than `string`, `!=` returns true if its two operands refer to different objects.</span></span> <span data-ttu-id="931dc-109">Для типа `string` оператор `!=` сравнивает значения строк.</span><span class="sxs-lookup"><span data-stu-id="931dc-109">For the `string` type, `!=` compares the values of the strings.</span></span>  
  
 <span data-ttu-id="931dc-110">Определяемые пользователем типы значений могут вызвать перегрузку оператора `!=` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="931dc-110">User-defined value types can overload the `!=` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="931dc-111">Это справедливо и для определяемых пользователем ссылочных типов, хотя оператор `!=` по умолчанию действует описанным выше способом и для предопределенных, и для определяемых пользователем ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="931dc-111">So can user-defined reference types, although by default `!=` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="931dc-112">В случае перегрузки `!=` также необходимо перегружать [==](../../../csharp/language-reference/operators/equality-comparison-operator.md).</span><span class="sxs-lookup"><span data-stu-id="931dc-112">If `!=` is overloaded, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) must also be overloaded.</span></span> <span data-ttu-id="931dc-113">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="931dc-113">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="931dc-114">Пример</span><span class="sxs-lookup"><span data-stu-id="931dc-114">Example</span></span>  
 [!code-csharp[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="931dc-115">См. также</span><span class="sxs-lookup"><span data-stu-id="931dc-115">See Also</span></span>

- [<span data-ttu-id="931dc-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="931dc-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="931dc-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="931dc-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="931dc-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="931dc-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
