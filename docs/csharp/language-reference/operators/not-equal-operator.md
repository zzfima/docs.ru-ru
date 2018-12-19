---
title: Справочник по C#. Оператор !=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: 15f1b5930117e608644a58343fb855562f36b21c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237822"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="86192-102">Оператор != (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="86192-102">!= Operator (C# Reference)</span></span>
<span data-ttu-id="86192-103">Оператор неравенства (`!=`) возвращает значение false, если его операнды равны. В противном случае возвращается значение true.</span><span class="sxs-lookup"><span data-stu-id="86192-103">The inequality operator (`!=`) returns false if its operands are equal, true otherwise.</span></span> <span data-ttu-id="86192-104">Операторы неравенства предопределены для всех типов, включая строки и объекты.</span><span class="sxs-lookup"><span data-stu-id="86192-104">Inequality operators are predefined for all types, including string and object.</span></span> <span data-ttu-id="86192-105">Определяемые пользователем типы могут перегружать оператор `!=`.</span><span class="sxs-lookup"><span data-stu-id="86192-105">User-defined types can overload the `!=` operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86192-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="86192-106">Remarks</span></span>  
 <span data-ttu-id="86192-107">Для предопределенных типов значений оператор неравенства (`!=`) возвращает значение true, если значения его операндов отличаются, и false в любых остальных случаях.</span><span class="sxs-lookup"><span data-stu-id="86192-107">For predefined value types, the inequality operator (`!=`) returns true if the values of its operands are different, false otherwise.</span></span> <span data-ttu-id="86192-108">Для ссылочных типов (кроме `string`) оператор `!=` возвращает значение true, если два его операнда ссылаются на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="86192-108">For reference types other than `string`, `!=` returns true if its two operands refer to different objects.</span></span> <span data-ttu-id="86192-109">Для типа `string` оператор `!=` сравнивает значения строк.</span><span class="sxs-lookup"><span data-stu-id="86192-109">For the `string` type, `!=` compares the values of the strings.</span></span>  
  
 <span data-ttu-id="86192-110">Определяемые пользователем типы значений могут вызвать перегрузку оператора `!=` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="86192-110">User-defined value types can overload the `!=` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="86192-111">Это справедливо и для определяемых пользователем ссылочных типов, хотя оператор `!=` по умолчанию действует описанным выше способом и для предопределенных, и для определяемых пользователем ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="86192-111">So can user-defined reference types, although by default `!=` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="86192-112">В случае перегрузки `!=` также необходимо перегружать [==](../../../csharp/language-reference/operators/equality-comparison-operator.md).</span><span class="sxs-lookup"><span data-stu-id="86192-112">If `!=` is overloaded, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) must also be overloaded.</span></span> <span data-ttu-id="86192-113">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="86192-113">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86192-114">Пример</span><span class="sxs-lookup"><span data-stu-id="86192-114">Example</span></span>  
 [!code-csharp[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="86192-115">См. также</span><span class="sxs-lookup"><span data-stu-id="86192-115">See Also</span></span>

- [<span data-ttu-id="86192-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="86192-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="86192-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="86192-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="86192-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="86192-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
