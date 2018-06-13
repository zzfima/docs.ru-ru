---
title: Оператор -- (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 25f301bc0b2bc9bf51b0a44f26b2efabae00e452
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288805"
---
# <a name="---operator-c-reference"></a><span data-ttu-id="b35f2-102">Оператор -- (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b35f2-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="b35f2-103">Оператор декремента (`--`) уменьшает операнд на 1.</span><span class="sxs-lookup"><span data-stu-id="b35f2-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="b35f2-104">Оператор декремента может находиться перед своим операндом или после него: `--variable` и `variable--`.</span><span class="sxs-lookup"><span data-stu-id="b35f2-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="b35f2-105">Первый случай — это операция префиксного декремента.</span><span class="sxs-lookup"><span data-stu-id="b35f2-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="b35f2-106">Результатом операции является значение операнда после его уменьшения.</span><span class="sxs-lookup"><span data-stu-id="b35f2-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="b35f2-107">Второй случай — это операция постфиксного декремента.</span><span class="sxs-lookup"><span data-stu-id="b35f2-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="b35f2-108">Результатом операции является значение операнда до его уменьшения.</span><span class="sxs-lookup"><span data-stu-id="b35f2-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b35f2-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b35f2-109">Remarks</span></span>  
 <span data-ttu-id="b35f2-110">Числовые типы и типы перечислений имеют предварительно определенные операторы декремента.</span><span class="sxs-lookup"><span data-stu-id="b35f2-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="b35f2-111">Определяемые пользователем типы могут вызвать перегрузку оператора `--` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="b35f2-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="b35f2-112">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="b35f2-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b35f2-113">Пример</span><span class="sxs-lookup"><span data-stu-id="b35f2-113">Example</span></span>  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b35f2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b35f2-114">See Also</span></span>  
 [<span data-ttu-id="b35f2-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b35f2-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b35f2-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b35f2-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b35f2-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b35f2-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
