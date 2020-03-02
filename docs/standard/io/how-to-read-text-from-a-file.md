---
title: Руководство. Чтение текста из файла
ms.date: 01/03/2019
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
ms.openlocfilehash: 8676e5f0acd0646b4854df7dde060ec15548ec3e
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155728"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="071a5-102">Руководство. Чтение текста из файла</span><span class="sxs-lookup"><span data-stu-id="071a5-102">How to: Read text from a file</span></span>
<span data-ttu-id="071a5-103">В следующих примерах демонстрируется синхронное и асинхронное чтение текста из текстового файла с использованием .NET для классических приложений.</span><span class="sxs-lookup"><span data-stu-id="071a5-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="071a5-104">В обоих примерах при создании экземпляра класса <xref:System.IO.StreamReader> указывается относительный или абсолютный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="071a5-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="071a5-105">Эти примеры кода не относятся к разработке приложений Universal Windows (UWP), поскольку в среде выполнения Windows используются разные типы потоков для чтения и записи файлов.</span><span class="sxs-lookup"><span data-stu-id="071a5-105">These code examples do not apply to developing for Universal Windows (UWP) apps, because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="071a5-106">Пример чтения текста из файла в приложении UWP см. в разделе [Краткое руководство. Чтение и запись файлов](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="071a5-106">For an example that shows how to read text from a file in a UWP app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="071a5-107">Примеры, демонстрирующие преобразование потоков .NET Framework в потоки среды выполнения Windows и наоборот, см. в разделе [Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="071a5-107">For examples that show how to convert between .NET Framework streams and Windows Runtime streams, see [How to: Convert between .NET Framework streams and Windows Runtime streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example-synchronous-read-in-a-console-app"></a><span data-ttu-id="071a5-108">Пример Синхронное чтение в консольном приложении</span><span class="sxs-lookup"><span data-stu-id="071a5-108">Example: Synchronous read in a console app</span></span>  
<span data-ttu-id="071a5-109">Следующий пример иллюстрирует синхронную операцию чтения в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="071a5-109">The following example shows a synchronous read operation within a console app.</span></span> <span data-ttu-id="071a5-110">В этом примере текстовый файл открывается с помощью модуля чтения потока, содержимое копируется в строку, а строка выводится в консоли.</span><span class="sxs-lookup"><span data-stu-id="071a5-110">This example opens the text file using a stream reader, copies the contents to a string, and outputs the string to the console.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="071a5-111">В примерах предполагается, что файл с именем *TestFile.txt* уже существует в той же папке, что и приложение.</span><span class="sxs-lookup"><span data-stu-id="071a5-111">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a><span data-ttu-id="071a5-112">Пример Асинхронное чтение в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="071a5-112">Example: Asynchronous read in a WPF app</span></span>
 <span data-ttu-id="071a5-113">Следующий пример иллюстрирует асинхронную операцию чтения в приложении Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="071a5-113">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) app.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="071a5-114">В примерах предполагается, что файл с именем *TestFile.txt* уже существует в той же папке, что и приложение.</span><span class="sxs-lookup"><span data-stu-id="071a5-114">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[TextFiles](../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.cs)]
 [!code-vb[TextFiles](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="071a5-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="071a5-115">See also</span></span>

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="071a5-116">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="071a5-116">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- <span data-ttu-id="071a5-117">[Руководство. Создание списка каталогов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="071a5-117">[How to: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span></span>  
- [<span data-ttu-id="071a5-118">Краткое руководство. Чтение и запись файлов</span><span class="sxs-lookup"><span data-stu-id="071a5-118">Quickstart: Reading and writing files</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [<span data-ttu-id="071a5-119">Руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="071a5-119">How to: Convert between .NET Framework streams and Windows Runtime streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [<span data-ttu-id="071a5-120">Руководство. Считывание данных из нового файла и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="071a5-120">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="071a5-121">Руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="071a5-121">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="071a5-122">Руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="071a5-122">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="071a5-123">Руководство. Считывание символов из строки</span><span class="sxs-lookup"><span data-stu-id="071a5-123">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="071a5-124">Руководство. Запись символов в строку</span><span class="sxs-lookup"><span data-stu-id="071a5-124">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="071a5-125">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="071a5-125">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
