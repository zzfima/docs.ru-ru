---
title: Оператор ~ (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 8af25217f9e7e66796192783a0b8e3415604dc90
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510115"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ea57a-102">Оператор ~ (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ea57a-102">~ Operator (C# Reference)</span></span>
<span data-ttu-id="ea57a-103">Оператор `~` выполняет операцию поразрядного дополнения операнда, заключающуюся в инвертировании каждого бита.</span><span class="sxs-lookup"><span data-stu-id="ea57a-103">The `~` operator performs a bitwise complement operation on its operand, which has the effect of reversing each bit.</span></span> <span data-ttu-id="ea57a-104">Операторы поразрядного дополнения предопределены для типов [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) и [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="ea57a-104">Bitwise complement operators are predefined for [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), and [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea57a-105">Символ `~` также используется для объявления методов завершения.</span><span class="sxs-lookup"><span data-stu-id="ea57a-105">The `~` symbol also is used to declare finalizers.</span></span> <span data-ttu-id="ea57a-106">Дополнительные сведения см. в разделе [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="ea57a-106">For more information, see [Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea57a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea57a-107">Remarks</span></span>  
 <span data-ttu-id="ea57a-108">Определяемые пользователем типы могут перегружать оператор `~`.</span><span class="sxs-lookup"><span data-stu-id="ea57a-108">User-defined types can overload the `~` operator.</span></span> <span data-ttu-id="ea57a-109">Дополнительные сведения см. в статье [operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="ea57a-109">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="ea57a-110">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="ea57a-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea57a-111">Пример</span><span class="sxs-lookup"><span data-stu-id="ea57a-111">Example</span></span>  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ea57a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ea57a-112">See Also</span></span>

- [<span data-ttu-id="ea57a-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ea57a-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ea57a-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ea57a-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ea57a-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="ea57a-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="ea57a-116">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="ea57a-116">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
