---
title: Оператор ++ (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: a52f614ce1bbfb8e9d9be686b277c1e69f6f9d35
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "47202255"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="3c829-102">Оператор ++ (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3c829-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="3c829-103">Оператор инкремента (`++`) увеличивает операнд на 1.</span><span class="sxs-lookup"><span data-stu-id="3c829-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="3c829-104">Оператор инкремента может находиться перед своим операндом или после него: `++variable` и `variable++`.</span><span class="sxs-lookup"><span data-stu-id="3c829-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c829-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c829-105">Remarks</span></span>  
 <span data-ttu-id="3c829-106">Первый случай — это операция префиксного инкремента.</span><span class="sxs-lookup"><span data-stu-id="3c829-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="3c829-107">Результатом операции является значение операнда после его увеличения.</span><span class="sxs-lookup"><span data-stu-id="3c829-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="3c829-108">Второй случай — это операция постфиксного инкремента.</span><span class="sxs-lookup"><span data-stu-id="3c829-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="3c829-109">Результатом операции является значение операнда до его увеличения.</span><span class="sxs-lookup"><span data-stu-id="3c829-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="3c829-110">Числовые типы и типы перечислений имеют предварительно определенные операторы инкремента.</span><span class="sxs-lookup"><span data-stu-id="3c829-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="3c829-111">Определяемые пользователем типы могут перегружать оператор `++` .</span><span class="sxs-lookup"><span data-stu-id="3c829-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="3c829-112">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="3c829-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c829-113">Пример</span><span class="sxs-lookup"><span data-stu-id="3c829-113">Example</span></span>  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3c829-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3c829-114">See Also</span></span>

- [<span data-ttu-id="3c829-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3c829-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3c829-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3c829-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3c829-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="3c829-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
