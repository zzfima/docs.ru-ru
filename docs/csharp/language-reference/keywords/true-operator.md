---
title: "Оператор true (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- true operator [C#]
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 96ab7679862959f3c99e31beac0bd5514228bd8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="true-operator-c-reference"></a><span data-ttu-id="6cbd3-102">Оператор true (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6cbd3-102">true Operator (C# Reference)</span></span>
<span data-ttu-id="6cbd3-103">Возвращает [логическое](../../../csharp/language-reference/keywords/bool.md) значение `true`, чтобы указать, что операнд имеет значение true, и возвращает значение `false` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="6cbd3-103">Returns the [bool](../../../csharp/language-reference/keywords/bool.md) value `true` to indicate that an operand is true and returns `false` otherwise.</span></span>  
  
 <span data-ttu-id="6cbd3-104">До версии C# 2.0 операторы `true` и `false` использовались для создания пользовательских типов значений, допускающих значение NULL, которые были совместимы с такими типами, как `SqlBool`.</span><span class="sxs-lookup"><span data-stu-id="6cbd3-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="6cbd3-105">Однако теперь язык предоставляет встроенную поддержку для типов, допускающих значение NULL, и по возможности следует использовать их вместо перегрузки операторов `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="6cbd3-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="6cbd3-106">Дополнительные сведения см. в разделе [Типы, допускающие значение NULL](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="6cbd3-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="6cbd3-107">С логическими значениями, допускающими значение NULL, выражение `a != b` не обязательно равно `!(a == b)`, так как одно или оба значений могут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="6cbd3-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="6cbd3-108">Необходимо перегрузить оба оператора `true` и `false` отдельно, чтобы правильно определить значения NULL в выражении.</span><span class="sxs-lookup"><span data-stu-id="6cbd3-108">You need to overload both the `true` and `false` operators separately to correctly identify the null values in the expression.</span></span> <span data-ttu-id="6cbd3-109">В следующем примере демонстрируется перегрузка и использование операторов `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="6cbd3-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/true-operator_1.cs)]  
  
 <span data-ttu-id="6cbd3-110">Тип, который перегружает операторы `true` и `false`, может использоваться для выражений управления в операторах [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) и [for](../../../csharp/language-reference/keywords/for.md) и в [условных выражениях](../../../csharp/language-reference/operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6cbd3-110">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), and [for](../../../csharp/language-reference/keywords/for.md) statements and in [conditional expressions](../../../csharp/language-reference/operators/conditional-operator.md).</span></span>  
  
 <span data-ttu-id="6cbd3-111">Если тип определяет оператор `true`, он должен также определять оператор [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="6cbd3-111">If a type defines operator `true`, it must also define operator [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
 <span data-ttu-id="6cbd3-112">Тип не может непосредственно перегрузить условные логические операторы ([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) и [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)), однако такой же результат может быть достигнут путем перегрузки обычных логических операторов и операторов `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="6cbd3-112">A type cannot directly overload the conditional logical operators ([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6cbd3-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6cbd3-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6cbd3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6cbd3-114">See Also</span></span>  
 [<span data-ttu-id="6cbd3-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6cbd3-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6cbd3-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6cbd3-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6cbd3-117">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6cbd3-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6cbd3-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="6cbd3-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="6cbd3-119">false</span><span class="sxs-lookup"><span data-stu-id="6cbd3-119">false</span></span>](../../../csharp/language-reference/keywords/false.md)
