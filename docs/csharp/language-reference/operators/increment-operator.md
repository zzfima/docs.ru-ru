---
title: "Оператор ++ (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ++_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f481dbe2437495b109d6d41cd24c8b4bb5b6a5b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="beb7d-102">Оператор ++ (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="beb7d-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="beb7d-103">Оператор инкремента (`++`) увеличивает операнд на 1.</span><span class="sxs-lookup"><span data-stu-id="beb7d-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="beb7d-104">Оператор инкремента может находиться перед своим операндом или после него: `++variable` и `variable++`.</span><span class="sxs-lookup"><span data-stu-id="beb7d-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beb7d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="beb7d-105">Remarks</span></span>  
 <span data-ttu-id="beb7d-106">Первый случай — это операция префиксного инкремента.</span><span class="sxs-lookup"><span data-stu-id="beb7d-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="beb7d-107">Результатом операции является значение операнда после его увеличения.</span><span class="sxs-lookup"><span data-stu-id="beb7d-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="beb7d-108">Второй случай — это операция постфиксного инкремента.</span><span class="sxs-lookup"><span data-stu-id="beb7d-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="beb7d-109">Результатом операции является значение операнда до его увеличения.</span><span class="sxs-lookup"><span data-stu-id="beb7d-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="beb7d-110">Числовые типы и типы перечислений имеют предварительно определенные операторы инкремента.</span><span class="sxs-lookup"><span data-stu-id="beb7d-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="beb7d-111">Определяемые пользователем типы могут перегружать оператор `++` .</span><span class="sxs-lookup"><span data-stu-id="beb7d-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="beb7d-112">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="beb7d-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="beb7d-113">Пример</span><span class="sxs-lookup"><span data-stu-id="beb7d-113">Example</span></span>  
 <span data-ttu-id="beb7d-114">[!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="beb7d-114">[!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb7d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="beb7d-115">See Also</span></span>  
 <span data-ttu-id="beb7d-116">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="beb7d-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="beb7d-117">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="beb7d-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="beb7d-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="beb7d-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

