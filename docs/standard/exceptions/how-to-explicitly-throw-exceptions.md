---
title: "Практическое руководство. Явное создание исключения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c3fce332263dac3f9906d33fe3bd2590050b86f8
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="06c90-102">Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="06c90-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="06c90-103">Исключение можно вызвать явным образом с помощью оператора `throw`.</span><span class="sxs-lookup"><span data-stu-id="06c90-103">You can explicitly throw an exception using the `throw` statement.</span></span> <span data-ttu-id="06c90-104">Перехваченное исключение можно вызвать повторно с помощью оператора `throw`.</span><span class="sxs-lookup"><span data-stu-id="06c90-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="06c90-105">При написании кода рекомендуется добавлять сведения в исключение, которое выдается повторно, чтобы предоставить дополнительную информацию при отладке.</span><span class="sxs-lookup"><span data-stu-id="06c90-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="06c90-106">В следующем примере кода блок `try`/`catch` используется, чтобы перехватить возможное <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="06c90-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="06c90-107">После блока `try` находится блок `catch`, который перехватывает <xref:System.IO.FileNotFoundException> и выводит сообщение в консоль, если файл данных не найден.</span><span class="sxs-lookup"><span data-stu-id="06c90-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="06c90-108">Следующий оператор `throw` создает новое исключение <xref:System.IO.FileNotFoundException> и добавляет в него текстовую информацию.</span><span class="sxs-lookup"><span data-stu-id="06c90-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="06c90-109">См. также</span><span class="sxs-lookup"><span data-stu-id="06c90-109">See Also</span></span>  
[<span data-ttu-id="06c90-110">Исключения</span><span class="sxs-lookup"><span data-stu-id="06c90-110">Exceptions</span></span>](index.md)
