---
title: Оператор ++ (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: 0fe1150ca7267d02feeab33168eab7f79734c2a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="43bb0-102">Оператор ++ (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="43bb0-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="43bb0-103">Оператор инкремента (`++`) увеличивает операнд на 1.</span><span class="sxs-lookup"><span data-stu-id="43bb0-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="43bb0-104">Оператор инкремента может находиться перед своим операндом или после него: `++variable` и `variable++`.</span><span class="sxs-lookup"><span data-stu-id="43bb0-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43bb0-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="43bb0-105">Remarks</span></span>  
 <span data-ttu-id="43bb0-106">Первый случай — это операция префиксного инкремента.</span><span class="sxs-lookup"><span data-stu-id="43bb0-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="43bb0-107">Результатом операции является значение операнда после его увеличения.</span><span class="sxs-lookup"><span data-stu-id="43bb0-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="43bb0-108">Второй случай — это операция постфиксного инкремента.</span><span class="sxs-lookup"><span data-stu-id="43bb0-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="43bb0-109">Результатом операции является значение операнда до его увеличения.</span><span class="sxs-lookup"><span data-stu-id="43bb0-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="43bb0-110">Числовые типы и типы перечислений имеют предварительно определенные операторы инкремента.</span><span class="sxs-lookup"><span data-stu-id="43bb0-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="43bb0-111">Определяемые пользователем типы могут перегружать оператор `++` .</span><span class="sxs-lookup"><span data-stu-id="43bb0-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="43bb0-112">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="43bb0-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43bb0-113">Пример</span><span class="sxs-lookup"><span data-stu-id="43bb0-113">Example</span></span>  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="43bb0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="43bb0-114">See Also</span></span>  
 [<span data-ttu-id="43bb0-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="43bb0-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="43bb0-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="43bb0-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="43bb0-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="43bb0-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
