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
ms.openlocfilehash: 25b157fafde7d2b75cd8b112848a01e9b3fb0db2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="65f05-102">Оператор ~ (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="65f05-102">~ Operator (C# Reference)</span></span>
<span data-ttu-id="65f05-103">Оператор `~` выполняет операцию поразрядного дополнения операнда, заключающуюся в инвертировании каждого бита.</span><span class="sxs-lookup"><span data-stu-id="65f05-103">The `~` operator performs a bitwise complement operation on its operand, which has the effect of reversing each bit.</span></span> <span data-ttu-id="65f05-104">Операторы поразрядного дополнения предопределены для типов [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) и [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="65f05-104">Bitwise complement operators are predefined for [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), and [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65f05-105">Символ `~` также используется для объявления методов завершения.</span><span class="sxs-lookup"><span data-stu-id="65f05-105">The `~` symbol also is used to declare finalizers.</span></span> <span data-ttu-id="65f05-106">Дополнительные сведения см. в разделе [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="65f05-106">For more information, see [Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65f05-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="65f05-107">Remarks</span></span>  
 <span data-ttu-id="65f05-108">Определяемые пользователем типы могут перегружать оператор `~`.</span><span class="sxs-lookup"><span data-stu-id="65f05-108">User-defined types can overload the `~` operator.</span></span> <span data-ttu-id="65f05-109">Дополнительные сведения см. в статье [operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="65f05-109">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="65f05-110">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="65f05-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65f05-111">Пример</span><span class="sxs-lookup"><span data-stu-id="65f05-111">Example</span></span>  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="65f05-112">См. также</span><span class="sxs-lookup"><span data-stu-id="65f05-112">See Also</span></span>  
 [<span data-ttu-id="65f05-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="65f05-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="65f05-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="65f05-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="65f05-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="65f05-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="65f05-116">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="65f05-116">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
