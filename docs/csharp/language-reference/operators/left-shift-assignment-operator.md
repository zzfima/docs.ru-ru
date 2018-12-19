---
title: Оператор &lt;&lt;=. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: f49c6360d6fee3f6d612aee51446545f25cd7d18
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239177"
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="b82eb-102">Оператор &lt;&lt;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b82eb-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="b82eb-103">Оператор присваивания сдвига влево.</span><span class="sxs-lookup"><span data-stu-id="b82eb-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b82eb-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="b82eb-104">Remarks</span></span>  
 <span data-ttu-id="b82eb-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="b82eb-105">An expression of the form</span></span>  
  
```csharp  
x <<= y  
```  
  
 <span data-ttu-id="b82eb-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="b82eb-106">is evaluated as</span></span>  
  
```csharp  
x = x << y  
```  
  
 <span data-ttu-id="b82eb-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="b82eb-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="b82eb-108">[Оператор <<](../../../csharp/language-reference/operators/left-shift-operator.md) сдвигает `x` влево на число битов, заданное в `y`.</span><span class="sxs-lookup"><span data-stu-id="b82eb-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="b82eb-109">Оператор `<<=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор <<](../../../csharp/language-reference/operators/left-shift-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="b82eb-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b82eb-110">Пример</span><span class="sxs-lookup"><span data-stu-id="b82eb-110">Example</span></span>  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b82eb-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b82eb-111">See Also</span></span>

- [<span data-ttu-id="b82eb-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b82eb-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b82eb-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b82eb-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b82eb-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b82eb-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
