---
title: Оператор *= (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 6bbf2142ca7e9e05010a29920da52e1439f6e882
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8b9c0-102">Оператор \*= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8b9c0-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="8b9c0-103">Бинарный оператор присваивания умножения.</span><span class="sxs-lookup"><span data-stu-id="8b9c0-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b9c0-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b9c0-104">Remarks</span></span>  
 <span data-ttu-id="8b9c0-105">Выражение, использующее оператор присваивания `*=`, такое как</span><span class="sxs-lookup"><span data-stu-id="8b9c0-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```csharp  
x *= y  
```  
  
 <span data-ttu-id="8b9c0-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="8b9c0-106">is equivalent to</span></span>  
  
```csharp  
x = x * y  
```  
  
 <span data-ttu-id="8b9c0-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="8b9c0-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="8b9c0-108">Для числовых типов [оператор \*](../../../csharp/language-reference/operators/multiplication-operator.md) используется для выполнения операций умножения.</span><span class="sxs-lookup"><span data-stu-id="8b9c0-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="8b9c0-109">Оператор `*=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор *](../../../csharp/language-reference/operators/multiplication-operator.md) (см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="8b9c0-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b9c0-110">Пример</span><span class="sxs-lookup"><span data-stu-id="8b9c0-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8b9c0-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8b9c0-111">See Also</span></span>  
 [<span data-ttu-id="8b9c0-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8b9c0-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8b9c0-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8b9c0-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8b9c0-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="8b9c0-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
