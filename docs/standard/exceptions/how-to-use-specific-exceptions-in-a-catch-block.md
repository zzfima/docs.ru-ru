---
title: Практическое руководство. Использование определенных исключений в блоке Catch
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 424db46c879974a9859637f9a2a5dfcd4494a3c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571802"
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a><span data-ttu-id="43e59-102">Практическое руководство. Использование определенных исключений в блоке catch</span><span class="sxs-lookup"><span data-stu-id="43e59-102">How to use specific exceptions in a catch block</span></span>

<span data-ttu-id="43e59-103">В общем случае вместо использования базового оператора `catch` рекомендуется перехватывать исключения определенного типа.</span><span class="sxs-lookup"><span data-stu-id="43e59-103">In general, it's good programming practice to catch a specific type of exception rather than use a basic `catch` statement.</span></span>

<span data-ttu-id="43e59-104">При возникновении исключения оно передается вверх по стеку, и каждый блок catch получает возможность обработать его.</span><span class="sxs-lookup"><span data-stu-id="43e59-104">When an exception occurs, it is passed up the stack and each catch block is given the opportunity to handle it.</span></span> <span data-ttu-id="43e59-105">Важен порядок операторов catch.</span><span class="sxs-lookup"><span data-stu-id="43e59-105">The order of catch statements is important.</span></span> <span data-ttu-id="43e59-106">Размещайте блоки catch, предназначенные для определенных исключений, до общего блока перехвата исключений. В противном случае компилятор может выдать ошибку.</span><span class="sxs-lookup"><span data-stu-id="43e59-106">Put catch blocks targeted to specific exceptions before a general exception catch block or the compiler might issue an error.</span></span> <span data-ttu-id="43e59-107">Соответствующий блок catch определяется путем соотнесения типа исключения с именем исключения, указанным в блоке catch.</span><span class="sxs-lookup"><span data-stu-id="43e59-107">The proper catch block is determined by matching the type of the exception to the name of the exception specified in the catch block.</span></span> <span data-ttu-id="43e59-108">Когда специальный блок catch отсутствует, исключение перехватывается общим блоком catch, если он существует.</span><span class="sxs-lookup"><span data-stu-id="43e59-108">If there is no specific catch block, the exception is caught by a general catch block, if one exists.</span></span>

<span data-ttu-id="43e59-109">В следующем примере кода блок `try`/`catch` используется, чтобы перехватить <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="43e59-109">The following code example uses a `try`/`catch` block to catch an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="43e59-110">В примере создается класс `Employee` с единственным свойством — уровнем сотрудника (`Emlevel`).</span><span class="sxs-lookup"><span data-stu-id="43e59-110">The sample creates a class called `Employee` with a single property, employee level (`Emlevel`).</span></span> <span data-ttu-id="43e59-111">Метод `PromoteEmployee` принимает объект и повышает уровень сотрудника.</span><span class="sxs-lookup"><span data-stu-id="43e59-111">A method, `PromoteEmployee`, takes an object and increments the employee level.</span></span> <span data-ttu-id="43e59-112">Исключение <xref:System.InvalidCastException> возникает, когда в метод `PromoteEmployee` передается экземпляр <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="43e59-112">An <xref:System.InvalidCastException> occurs when a <xref:System.DateTime> instance is passed to the `PromoteEmployee` method.</span></span>

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)] 

## <a name="see-also"></a><span data-ttu-id="43e59-113">См. также</span><span class="sxs-lookup"><span data-stu-id="43e59-113">See Also</span></span>  
[<span data-ttu-id="43e59-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="43e59-114">Exceptions</span></span>](index.md)
