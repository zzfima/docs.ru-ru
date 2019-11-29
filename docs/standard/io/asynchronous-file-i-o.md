---
title: Асинхронный файловый ввод-вывод
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, synchronous streams
- asynchronous I/O
- synchronous I/O
- streams, asynchronous streams
- I/O [.NET Framework], asynchronous I/O
- Stream class, synchronous I/O
- data streams, asynchronous streams
- Stream class, asynchronous I/O
- multiple I/O requests
- data streams, synchronous streams
ms.assetid: dbdd55e7-d6b9-4f9e-8abb-ab0edd4457f7
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b39373239d6aefaa671afebbb85dc2156866358f
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204809"
---
# <a name="asynchronous-file-io"></a><span data-ttu-id="58d3b-102">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="58d3b-102">Asynchronous File I/O</span></span>

<span data-ttu-id="58d3b-103">Асинхронные операции позволяют выполнять ресурсоемкие операции ввода-вывода без блокировки основного потока.</span><span class="sxs-lookup"><span data-stu-id="58d3b-103">Asynchronous operations enable you to perform resource-intensive I/O operations without blocking the main thread.</span></span> <span data-ttu-id="58d3b-104">Это соображение, связанное с производительностью, особенно важно в приложениях Магазина Windows 8.x и классических приложениях, в которых длительная потоковая операция может блокировать поток пользовательского интерфейса и создавать впечатление, что приложение не работает.</span><span class="sxs-lookup"><span data-stu-id="58d3b-104">This performance consideration is particularly important in a Windows 8.x Store app or desktop app where a time-consuming stream operation can block the UI thread and make your app appear as if it is not working.</span></span>

<span data-ttu-id="58d3b-105">Начиная с .NET Framework 4.5 для упрощения асинхронных операций типы ввода-вывода включают в себя асинхронные методы.</span><span class="sxs-lookup"><span data-stu-id="58d3b-105">Starting with the .NET Framework 4.5, the I/O types include async methods to simplify asynchronous operations.</span></span> <span data-ttu-id="58d3b-106">Асинхронный метод содержит `Async` в своем имени, например <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>и <xref:System.IO.TextReader.ReadToEndAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="58d3b-106">An async method contains `Async` in its name, such as <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>, and <xref:System.IO.TextReader.ReadToEndAsync%2A>.</span></span> <span data-ttu-id="58d3b-107">Эти асинхронные методы реализуются на базе классов потоков, таких как <xref:System.IO.Stream>, <xref:System.IO.FileStream>и <xref:System.IO.MemoryStream>, а также классов, используемых для чтения или записи данных в потоках, таких как <xref:System.IO.TextReader> и <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="58d3b-107">These async methods are implemented on stream classes, such as <xref:System.IO.Stream>, <xref:System.IO.FileStream>, and <xref:System.IO.MemoryStream>, and on classes that are used for reading from or writing to streams, such <xref:System.IO.TextReader> and <xref:System.IO.TextWriter>.</span></span>

<span data-ttu-id="58d3b-108">В платформе .NET Framework 4 и более ранних версий для реализации операций асинхронного ввода-вывода необходимо использовать такие методы, как <xref:System.IO.Stream.BeginRead%2A> и <xref:System.IO.Stream.EndRead%2A> .</span><span class="sxs-lookup"><span data-stu-id="58d3b-108">In the .NET Framework 4 and earlier versions, you have to use methods such as <xref:System.IO.Stream.BeginRead%2A> and <xref:System.IO.Stream.EndRead%2A> to implement asynchronous I/O operations.</span></span> <span data-ttu-id="58d3b-109">Эти методы по-прежнему доступны в .NET Framework 4.5 для поддержки устаревшего кода. Однако асинхронные методы позволяют реализовать операции асинхронного ввода-вывода гораздо проще.</span><span class="sxs-lookup"><span data-stu-id="58d3b-109">These methods are still available in the .NET Framework 4.5 to support legacy code; however, the async methods help you implement asynchronous I/O operations more easily.</span></span>

<span data-ttu-id="58d3b-110">Языки C# и Visual Basic имеют по два ключевых слова для асинхронного программирования:</span><span class="sxs-lookup"><span data-stu-id="58d3b-110">C# and Visual Basic each have two keywords for asynchronous programming:</span></span>

- <span data-ttu-id="58d3b-111">Модификатор`Async` (Visual Basic) или `async` (C#), который используется для пометки метода, содержащего асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="58d3b-111">`Async` (Visual Basic) or `async` (C#) modifier, which is used to mark a method that contains an asynchronous operation.</span></span>

- <span data-ttu-id="58d3b-112">Оператор`Await` (Visual Basic) или `await` (C#), который применяется к результату асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="58d3b-112">`Await` (Visual Basic) or `await` (C#) operator, which is applied to the result of an async method.</span></span>

<span data-ttu-id="58d3b-113">Для реализации операций асинхронного ввода-вывода используйте эти ключевые слова в сочетании с асинхронными методами, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="58d3b-113">To implement asynchronous I/O operations, use these keywords in conjunction with the async methods, as shown in the following examples.</span></span> <span data-ttu-id="58d3b-114">Дополнительные сведения см. в статье [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](../../csharp/programming-guide/concepts/async/index.md) или статье [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="58d3b-114">For more information, see [Asynchronous programming with async and await (C#)](../../csharp/programming-guide/concepts/async/index.md) or [Asynchronous Programming with Async and Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="58d3b-115">Следующий пример демонстрирует использование двух объектов <xref:System.IO.FileStream> для асинхронного копирования файлов из одного каталога в другой.</span><span class="sxs-lookup"><span data-stu-id="58d3b-115">The following example demonstrates how to use two <xref:System.IO.FileStream> objects to copy files asynchronously from one directory to another.</span></span> <span data-ttu-id="58d3b-116">Обратите внимание, что обработчик событий <xref:System.Web.UI.WebControls.Button.Click> для элемента управления <xref:System.Windows.Controls.Button> помечается с помощью модификатора `async` , так как вызывает асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="58d3b-116">Notice that the <xref:System.Web.UI.WebControls.Button.Click> event handler for the <xref:System.Windows.Controls.Button> control is marked with the `async` modifier because it calls an asynchronous method.</span></span>

[!code-csharp[Asynchronous_File_IO_async#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example.cs#1)]
[!code-vb[Asynchronous_File_IO_async#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example.vb#1)]

<span data-ttu-id="58d3b-117">Следующий пример похож на предыдущий, но использует объекты <xref:System.IO.StreamReader> и <xref:System.IO.StreamWriter> для чтения и записи содержимого текстового файла в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="58d3b-117">The next example is similar to the previous one but uses <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> objects to read and write the contents of a text file asynchronously.</span></span>

[!code-csharp[Asynchronous_File_IO_async#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example2.cs#2)]
[!code-vb[Asynchronous_File_IO_async#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example2.vb#2)]

<span data-ttu-id="58d3b-118">В приведенном ниже примере показан файл кода программной части и XAML-файл, которые используются, чтобы открыть файл в виде <xref:System.IO.Stream> в приложении Магазина Windows 8.x и считать его содержимое с помощью экземпляра класса <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="58d3b-118">The next example shows the code-behind file and the XAML file that are used to open a file as a <xref:System.IO.Stream> in a Windows 8.x Store app, and read its contents by using an instance of the <xref:System.IO.StreamReader> class.</span></span> <span data-ttu-id="58d3b-119">Здесь асинхронные методы используются для открытия файла в виде потока и чтения его содержимого.</span><span class="sxs-lookup"><span data-stu-id="58d3b-119">It uses asynchronous methods to open the file as a stream and to read its contents.</span></span>

[!code-csharp[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml.cs#2)]
[!code-vb[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/vb/blankpage.xaml.vb#2)]

[!code-xaml[System.IO.WindowsRuntimeStorageExtensions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml#1)]

## <a name="see-also"></a><span data-ttu-id="58d3b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="58d3b-120">See also</span></span>

- <xref:System.IO.Stream>
- [<span data-ttu-id="58d3b-121">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="58d3b-121">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="58d3b-122">Асинхронное программирование с использованием ключевых слов Async и Await (C#)</span><span class="sxs-lookup"><span data-stu-id="58d3b-122">Asynchronous programming with async and await (C#)</span></span>](../../csharp/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="58d3b-123">Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58d3b-123">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
