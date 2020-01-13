---
title: Практическое руководство. Использование определенных исключений в блоке catch
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try/catch blocks
- catch blocks
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
ms.openlocfilehash: 6f0956c6418d894a5768463861151f86a1948850
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708585"
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a><span data-ttu-id="6138b-102">Практическое руководство. Использование определенных исключений в блоке catch</span><span class="sxs-lookup"><span data-stu-id="6138b-102">How to use specific exceptions in a catch block</span></span>

<span data-ttu-id="6138b-103">В общем случае вместо использования базового оператора `catch` рекомендуется перехватывать исключения определенного типа.</span><span class="sxs-lookup"><span data-stu-id="6138b-103">In general, it's good programming practice to catch a specific type of exception rather than use a basic `catch` statement.</span></span>

<span data-ttu-id="6138b-104">При возникновении исключения оно передается вверх по стеку, и каждый блок catch получает возможность обработать его.</span><span class="sxs-lookup"><span data-stu-id="6138b-104">When an exception occurs, it is passed up the stack and each catch block is given the opportunity to handle it.</span></span> <span data-ttu-id="6138b-105">Важен порядок операторов catch.</span><span class="sxs-lookup"><span data-stu-id="6138b-105">The order of catch statements is important.</span></span> <span data-ttu-id="6138b-106">Размещайте блоки catch, предназначенные для определенных исключений, до общего блока перехвата исключений. В противном случае компилятор может выдать ошибку.</span><span class="sxs-lookup"><span data-stu-id="6138b-106">Put catch blocks targeted to specific exceptions before a general exception catch block or the compiler might issue an error.</span></span> <span data-ttu-id="6138b-107">Соответствующий блок catch определяется путем соотнесения типа исключения с именем исключения, указанным в блоке catch.</span><span class="sxs-lookup"><span data-stu-id="6138b-107">The proper catch block is determined by matching the type of the exception to the name of the exception specified in the catch block.</span></span> <span data-ttu-id="6138b-108">Когда специальный блок catch отсутствует, исключение перехватывается общим блоком catch, если он существует.</span><span class="sxs-lookup"><span data-stu-id="6138b-108">If there is no specific catch block, the exception is caught by a general catch block, if one exists.</span></span>

<span data-ttu-id="6138b-109">В следующем примере кода блок `try`/`catch` используется, чтобы перехватить <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="6138b-109">The following code example uses a `try`/`catch` block to catch an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="6138b-110">В примере создается класс `Employee` с единственным свойством — уровнем сотрудника (`Emlevel`).</span><span class="sxs-lookup"><span data-stu-id="6138b-110">The sample creates a class called `Employee` with a single property, employee level (`Emlevel`).</span></span> <span data-ttu-id="6138b-111">Метод `PromoteEmployee` принимает объект и повышает уровень сотрудника.</span><span class="sxs-lookup"><span data-stu-id="6138b-111">A method, `PromoteEmployee`, takes an object and increments the employee level.</span></span> <span data-ttu-id="6138b-112">Исключение <xref:System.InvalidCastException> возникает, когда в метод `PromoteEmployee` передается экземпляр <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="6138b-112">An <xref:System.InvalidCastException> occurs when a <xref:System.DateTime> instance is passed to the `PromoteEmployee` method.</span></span>

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)] 

## <a name="see-also"></a><span data-ttu-id="6138b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6138b-113">See also</span></span>

- [<span data-ttu-id="6138b-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="6138b-114">Exceptions</span></span>](index.md)
