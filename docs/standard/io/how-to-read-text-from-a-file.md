---
title: Практическое руководство. Считывание текста из файла
ms.date: 06/19/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ffc8c88f01ba10bceb4f768f38ae9b1dcc4148e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43422179"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="d3957-102">Практическое руководство. Считывание текста из файла</span><span class="sxs-lookup"><span data-stu-id="d3957-102">How to: Read Text from a File</span></span>
<span data-ttu-id="d3957-103">В следующих примерах демонстрируется синхронное и асинхронное чтение текста из текстового файла с использованием .NET для классических приложений.</span><span class="sxs-lookup"><span data-stu-id="d3957-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="d3957-104">В обоих примерах при создании экземпляра класса <xref:System.IO.StreamReader> указывается относительный или абсолютный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="d3957-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span> <span data-ttu-id="d3957-105">В следующих примерах предполагается, что файл с именем TestFile.txt находится в той же папке, что и приложение.</span><span class="sxs-lookup"><span data-stu-id="d3957-105">The following examples assume that the file named TestFile.txt is in the same folder as the application.</span></span>  
  
 <span data-ttu-id="d3957-106">Эти примеры кода не относятся к разработке приложений для Microsoft Store, поскольку в среде выполнения Windows используются разные типы потоков для чтения и записи файлов.</span><span class="sxs-lookup"><span data-stu-id="d3957-106">These code examples do not apply to developing for Windows Store Apps because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="d3957-107">Пример чтения текста из файла в приложении Microsoft Store см. в разделе [Краткое руководство. Чтение и запись файлов](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="d3957-107">For an example that shows how to read text from a file in a Windows Store app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="d3957-108">Примеры преобразования между потоками NET Framework и потоками среды выполнения Windows см. в разделе [Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="d3957-108">For examples that show how to convert between .NET Framework streams and Windows runtime streams, see [How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3957-109">Пример</span><span class="sxs-lookup"><span data-stu-id="d3957-109">Example</span></span>  
 <span data-ttu-id="d3957-110">Следующий пример иллюстрирует синхронную операцию чтения в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="d3957-110">The following example shows a synchronous read operation within a console application.</span></span> <span data-ttu-id="d3957-111">В этом примере текстовый файл открывается с помощью средства чтения потока, содержимое копируется в строку, а строка выводится на консоль.</span><span class="sxs-lookup"><span data-stu-id="d3957-111">In this example, the text file is opened using a stream reader, the contents are copied to a string, and the string is output to the console.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="d3957-112">Пример</span><span class="sxs-lookup"><span data-stu-id="d3957-112">Example</span></span>  
 <span data-ttu-id="d3957-113">Следующий пример иллюстрирует асинхронную операцию чтения в приложении Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="d3957-113">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d3957-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d3957-114">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="d3957-115">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="d3957-115">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="d3957-116">Практическое руководство. Создание списка каталогов</span><span class="sxs-lookup"><span data-stu-id="d3957-116">NIB: How to: Create a Directory Listing</span></span>](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [<span data-ttu-id="d3957-117">Краткое руководство. Чтение и запись файлов</span><span class="sxs-lookup"><span data-stu-id="d3957-117">Quickstart: Reading and writing files</span></span>](https://msdn.microsoft.com/library/windows/apps/hh758325.aspx)  
 [<span data-ttu-id="d3957-118">Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="d3957-118">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [<span data-ttu-id="d3957-119">Практическое руководство. Считывание из нового файла данных и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="d3957-119">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="d3957-120">Практическое руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="d3957-120">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="d3957-121">Практическое руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="d3957-121">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="d3957-122">Практическое руководство. Считывание символов из строки</span><span class="sxs-lookup"><span data-stu-id="d3957-122">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="d3957-123">Практическое руководство. Запись символов в строку</span><span class="sxs-lookup"><span data-stu-id="d3957-123">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="d3957-124">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="d3957-124">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
