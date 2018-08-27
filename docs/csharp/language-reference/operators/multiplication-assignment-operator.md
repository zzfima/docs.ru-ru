---
title: Оператор *= (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: e47bc5c681c94ac3fc5c345c56b3814350ffa5ec
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932354"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="eb43b-102">Оператор \*= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="eb43b-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="eb43b-103">Бинарный оператор присваивания умножения.</span><span class="sxs-lookup"><span data-stu-id="eb43b-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb43b-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="eb43b-104">Remarks</span></span>  
 <span data-ttu-id="eb43b-105">Выражение, использующее оператор присваивания `*=`, такое как</span><span class="sxs-lookup"><span data-stu-id="eb43b-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```csharp  
x *= y  
```  
  
 <span data-ttu-id="eb43b-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="eb43b-106">is equivalent to</span></span>  
  
```csharp  
x = x * y  
```  
  
 <span data-ttu-id="eb43b-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="eb43b-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="eb43b-108">Для числовых типов [оператор \*](../../../csharp/language-reference/operators/multiplication-operator.md) используется для выполнения операций умножения.</span><span class="sxs-lookup"><span data-stu-id="eb43b-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="eb43b-109">Оператор `*=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор *](../../../csharp/language-reference/operators/multiplication-operator.md) (см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="eb43b-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb43b-110">Пример</span><span class="sxs-lookup"><span data-stu-id="eb43b-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="eb43b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="eb43b-111">See Also</span></span>

- [<span data-ttu-id="eb43b-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="eb43b-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="eb43b-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="eb43b-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="eb43b-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="eb43b-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
