---
title: Оператор ^= (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: d6546f23ffb6dee792339a7e3863bf58ae668d58
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857236"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ea442-102">Оператор ^= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ea442-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="ea442-103">Оператор присваивания исключающего ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="ea442-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea442-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea442-104">Remarks</span></span>  
 <span data-ttu-id="ea442-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="ea442-105">An expression of the form</span></span>  
  
```csharp  
x ^= y  
```  
  
 <span data-ttu-id="ea442-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="ea442-106">is evaluated as</span></span>  
  
```csharp  
x = x ^ y  
```  
  
 <span data-ttu-id="ea442-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="ea442-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="ea442-108">[Оператор ^](../../../csharp/language-reference/operators/xor-operator.md) выполняет побитовую операцию исключающего ИЛИ в отношении целочисленных операндов и логическую операцию исключающего ИЛИ в отношении операндов типа [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="ea442-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="ea442-109">Оператор ^= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор ^](../../../csharp/language-reference/operators/xor-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ea442-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea442-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ea442-110">Example</span></span>  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ea442-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ea442-111">See Also</span></span>

- [<span data-ttu-id="ea442-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ea442-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ea442-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ea442-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ea442-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="ea442-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
