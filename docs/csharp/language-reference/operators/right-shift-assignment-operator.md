---
title: Справочник по C#. Оператор =&gt;&gt;
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: aebc92ffb007db7b4950313874ebc2bf3c40615f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239450"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="37b08-102">Оператор &gt;&gt;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="37b08-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="37b08-103">Оператор присваивания сдвига вправо.</span><span class="sxs-lookup"><span data-stu-id="37b08-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37b08-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="37b08-104">Remarks</span></span>  
 <span data-ttu-id="37b08-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="37b08-105">An expression of the form</span></span>  
  
```csharp  
x >>= y  
```  
  
 <span data-ttu-id="37b08-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="37b08-106">is evaluated as</span></span>  
  
```csharp  
x = x >> y  
```  
  
 <span data-ttu-id="37b08-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="37b08-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="37b08-108">[Оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) сдвигает `x` вправо на величину, указанную в `y`.</span><span class="sxs-lookup"><span data-stu-id="37b08-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="37b08-109">Оператор >>= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="37b08-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37b08-110">Пример</span><span class="sxs-lookup"><span data-stu-id="37b08-110">Example</span></span>  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="37b08-111">См. также</span><span class="sxs-lookup"><span data-stu-id="37b08-111">See Also</span></span>

- [<span data-ttu-id="37b08-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="37b08-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="37b08-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="37b08-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="37b08-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="37b08-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
