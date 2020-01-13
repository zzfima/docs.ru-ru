---
title: Практическое руководство. Явное создание исключений
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 750da20b8c1c40901cc363ac0eff8af888821ce9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708866"
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="d63f5-102">Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="d63f5-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="d63f5-103">Исключение можно вызвать явным образом с помощью C# [`throw`](../../csharp/language-reference/keywords/throw.md) или оператора Visual Basic [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d63f5-103">You can explicitly throw an exception using the C# [`throw`](../../csharp/language-reference/keywords/throw.md) or the Visual Basic [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) statement.</span></span> <span data-ttu-id="d63f5-104">Перехваченное исключение можно вызвать повторно с помощью оператора `throw`.</span><span class="sxs-lookup"><span data-stu-id="d63f5-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="d63f5-105">При написании кода рекомендуется добавлять сведения в исключение, которое выдается повторно, чтобы предоставить дополнительную информацию при отладке.</span><span class="sxs-lookup"><span data-stu-id="d63f5-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="d63f5-106">В следующем примере кода блок `try`/`catch` используется, чтобы перехватить возможное <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="d63f5-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="d63f5-107">После блока `try` находится блок `catch`, который перехватывает <xref:System.IO.FileNotFoundException> и выводит сообщение в консоль, если файл данных не найден.</span><span class="sxs-lookup"><span data-stu-id="d63f5-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="d63f5-108">Следующий оператор `throw` создает новое исключение <xref:System.IO.FileNotFoundException> и добавляет в него текстовую информацию.</span><span class="sxs-lookup"><span data-stu-id="d63f5-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="d63f5-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d63f5-109">See also</span></span>

- [<span data-ttu-id="d63f5-110">Исключения</span><span class="sxs-lookup"><span data-stu-id="d63f5-110">Exceptions</span></span>](index.md)
