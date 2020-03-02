---
title: Руководство. Запись текста в файл
ms.date: 01/04/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
ms.openlocfilehash: ba1c1815f0e49c02d1f0ee3c48ba01b7c2f5e727
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160252"
---
# <a name="how-to-write-text-to-a-file"></a><span data-ttu-id="e8594-102">Руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="e8594-102">How to: Write text to a file</span></span>
<span data-ttu-id="e8594-103">В этом разделе показаны различные способы записи текста в файл для приложения .NET.</span><span class="sxs-lookup"><span data-stu-id="e8594-103">This topic shows different ways to write text to a file for a .NET app.</span></span>

<span data-ttu-id="e8594-104">Для записи текста в файл обычно используются следующие классы и методы.</span><span class="sxs-lookup"><span data-stu-id="e8594-104">The following classes and methods are typically used to write text to a file:</span></span>  
  
- <span data-ttu-id="e8594-105"><xref:System.IO.StreamWriter> содержит методы для синхронной (<xref:System.IO.StreamWriter.Write%2A> или <xref:System.IO.TextWriter.WriteLine%2A>) или асинхронной (<xref:System.IO.StreamWriter.WriteAsync%2A> и <xref:System.IO.StreamWriter.WriteLineAsync%2A>) записи в файл.</span><span class="sxs-lookup"><span data-stu-id="e8594-105"><xref:System.IO.StreamWriter> contains methods to write to a file synchronously (<xref:System.IO.StreamWriter.Write%2A> and <xref:System.IO.TextWriter.WriteLine%2A>) or asynchronously (<xref:System.IO.StreamWriter.WriteAsync%2A> and <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span></span>  
  
- <span data-ttu-id="e8594-106"><xref:System.IO.File> предоставляет статические методы для записи текста в файл, такие как <xref:System.IO.File.WriteAllLines%2A> и <xref:System.IO.File.WriteAllText%2A>, или для добавления текста в файл (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> или <xref:System.IO.File.AppendText%2A>).</span><span class="sxs-lookup"><span data-stu-id="e8594-106"><xref:System.IO.File> provides static methods to write text to a file, such as <xref:System.IO.File.WriteAllLines%2A> and <xref:System.IO.File.WriteAllText%2A>, or to append text to a file, such as <xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A>, and <xref:System.IO.File.AppendText%2A>.</span></span>  
  
- <span data-ttu-id="e8594-107"><xref:System.IO.Path> предназначен для использования со строками, содержащими сведения о пути к файлу или каталогу.</span><span class="sxs-lookup"><span data-stu-id="e8594-107"><xref:System.IO.Path> is for strings that have file or directory path information.</span></span> <span data-ttu-id="e8594-108">Он содержит метод <xref:System.IO.Path.Combine%2A>; в .NET Core 2.1 и более поздних версиях также есть методы <xref:System.IO.Path.Join%2A> и <xref:System.IO.Path.TryJoin%2A>, которые позволяют объединять строки для создания пути к файлу или каталогу.</span><span class="sxs-lookup"><span data-stu-id="e8594-108">It contains the <xref:System.IO.Path.Combine%2A> method and, in .NET Core 2.1 and later, the <xref:System.IO.Path.Join%2A> and <xref:System.IO.Path.TryJoin%2A> methods, which allow concatenation of strings to build a file or directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="e8594-109">Нижеприведенные примеры демонстрируют минимальный объем необходимого кода.</span><span class="sxs-lookup"><span data-stu-id="e8594-109">The following examples show only the minimum amount of code needed.</span></span> <span data-ttu-id="e8594-110">Реальное приложение обычно обеспечивает более надежную проверку ошибок и обработку исключений.</span><span class="sxs-lookup"><span data-stu-id="e8594-110">A real-world app usually provides more robust error checking and exception handling.</span></span>  
  
## <a name="example-synchronously-write-text-with-streamwriter"></a><span data-ttu-id="e8594-111">Пример Синхронная запись текста с помощью StreamWriter</span><span class="sxs-lookup"><span data-stu-id="e8594-111">Example: Synchronously write text with StreamWriter</span></span>

<span data-ttu-id="e8594-112">В следующем примере показано, как синхронно записать текст в новый файл с помощью класса <xref:System.IO.StreamWriter> по одной строке за раз.</span><span class="sxs-lookup"><span data-stu-id="e8594-112">The following example shows how to use the <xref:System.IO.StreamWriter> class to synchronously write text to a new file one line at a time.</span></span> <span data-ttu-id="e8594-113">Поскольку объект <xref:System.IO.StreamWriter> объявляется и создается в инструкции `using`, вызывается метод <xref:System.IO.StreamWriter.Dispose%2A>, который автоматически выполняет очистку и закрывает поток.</span><span class="sxs-lookup"><span data-stu-id="e8594-113">Because the <xref:System.IO.StreamWriter> object is declared and instantiated in a `using` statement, the <xref:System.IO.StreamWriter.Dispose%2A> method is invoked, which automatically flushes and closes the stream.</span></span>  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/write.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/write.vb)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="example-synchronously-append-text-with-streamwriter"></a><span data-ttu-id="e8594-114">Пример Синхронное добавление текста с помощью StreamWriter</span><span class="sxs-lookup"><span data-stu-id="e8594-114">Example: Synchronously append text with StreamWriter</span></span>

<span data-ttu-id="e8594-115">В следующем примере показано, как использовать класс <xref:System.IO.StreamWriter>, чтобы синхронно добавить текст в текстовый файл, созданный в первом примере.</span><span class="sxs-lookup"><span data-stu-id="e8594-115">The following example shows how to use the <xref:System.IO.StreamWriter> class to synchronously append text to the text file created in the first example.</span></span>

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/append.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/append.vb)]  

## <a name="example-asynchronously-write-text-with-streamwriter"></a><span data-ttu-id="e8594-116">Пример Асинхронная запись текста с помощью StreamWriter</span><span class="sxs-lookup"><span data-stu-id="e8594-116">Example: Asynchronously write text with StreamWriter</span></span>

<span data-ttu-id="e8594-117">В следующем примере показано, как асинхронно записать текст в новый файл с помощью класса <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="e8594-117">The following example shows how to asynchronously write text to a new file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="e8594-118">Вызов метода <xref:System.IO.StreamWriter.WriteAsync%2A> должен находиться в методе `async`.</span><span class="sxs-lookup"><span data-stu-id="e8594-118">To invoke the <xref:System.IO.StreamWriter.WriteAsync%2A> method, the method call must be within an `async` method.</span></span> <span data-ttu-id="e8594-119">Для примера на C# требуется C# 7.1 или более поздней версии, где добавлена поддержка модификатора `async` для точки входа программы.</span><span class="sxs-lookup"><span data-stu-id="e8594-119">The C# example requires C# 7.1 or later, which adds support for the `async` modifier on the program entry point.</span></span>

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/async.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/async.vb)]  

## <a name="example-write-and-append-text-with-the-file-class"></a><span data-ttu-id="e8594-120">Пример Запись и добавление текста с помощью класса File</span><span class="sxs-lookup"><span data-stu-id="e8594-120">Example: Write and append text with the File class</span></span>

<span data-ttu-id="e8594-121">В следующем примере показано, как записать текст в новый файл и добавить новые строки текста в тот же файл с помощью класса <xref:System.IO.File> .</span><span class="sxs-lookup"><span data-stu-id="e8594-121">The following example shows how to write text to a new file and append new lines of text to the same file using the <xref:System.IO.File> class.</span></span> <span data-ttu-id="e8594-122">Методы <xref:System.IO.File.WriteAllText%2A> и <xref:System.IO.File.AppendAllLines%2A> открывают и закрывают файл автоматически.</span><span class="sxs-lookup"><span data-stu-id="e8594-122">The <xref:System.IO.File.WriteAllText%2A> and <xref:System.IO.File.AppendAllLines%2A> methods open and close the file automatically.</span></span> <span data-ttu-id="e8594-123">Если предоставленный в методе <xref:System.IO.File.WriteAllText%2A> путь уже существует, файл будет перезаписан.</span><span class="sxs-lookup"><span data-stu-id="e8594-123">If the path you provide to the <xref:System.IO.File.WriteAllText%2A> method already exists, the file is overwritten.</span></span>  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/file.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/file.vb)]  

## <a name="see-also"></a><span data-ttu-id="e8594-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e8594-124">See also</span></span>

- <xref:System.IO.StreamWriter>
- <xref:System.IO.Path>
- <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e8594-125">Руководство. Перечисление каталогов и файлов</span><span class="sxs-lookup"><span data-stu-id="e8594-125">How to: Enumerate directories and files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)
- [<span data-ttu-id="e8594-126">Руководство. Считывание данных из нового файла и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="e8594-126">How to: Read and write to a newly-created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [<span data-ttu-id="e8594-127">Руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="e8594-127">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [<span data-ttu-id="e8594-128">Руководство. Чтение текста из файла</span><span class="sxs-lookup"><span data-stu-id="e8594-128">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [<span data-ttu-id="e8594-129">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="e8594-129">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
