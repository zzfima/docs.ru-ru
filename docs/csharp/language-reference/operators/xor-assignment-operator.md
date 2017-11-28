---
title: "Оператор ^= (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ^=_CSharpKeyword
helpviewer_keywords: ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8d4de06dbfd269dc5e0f2cc5003e8981068220a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="81f93-102">Оператор ^= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="81f93-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="81f93-103">Оператор присваивания исключающего ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="81f93-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81f93-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="81f93-104">Remarks</span></span>  
 <span data-ttu-id="81f93-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="81f93-105">An expression of the form</span></span>  
  
```  
x ^= y  
```  
  
 <span data-ttu-id="81f93-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="81f93-106">is evaluated as</span></span>  
  
```  
x = x ^ y  
```  
  
 <span data-ttu-id="81f93-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="81f93-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="81f93-108">[Оператор ^](../../../csharp/language-reference/operators/xor-operator.md) выполняет побитовую операцию исключающего ИЛИ в отношении целочисленных операндов и логическую операцию исключающего ИЛИ в отношении операндов типа [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="81f93-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="81f93-109">Оператор ^= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор ^](../../../csharp/language-reference/operators/xor-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="81f93-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81f93-110">Пример</span><span class="sxs-lookup"><span data-stu-id="81f93-110">Example</span></span>  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="81f93-111">См. также</span><span class="sxs-lookup"><span data-stu-id="81f93-111">See Also</span></span>  
 [<span data-ttu-id="81f93-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="81f93-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="81f93-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="81f93-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="81f93-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="81f93-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
