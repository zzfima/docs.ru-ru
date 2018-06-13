---
title: Составление потоков
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET Framework], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 231bd98b556dafeb69091de4a6770c1462824659
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572857"
---
# <a name="composing-streams"></a><span data-ttu-id="7f932-102">Составление потоков</span><span class="sxs-lookup"><span data-stu-id="7f932-102">Composing Streams</span></span>
<span data-ttu-id="7f932-103">Резервное хранилище — это устройство хранения информации, например диск или память.</span><span class="sxs-lookup"><span data-stu-id="7f932-103">A backing store is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="7f932-104">Каждое из резервных хранилищ использует собственную реализацию потока, основанную на классе <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="7f932-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="7f932-105">Каждый тип потока считывает и записывает байты в собственное резервное хранилище.</span><span class="sxs-lookup"><span data-stu-id="7f932-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="7f932-106">Потоки, которые связаны с резервными хранилищами, называются базовыми.</span><span class="sxs-lookup"><span data-stu-id="7f932-106">Streams that connect to backing stores are called base streams.</span></span> <span data-ttu-id="7f932-107">Базовые потоки имеют конструкторы, которые используют параметры для подключения к соответствующему резервному хранилищу.</span><span class="sxs-lookup"><span data-stu-id="7f932-107">Base streams have constructors that have the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="7f932-108">Например, конструкторы класса <xref:System.IO.FileStream> задают параметр пути, который определяет порядок совместного использования этого файла в процессах.</span><span class="sxs-lookup"><span data-stu-id="7f932-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes, and so on.</span></span>  
  
 <span data-ttu-id="7f932-109">В структуре классов <xref:System.IO> реализовано упрощенное составление потоков.</span><span class="sxs-lookup"><span data-stu-id="7f932-109">The design of the <xref:System.IO> classes provides simplified stream composing.</span></span> <span data-ttu-id="7f932-110">Базовые потоки могут присоединяться к одному или нескольким транзитным потокам, которые предоставляют нужные возможности.</span><span class="sxs-lookup"><span data-stu-id="7f932-110">Base streams can be attached to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="7f932-111">В конце цепочки можно прикрепить средство чтения или записи, что позволяет удобно читать и записывать нужные типы.</span><span class="sxs-lookup"><span data-stu-id="7f932-111">A reader or writer can be attached to the end of the chain so that the preferred types can be read or written easily.</span></span>  
  
 <span data-ttu-id="7f932-112">В следующем примере кода создается поток **FileStream** на основе существующего `MyFile.txt`, предназначенный для буферизации `MyFile.txt`.</span><span class="sxs-lookup"><span data-stu-id="7f932-112">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="7f932-113">(Обратите внимание, что потоки **FileStream** буферизуются по умолчанию.) Далее создается <xref:System.IO.StreamReader> для чтения символов из **FileStream** и передается в качестве аргумента конструктору **StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="7f932-113">(Note that **FileStreams** are buffered by default.) Next, a <xref:System.IO.StreamReader> is created to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="7f932-114"><xref:System.IO.StreamReader.ReadLine%2A> выполняет чтение, пока <xref:System.IO.StreamReader.Peek%2A> обнаруживает символы.</span><span class="sxs-lookup"><span data-stu-id="7f932-114"><xref:System.IO.StreamReader.ReadLine%2A> reads until <xref:System.IO.StreamReader.Peek%2A> finds no more characters.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 <span data-ttu-id="7f932-115">В следующем примере кода создается поток **FileStream** на основе существующего `MyFile.txt`, предназначенный для буферизации `MyFile.txt`.</span><span class="sxs-lookup"><span data-stu-id="7f932-115">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="7f932-116">(Обратите внимание, что потоки **FileStream** буферизуются по умолчанию.) Далее создается **BinaryReader** для чтения байтов из **FileStream** и передается в качестве аргумента конструктору **BinaryReader**.</span><span class="sxs-lookup"><span data-stu-id="7f932-116">(Note that **FileStreams** are buffered by default.) Next, a **BinaryReader** is created to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="7f932-117"><xref:System.IO.BinaryReader.ReadByte%2A> выполняет чтение, пока <xref:System.IO.BinaryReader.PeekChar%2A> обнаруживает байты.</span><span class="sxs-lookup"><span data-stu-id="7f932-117"><xref:System.IO.BinaryReader.ReadByte%2A> reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="7f932-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7f932-118">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
