---
title: Практическое руководство. Использование пробного блока и блока перехвата для перехвата исключений
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 852df5cb3eeea2ee5fa44ddce2f97e9c4f8d8b5a
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46699317"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="19b2d-102">Использование блока try/catch для перехвата исключений</span><span class="sxs-lookup"><span data-stu-id="19b2d-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="19b2d-103">Поместите фрагмент кода, который может выдавать исключения, в `try` блок, а код, который обрабатывает исключения, — в блок `catch`.</span><span class="sxs-lookup"><span data-stu-id="19b2d-103">Place the sections of code that might throw exceptions in a `try` block and place code that handles exceptions in a `catch` block.</span></span> <span data-ttu-id="19b2d-104">Блок `catch` — это последовательность операторов, начинающаяся с ключевого слова `catch`, за которым следует тип исключения и требуемое действие.</span><span class="sxs-lookup"><span data-stu-id="19b2d-104">The `catch` block is a series of statements beginning with the keyword `catch`, followed by an exception type and an action to be taken.</span></span>

<span data-ttu-id="19b2d-105">В следующем примере кода блок `try`/`catch` используется для перехвата возможного исключения.</span><span class="sxs-lookup"><span data-stu-id="19b2d-105">The following code example uses a `try`/`catch` block to catch a possible exception.</span></span> <span data-ttu-id="19b2d-106">Метод `Main` содержит блок `try` с оператором <xref:System.IO.StreamReader>, который открывает файл данных `data.txt` и записывает строку из этого файла.</span><span class="sxs-lookup"><span data-stu-id="19b2d-106">The `Main` method contains a `try` block with a <xref:System.IO.StreamReader> statement that opens a data file called `data.txt` and writes a string from the file.</span></span> <span data-ttu-id="19b2d-107">Следующий блок `try` — это блок `catch`, который перехватывает все исключения, поступающие из блока `try`.</span><span class="sxs-lookup"><span data-stu-id="19b2d-107">Following the `try` block is a `catch` block that catches any exception that results from the `try` block.</span></span>

 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

<span data-ttu-id="19b2d-108">Среда CLR перехватывает исключения, которые не перехватываются блоком catch.</span><span class="sxs-lookup"><span data-stu-id="19b2d-108">The common language runtime catches exceptions that are not caught by a catch block.</span></span> <span data-ttu-id="19b2d-109">В зависимости от настроек среды выполнения появляется диалоговое окно отладки, работа программы завершается и отображается диалоговое окно со сведениями об исключении либо ошибка выводится в STDERR.</span><span class="sxs-lookup"><span data-stu-id="19b2d-109">Depending on how the runtime is configured, a debug dialog box appears, or the program stops executing and a dialog box with exception information appears, or an error is printed out to STDERR.</span></span>

> [!NOTE] 
> <span data-ttu-id="19b2d-110">Исключение может быть вызвано практически любой строкой кода, особенно те исключения, которые вызываются самой средой CLR, например <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="19b2d-110">Almost any line of code can cause an exception, particularly exceptions that are thrown by the common language runtime itself, such as <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="19b2d-111">Большинству приложений не требуется обрабатывать эти исключения, но вы должны помнить об этом при написании библиотек, предназначенных для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="19b2d-111">Most applications don't have to deal with these exceptions, but you should be aware of this possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="19b2d-112">Рекомендации о том, когда следует помещать код в блок Try, см. в разделе о [лучших методиках обработки исключений](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="19b2d-112">For suggestions on when to set code in a Try block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="19b2d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="19b2d-113">See also</span></span>

- [<span data-ttu-id="19b2d-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="19b2d-114">Exceptions</span></span>](index.md)
