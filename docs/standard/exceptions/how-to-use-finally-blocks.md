---
title: Практическое руководство. Использование блоков Finally
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
ms.openlocfilehash: 44fbb53437c4c8f19a424227a167e2e268b77057
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708836"
---
# <a name="how-to-use-finally-blocks"></a><span data-ttu-id="4d900-102">Использование блоков finally</span><span class="sxs-lookup"><span data-stu-id="4d900-102">How to use finally blocks</span></span>

<span data-ttu-id="4d900-103">При возникновении исключения выполнение останавливается, и управление передается соответствующему обработчику исключений.</span><span class="sxs-lookup"><span data-stu-id="4d900-103">When an exception occurs, execution stops and control is given to the appropriate exception handler.</span></span> <span data-ttu-id="4d900-104">Часто это означает, что ожидаемые вами строки кода пропускаются.</span><span class="sxs-lookup"><span data-stu-id="4d900-104">This often means that lines of code you expect to be executed are bypassed.</span></span> <span data-ttu-id="4d900-105">Даже при возникновении исключения требуется определенная очистка ресурсов, например закрытие файла.</span><span class="sxs-lookup"><span data-stu-id="4d900-105">Some resource cleanup, such as closing a file, needs to be done even if an exception is thrown.</span></span> <span data-ttu-id="4d900-106">Для этого можно использовать блок `finally`.</span><span class="sxs-lookup"><span data-stu-id="4d900-106">To do this, you can use a `finally` block.</span></span> <span data-ttu-id="4d900-107">Блок `finally` выполняются всегда, независимо от того, возникает ли исключение.</span><span class="sxs-lookup"><span data-stu-id="4d900-107">A `finally` block always executes, regardless of whether an exception is thrown.</span></span>

<span data-ttu-id="4d900-108">В следующем примере кода блок `try`/`catch` используется, чтобы перехватить <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="4d900-108">The following code example uses a `try`/`catch` block to catch an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="4d900-109">Метод `Main` создает два массива и пытается скопировать один из них в другой.</span><span class="sxs-lookup"><span data-stu-id="4d900-109">The `Main` method creates two arrays and attempts to copy one to the other.</span></span> <span data-ttu-id="4d900-110">Это действие создает исключение <xref:System.ArgumentOutOfRangeException>, и ошибка выводится на консоль.</span><span class="sxs-lookup"><span data-stu-id="4d900-110">The action generates an <xref:System.ArgumentOutOfRangeException> and the error is written to the console.</span></span> <span data-ttu-id="4d900-111">Блок `finally` выполняется вне зависимости от результата операции копирования.</span><span class="sxs-lookup"><span data-stu-id="4d900-111">The `finally` block executes regardless of the outcome of the copy action.</span></span>

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="4d900-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4d900-112">See also</span></span>

- [<span data-ttu-id="4d900-113">Исключения</span><span class="sxs-lookup"><span data-stu-id="4d900-113">Exceptions</span></span>](index.md)
