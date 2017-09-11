---
title: "Оператор -- (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- --_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
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
ms.openlocfilehash: 100e68f3b07164b0cfb398a32f47137f2726943f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="---operator-c-reference"></a><span data-ttu-id="af02a-102">Оператор -- (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="af02a-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="af02a-103">Оператор декремента (`--`) уменьшает операнд на 1.</span><span class="sxs-lookup"><span data-stu-id="af02a-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="af02a-104">Оператор декремента может находиться перед своим операндом или после него: `--variable` и `variable--`.</span><span class="sxs-lookup"><span data-stu-id="af02a-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="af02a-105">Первый случай — это операция префиксного декремента.</span><span class="sxs-lookup"><span data-stu-id="af02a-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="af02a-106">Результатом операции является значение операнда после его уменьшения.</span><span class="sxs-lookup"><span data-stu-id="af02a-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="af02a-107">Второй случай — это операция постфиксного декремента.</span><span class="sxs-lookup"><span data-stu-id="af02a-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="af02a-108">Результатом операции является значение операнда до его уменьшения.</span><span class="sxs-lookup"><span data-stu-id="af02a-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af02a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="af02a-109">Remarks</span></span>  
 <span data-ttu-id="af02a-110">Числовые типы и типы перечислений имеют предварительно определенные операторы декремента.</span><span class="sxs-lookup"><span data-stu-id="af02a-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="af02a-111">Определяемые пользователем типы могут вызвать перегрузку оператора `--` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="af02a-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="af02a-112">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="af02a-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af02a-113">Пример</span><span class="sxs-lookup"><span data-stu-id="af02a-113">Example</span></span>  
 <span data-ttu-id="af02a-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="af02a-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af02a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="af02a-115">See Also</span></span>  
 <span data-ttu-id="af02a-116">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="af02a-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="af02a-117">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="af02a-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="af02a-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="af02a-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

