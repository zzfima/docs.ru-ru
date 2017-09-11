---
title: "+ Оператор (ссылка C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
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
ms.openlocfilehash: 5455375148f1924c7fe1cdb10e7924abb83a1565
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="c8028-102">Оператор + (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c8028-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="c8028-103">Оператор `+` может функционировать как унарный или как бинарный оператор.</span><span class="sxs-lookup"><span data-stu-id="c8028-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8028-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="c8028-104">Remarks</span></span>  
 <span data-ttu-id="c8028-105">Унарные операторы `+` предварительно определены для всех числовых типов.</span><span class="sxs-lookup"><span data-stu-id="c8028-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="c8028-106">Результатом использования унарного оператора `+` для числового типа является просто значение операнда.</span><span class="sxs-lookup"><span data-stu-id="c8028-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="c8028-107">Бинарные операторы `+` предварительно определены для числовых и строковых типов.</span><span class="sxs-lookup"><span data-stu-id="c8028-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="c8028-108">Для числовых типов оператор "+" вычисляет сумму двух его операндов.</span><span class="sxs-lookup"><span data-stu-id="c8028-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="c8028-109">Если один или оба операнда имеют строковый тип, оператор "+" сцепляет строковые представления операндов.</span><span class="sxs-lookup"><span data-stu-id="c8028-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="c8028-110">Для типов делегатов также используется бинарный оператор `+`, который выполняет сцепление делегатов.</span><span class="sxs-lookup"><span data-stu-id="c8028-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="c8028-111">Пользовательские типы могут перегружать унарный оператор `+` и бинарный оператор `+`.</span><span class="sxs-lookup"><span data-stu-id="c8028-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="c8028-112">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="c8028-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="c8028-113">Дополнительные сведения см. в разделе [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="c8028-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8028-114">Пример</span><span class="sxs-lookup"><span data-stu-id="c8028-114">Example</span></span>  
 <span data-ttu-id="c8028-115">[!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c8028-115">[!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c8028-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c8028-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c8028-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c8028-117">See Also</span></span>  
 <span data-ttu-id="c8028-118">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c8028-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c8028-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c8028-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c8028-120">[Операторы в C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="c8028-120">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="c8028-121">operator (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c8028-121">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)

