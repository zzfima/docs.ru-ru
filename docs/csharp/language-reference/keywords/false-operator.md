---
title: "Оператор false (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e12de403ca31952837913fdaaa8b221986f0e5fe
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="false-operator-c-reference"></a><span data-ttu-id="6bfad-102">Оператор false (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6bfad-102">false Operator (C# Reference)</span></span>
<span data-ttu-id="6bfad-103">Возвращает [логическое](../../../csharp/language-reference/keywords/bool.md) значение `true`, чтобы указать, что операнд является `false`, и возвращает значение `false` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="6bfad-103">Returns the [bool](../../../csharp/language-reference/keywords/bool.md) value `true` to indicate that an operand is `false` and returns `false` otherwise.</span></span>  
  
 <span data-ttu-id="6bfad-104">До версии C# 2.0 операторы `true` и `false` использовались для создания пользовательских типов значений, допускающих значение NULL, которые были совместимы с такими типами, как `SqlBool`.</span><span class="sxs-lookup"><span data-stu-id="6bfad-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="6bfad-105">Однако теперь язык предоставляет встроенную поддержку для типов, допускающих значение NULL, и по возможности следует использовать их вместо перегрузки операторов `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="6bfad-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="6bfad-106">Дополнительные сведения см. в разделе [Типы, допускающие значение NULL](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="6bfad-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="6bfad-107">С логическими значениями, допускающими значение NULL, выражение `a != b` не обязательно равно `!(a == b)`, так как одно или оба значений могут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="6bfad-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="6bfad-108">Необходимо перегрузить оба оператора `true` и `false` отдельно, чтобы правильно обработать значения NULL в выражении.</span><span class="sxs-lookup"><span data-stu-id="6bfad-108">You have to overload both the `true` and `false` operators separately to correctly handle the null values in the expression.</span></span> <span data-ttu-id="6bfad-109">В следующем примере демонстрируется перегрузка и использование операторов `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="6bfad-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>  
  
 <span data-ttu-id="6bfad-110">[!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6bfad-110">[!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="6bfad-111">Тип, который перегружает операторы `true` и `false`, может использоваться для выражений управления в операторах [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) и [for](../../../csharp/language-reference/keywords/for.md) и в [условных выражениях](../../../csharp/language-reference/operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6bfad-111">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), and [for](../../../csharp/language-reference/keywords/for.md) statements and in [conditional expressions](../../../csharp/language-reference/operators/conditional-operator.md).</span></span>  
  
 <span data-ttu-id="6bfad-112">Если тип определяет оператор `false`, он должен также определять оператор [true](../../../csharp/language-reference/keywords/true.md).</span><span class="sxs-lookup"><span data-stu-id="6bfad-112">If a type defines operator `false`, it must also define operator [true](../../../csharp/language-reference/keywords/true.md).</span></span>  
  
 <span data-ttu-id="6bfad-113">Тип не может непосредственно перегрузить условные логические операторы [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) и [||](../../../csharp/language-reference/operators/conditional-or-operator.md), однако такой же результат может быть достигнут путем перегрузки обычных логических операторов и операторов `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="6bfad-113">A type cannot directly overload the conditional logical operators [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6bfad-114">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6bfad-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6bfad-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6bfad-115">See Also</span></span>  
 <span data-ttu-id="6bfad-116">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6bfad-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6bfad-117">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6bfad-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6bfad-118">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="6bfad-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="6bfad-119">[Операторы в C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="6bfad-119">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="6bfad-120">true</span><span class="sxs-lookup"><span data-stu-id="6bfad-120">true</span></span>](../../../csharp/language-reference/keywords/true.md)

