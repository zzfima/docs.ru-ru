---
title: "Практическое руководство. Считывание символов из строки"
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
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9116ec63bfc1d12daf7627186a52bd29d5918485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="0e9f6-102">Практическое руководство. Считывание символов из строки</span><span class="sxs-lookup"><span data-stu-id="0e9f6-102">How to: Read Characters from a String</span></span>
<span data-ttu-id="0e9f6-103">В следующем примере кода демонстрируется синхронное и асинхронное чтение знаков из строки.</span><span class="sxs-lookup"><span data-stu-id="0e9f6-103">The following code examples show how to read characters synchronously and asynchronously from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e9f6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0e9f6-104">Example</span></span>  
 <span data-ttu-id="0e9f6-105">Этот пример считывает 13 символов синхронно из строки, сохраняет их в массиве и отображает эти символы.</span><span class="sxs-lookup"><span data-stu-id="0e9f6-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays those characters.</span></span> <span data-ttu-id="0e9f6-106">Затем он считывает остальные символы в строке, сохраняет их в массив, начиная с шестой элемент и отображает содержимое массива.</span><span class="sxs-lookup"><span data-stu-id="0e9f6-106">It then reads the remaining characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="0e9f6-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0e9f6-107">Example</span></span>  
 <span data-ttu-id="0e9f6-108">Следующий пример считывает все символы асинхронно с <xref:System.Windows.Controls.TextBox> управления и сохраняет их в массиве.</span><span class="sxs-lookup"><span data-stu-id="0e9f6-108">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="0e9f6-109">Затем он асинхронно записывает каждый символ буквы или символы-разделители в отдельной строке следуют разрыв строки <xref:System.Windows.Controls.TextBlock> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0e9f6-109">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0e9f6-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0e9f6-110">See Also</span></span>  
 <xref:System.IO.StringReader>  
 <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="0e9f6-111">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="0e9f6-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="0e9f6-112">NIB: Практическое: Создание списка каталогов</span><span class="sxs-lookup"><span data-stu-id="0e9f6-112">NIB: How to: Create a Directory Listing</span></span>](http://msdn.microsoft.com/en-us/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [<span data-ttu-id="0e9f6-113">Практическое руководство. Считывание из нового файла данных и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="0e9f6-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="0e9f6-114">Практическое руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="0e9f6-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="0e9f6-115">Практическое руководство. Считывание текста из файла</span><span class="sxs-lookup"><span data-stu-id="0e9f6-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="0e9f6-116">Практическое руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="0e9f6-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="0e9f6-117">Практическое руководство. Запись символов в строку</span><span class="sxs-lookup"><span data-stu-id="0e9f6-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="0e9f6-118">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="0e9f6-118">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
