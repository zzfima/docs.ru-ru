---
title: "Практическое руководство. Выполнение кода очистки с использованием блока finally (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b1f7bccacf20a9322f4de75740cdc34b4a97fa4c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="df06f-102">Практическое руководство. Выполнение кода очистки с использованием блока finally (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="df06f-102">How to: Execute Cleanup Code Using finally (C# Programming Guide)</span></span>
<span data-ttu-id="df06f-103">Оператор `finally` позволяет гарантировать, что необходимая очистка объектов, как правило, объектов, занимающих внешние ресурсы, возникает немедленно, даже при создании исключения.</span><span class="sxs-lookup"><span data-stu-id="df06f-103">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="df06f-104">Примером подобной очистки является вызов <xref:System.IO.Stream.Close%2A> для <xref:System.IO.FileStream> сразу после использования вместо ожидания сборки мусора, выполняемой для объекта средой CLR, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="df06f-104">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>  
  
 <span data-ttu-id="df06f-105">[!code-cs[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="df06f-105">[!code-cs[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="df06f-106">Пример</span><span class="sxs-lookup"><span data-stu-id="df06f-106">Example</span></span>  
 <span data-ttu-id="df06f-107">Чтобы преобразовать предыдущий код в оператор `try-catch-finally`, код очистки отделяется от рабочего кода следующим образом:</span><span class="sxs-lookup"><span data-stu-id="df06f-107">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>  
  
 <span data-ttu-id="df06f-108">[!code-cs[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="df06f-108">[!code-cs[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]</span></span>  
  
 <span data-ttu-id="df06f-109">Так как исключение может возникнуть в любой момент в блоке `try` до вызова `OpenWrite()`, или может произойти сбой самого вызова `OpenWrite()`, мы не можем гарантировать, что файл будет открыт при попытке закрыть его.</span><span class="sxs-lookup"><span data-stu-id="df06f-109">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we are not guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="df06f-110">Блок `finally` добавляет проверку того, что объект <xref:System.IO.FileStream> имеет отличное от `null` значение, прежде чем будет вызван метод <xref:System.IO.Stream.Close%2A>.</span><span class="sxs-lookup"><span data-stu-id="df06f-110">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object is not `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="df06f-111">Без проверки `null` блок `finally` может создавать собственное исключение <xref:System.NullReferenceException>, однако создания исключений в блоках `finally` следует по возможности избегать.</span><span class="sxs-lookup"><span data-stu-id="df06f-111">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it is possible.</span></span>  
  
 <span data-ttu-id="df06f-112">Подключение к базе данных — еще один подходящий кандидат для заключения в блок `finally`.</span><span class="sxs-lookup"><span data-stu-id="df06f-112">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="df06f-113">Так как количество разрешенных подключений к серверу базы данных иногда ограничено, закрывать подключения к базе данных рекомендуется как можно быстрее.</span><span class="sxs-lookup"><span data-stu-id="df06f-113">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="df06f-114">Если перед закрытием подключения возникает исключение, это еще один случай, когда использование блока `finally` предпочтительнее, чем ожидание сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="df06f-114">If an exception is thrown before you can close your connection, this is another case where using the `finally` block is better than waiting for garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df06f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="df06f-115">See Also</span></span>  
 <span data-ttu-id="df06f-116">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="df06f-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="df06f-117">[Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="df06f-117">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="df06f-118">[Обработка исключений](../../../csharp/programming-guide/exceptions/exception-handling.md) </span><span class="sxs-lookup"><span data-stu-id="df06f-118">[Exception Handling](../../../csharp/programming-guide/exceptions/exception-handling.md) </span></span>  
 <span data-ttu-id="df06f-119">[Оператор using](../../../csharp/language-reference/keywords/using-statement.md) </span><span class="sxs-lookup"><span data-stu-id="df06f-119">[using Statement](../../../csharp/language-reference/keywords/using-statement.md) </span></span>  
 <span data-ttu-id="df06f-120">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="df06f-120">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="df06f-121">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span><span class="sxs-lookup"><span data-stu-id="df06f-121">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span></span>  
 [<span data-ttu-id="df06f-122">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="df06f-122">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)

