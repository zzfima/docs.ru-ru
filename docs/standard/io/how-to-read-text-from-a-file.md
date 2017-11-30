---
title: "Практическое руководство. Считывание текста из файла"
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
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
caps.latest.revision: "23"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 026f6ae4dd9aee340d6a9ffb931d0525ae75654a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="81da6-102">Практическое руководство. Считывание текста из файла</span><span class="sxs-lookup"><span data-stu-id="81da6-102">How to: Read Text from a File</span></span>
<span data-ttu-id="81da6-103">В следующих примерах демонстрируется синхронное и асинхронное чтение текста из текстового файла с использованием .NET для классических приложений.</span><span class="sxs-lookup"><span data-stu-id="81da6-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="81da6-104">В обоих примерах при создании экземпляра класса <xref:System.IO.StreamReader> указывается относительный или абсолютный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="81da6-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span> <span data-ttu-id="81da6-105">В следующих примерах предполагается, что файл с именем TestFile.txt находится в той же папке, что и приложение.</span><span class="sxs-lookup"><span data-stu-id="81da6-105">The following examples assume that the file named TestFile.txt is in the same folder as the application.</span></span>  
  
 <span data-ttu-id="81da6-106">Эти примеры кода не относятся к разработке приложений для Магазина Windows, поскольку в среде выполнения Windows используются разные типы потоков для чтения и записи файлов.</span><span class="sxs-lookup"><span data-stu-id="81da6-106">These code examples do not apply developing for Windows Store Apps because the Windows Runtime provides different streams types reading and writing to files.</span></span> <span data-ttu-id="81da6-107">Пример, демонстрирующий чтение текста из файла в контексте приложения для магазина Windows см. в разделе [краткое руководство: чтение и запись файлов](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx).</span><span class="sxs-lookup"><span data-stu-id="81da6-107">For an example that shows how to read text from a file within the context of a Windows Store app, see [Quickstart: Reading and writing files](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx).</span></span> <span data-ttu-id="81da6-108">Примеры, демонстрирующие преобразование между потоками .NET Framework и потоками среды выполнения Windows см. в разделе [как: преобразование между потоками .NET Framework и потоками среды выполнения Windows](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="81da6-108">For examples that show how to convert between .NET Framework streams and Windows runtime streams see [How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81da6-109">Пример</span><span class="sxs-lookup"><span data-stu-id="81da6-109">Example</span></span>  
 <span data-ttu-id="81da6-110">Первый пример иллюстрирует синхронную операцию чтения в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="81da6-110">The first example shows a synchronous read operation within a console application.</span></span> <span data-ttu-id="81da6-111">В этом примере текстовый файл открывается с помощью модуля чтения потока, содержимое копируется в строку, а строка выводится на консоль.</span><span class="sxs-lookup"><span data-stu-id="81da6-111">In this example, the text file is opened using a stream reader, the contents are copied to a string and string is output to the console.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="81da6-112">Пример</span><span class="sxs-lookup"><span data-stu-id="81da6-112">Example</span></span>  
 <span data-ttu-id="81da6-113">Второй пример иллюстрирует асинхронную операцию чтения в приложении Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="81da6-113">The second example shows an asynchronous read operation within a Windows Presentation Foundation (WPF) application.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="81da6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="81da6-114">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="81da6-115">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="81da6-115">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="81da6-116">NIB: Практическое: Создание списка каталогов</span><span class="sxs-lookup"><span data-stu-id="81da6-116">NIB: How to: Create a Directory Listing</span></span>](http://msdn.microsoft.com/en-us/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [<span data-ttu-id="81da6-117">Краткое руководство: Чтение и запись файлов</span><span class="sxs-lookup"><span data-stu-id="81da6-117">Quickstart: Reading and writing files</span></span>](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)  
 [<span data-ttu-id="81da6-118">Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="81da6-118">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [<span data-ttu-id="81da6-119">Практическое руководство. Считывание из нового файла данных и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="81da6-119">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="81da6-120">Практическое руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="81da6-120">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="81da6-121">Практическое руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="81da6-121">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="81da6-122">Практическое руководство. Считывание символов из строки</span><span class="sxs-lookup"><span data-stu-id="81da6-122">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="81da6-123">Практическое руководство. Запись символов в строку</span><span class="sxs-lookup"><span data-stu-id="81da6-123">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="81da6-124">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="81da6-124">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
