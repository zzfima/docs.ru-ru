---
title: + Оператор (ссылка C#)
ms.date: 07/20/2015
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: d4a269c07e0d6dc2ac6a6a101f200653c6ea7a29
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244875"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a2ba0-102">Оператор + (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a2ba0-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="a2ba0-103">Оператор `+` может функционировать как унарный или как бинарный оператор.</span><span class="sxs-lookup"><span data-stu-id="a2ba0-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2ba0-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2ba0-104">Remarks</span></span>  
 <span data-ttu-id="a2ba0-105">Унарные операторы `+` предварительно определены для всех числовых типов.</span><span class="sxs-lookup"><span data-stu-id="a2ba0-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="a2ba0-106">Результатом использования унарного оператора `+` для числового типа является просто значение операнда.</span><span class="sxs-lookup"><span data-stu-id="a2ba0-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="a2ba0-107">Бинарные операторы `+` предварительно определены для числовых и строковых типов.</span><span class="sxs-lookup"><span data-stu-id="a2ba0-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="a2ba0-108">Для числовых типов оператор "+" вычисляет сумму двух его операндов.</span><span class="sxs-lookup"><span data-stu-id="a2ba0-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="a2ba0-109">Если один или оба операнда имеют строковый тип, оператор "+" сцепляет строковые представления операндов.</span><span class="sxs-lookup"><span data-stu-id="a2ba0-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="a2ba0-110">Для типов делегатов также используется бинарный оператор `+`, который выполняет сцепление делегатов.</span><span class="sxs-lookup"><span data-stu-id="a2ba0-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="a2ba0-111">Пользовательские типы могут перегружать унарный оператор `+` и бинарный оператор `+`.</span><span class="sxs-lookup"><span data-stu-id="a2ba0-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="a2ba0-112">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="a2ba0-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="a2ba0-113">Дополнительные сведения см. в разделе [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="a2ba0-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2ba0-114">Пример</span><span class="sxs-lookup"><span data-stu-id="a2ba0-114">Example</span></span>  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="a2ba0-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a2ba0-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a2ba0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a2ba0-116">See Also</span></span>  
 [<span data-ttu-id="a2ba0-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a2ba0-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a2ba0-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a2ba0-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a2ba0-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="a2ba0-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="a2ba0-120">operator (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a2ba0-120">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)
