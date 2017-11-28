---
title: "Оператор ++ (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6deb2f772fefc93020e7eaaed6be35e48b11df7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1b95f-102">Оператор ++ (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1b95f-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="1b95f-103">Оператор инкремента (`++`) увеличивает операнд на 1.</span><span class="sxs-lookup"><span data-stu-id="1b95f-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="1b95f-104">Оператор инкремента может находиться перед своим операндом или после него: `++variable` и `variable++`.</span><span class="sxs-lookup"><span data-stu-id="1b95f-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b95f-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b95f-105">Remarks</span></span>  
 <span data-ttu-id="1b95f-106">Первый случай — это операция префиксного инкремента.</span><span class="sxs-lookup"><span data-stu-id="1b95f-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="1b95f-107">Результатом операции является значение операнда после его увеличения.</span><span class="sxs-lookup"><span data-stu-id="1b95f-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="1b95f-108">Второй случай — это операция постфиксного инкремента.</span><span class="sxs-lookup"><span data-stu-id="1b95f-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="1b95f-109">Результатом операции является значение операнда до его увеличения.</span><span class="sxs-lookup"><span data-stu-id="1b95f-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="1b95f-110">Числовые типы и типы перечислений имеют предварительно определенные операторы инкремента.</span><span class="sxs-lookup"><span data-stu-id="1b95f-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="1b95f-111">Определяемые пользователем типы могут перегружать оператор `++` .</span><span class="sxs-lookup"><span data-stu-id="1b95f-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="1b95f-112">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="1b95f-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b95f-113">Пример</span><span class="sxs-lookup"><span data-stu-id="1b95f-113">Example</span></span>  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="1b95f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1b95f-114">See Also</span></span>  
 [<span data-ttu-id="1b95f-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1b95f-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1b95f-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1b95f-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1b95f-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="1b95f-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
