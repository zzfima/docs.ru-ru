---
title: "Оператор ^ (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
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
ms.openlocfilehash: f081dd2979930404639638179444adc05dd462e1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="cc0d8-102">Оператор ^ (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="cc0d8-102">^ Operator (C# Reference)</span></span>
<span data-ttu-id="cc0d8-103">Бинарные операторы `^` предварительно определены для целочисленных типов и типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="cc0d8-104">Для целочисленных типов оператор `^` выполняет побитовую операцию исключающего ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="cc0d8-105">Для операндов типа `bool` оператор `^` выполняет логическую операцию исключающего ИЛИ для всех своих операндов. Таким образом, значение `true` возвращается только тогда, когда только один из операндов имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc0d8-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc0d8-106">Remarks</span></span>  
 <span data-ttu-id="cc0d8-107">Определяемые пользователем типы могут вызвать перегрузку оператора `^` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="cc0d8-107">User-defined types can overload the `^` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="cc0d8-108">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc0d8-109">Пример</span><span class="sxs-lookup"><span data-stu-id="cc0d8-109">Example</span></span>  
 <span data-ttu-id="cc0d8-110">[!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cc0d8-110">[!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="cc0d8-111">При вычислении выражения `0xf8 ^ 0x3f` в предыдущем примере выполняется побитовая операция исключающего ИЛИ со следующими двумя двоичными значениями, которые соответствуют шестнадцатеричным значениям F8 и 3F:</span><span class="sxs-lookup"><span data-stu-id="cc0d8-111">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>  
  
 `1111 1000`  
  
 `0011 1111`  
  
 <span data-ttu-id="cc0d8-112">В результате выполнения операции исключающего ИЛИ получается значение `1100 0111` или C7 в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-112">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0d8-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cc0d8-113">See Also</span></span>  
 <span data-ttu-id="cc0d8-114">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="cc0d8-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="cc0d8-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cc0d8-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="cc0d8-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="cc0d8-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

