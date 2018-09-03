---
title: Оператор &gt;&gt;= (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: f2bac6a4320980d80a9b6c2597dcf8dc6f08ac70
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43423475"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="09620-102">Оператор &gt;&gt;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="09620-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="09620-103">Оператор присваивания сдвига вправо.</span><span class="sxs-lookup"><span data-stu-id="09620-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09620-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="09620-104">Remarks</span></span>  
 <span data-ttu-id="09620-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="09620-105">An expression of the form</span></span>  
  
```csharp  
x >>= y  
```  
  
 <span data-ttu-id="09620-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="09620-106">is evaluated as</span></span>  
  
```csharp  
x = x >> y  
```  
  
 <span data-ttu-id="09620-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="09620-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="09620-108">[Оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) сдвигает `x` вправо на величину, указанную в `y`.</span><span class="sxs-lookup"><span data-stu-id="09620-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="09620-109">Оператор >>= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="09620-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="09620-110">Пример</span><span class="sxs-lookup"><span data-stu-id="09620-110">Example</span></span>  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="09620-111">См. также</span><span class="sxs-lookup"><span data-stu-id="09620-111">See Also</span></span>

- [<span data-ttu-id="09620-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="09620-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="09620-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="09620-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="09620-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="09620-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
