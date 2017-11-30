---
title: "Составление потоков"
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
- streams, base streams
- I/O [.NET Framework], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75800210a52620c5b08a01c5f8fa888bf40843fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="composing-streams"></a><span data-ttu-id="2414c-102">Составление потоков</span><span class="sxs-lookup"><span data-stu-id="2414c-102">Composing Streams</span></span>
<span data-ttu-id="2414c-103">Резервное хранилище — это устройство хранения информации, например диск или память.</span><span class="sxs-lookup"><span data-stu-id="2414c-103">A backing store is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="2414c-104">Каждый из резервных хранилищ используется собственный поток как реализация <xref:System.IO.Stream> класса.</span><span class="sxs-lookup"><span data-stu-id="2414c-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="2414c-105">Каждый тип потока считывает и записывает байты в собственное резервное хранилище.</span><span class="sxs-lookup"><span data-stu-id="2414c-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="2414c-106">Потоки, которые связаны с резервными хранилищами, называются базовыми.</span><span class="sxs-lookup"><span data-stu-id="2414c-106">Streams that connect to backing stores are called base streams.</span></span> <span data-ttu-id="2414c-107">Базовые потоки имеют конструкторы, которые имеют параметры, необходимые для подключения к резервному хранилищу потока.</span><span class="sxs-lookup"><span data-stu-id="2414c-107">Base streams have constructors that have the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="2414c-108">Например <xref:System.IO.FileStream> имеет конструктор, задающий путь, который определяет порядок совместного использования файла процессами и т. д.</span><span class="sxs-lookup"><span data-stu-id="2414c-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes, and so on.</span></span>  
  
 <span data-ttu-id="2414c-109">В структуре <xref:System.IO> классы предоставляет упрощенное составление потоков.</span><span class="sxs-lookup"><span data-stu-id="2414c-109">The design of the <xref:System.IO> classes provides simplified stream composing.</span></span> <span data-ttu-id="2414c-110">Базовые потоки могут прикрепляться в один или несколько транзитных потоки, которые предоставляют функциональные возможности, которые нужно.</span><span class="sxs-lookup"><span data-stu-id="2414c-110">Base streams can be attached to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="2414c-111">Средство чтения или записи могут прикрепляться в конце цепочки, чтобы прочитать или записать легко предпочитаемых типов.</span><span class="sxs-lookup"><span data-stu-id="2414c-111">A reader or writer can be attached to the end of the chain so that the preferred types can be read or written easily.</span></span>  
  
 <span data-ttu-id="2414c-112">В следующем примере кода создается **FileStream** для существующего `MyFile.txt` в порядке буфер `MyFile.txt`.</span><span class="sxs-lookup"><span data-stu-id="2414c-112">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="2414c-113">(Обратите внимание, что **файловых групп FileStream** буферизуется по умолчанию.) Далее, <xref:System.IO.StreamReader> создается для чтения символов из **FileStream**, который передается **StreamReader** аргументом конструктора.</span><span class="sxs-lookup"><span data-stu-id="2414c-113">(Note that **FileStreams** are buffered by default.) Next, a <xref:System.IO.StreamReader> is created to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="2414c-114"><xref:System.IO.StreamReader.ReadLine%2A>выполняет чтение до <xref:System.IO.StreamReader.Peek%2A> находит больше нет символов.</span><span class="sxs-lookup"><span data-stu-id="2414c-114"><xref:System.IO.StreamReader.ReadLine%2A> reads until <xref:System.IO.StreamReader.Peek%2A> finds no more characters.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 <span data-ttu-id="2414c-115">В следующем примере кода создается **FileStream** для существующего `MyFile.txt` в порядке буфер `MyFile.txt`.</span><span class="sxs-lookup"><span data-stu-id="2414c-115">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="2414c-116">(Обратите внимание, что **файловых групп FileStream** буферизуется по умолчанию.) Далее, **BinaryReader** для чтения байтов из **FileStream**, который передается **BinaryReader** аргументом конструктора.</span><span class="sxs-lookup"><span data-stu-id="2414c-116">(Note that **FileStreams** are buffered by default.) Next, a **BinaryReader** is created to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="2414c-117"><xref:System.IO.BinaryReader.ReadByte%2A>выполняет чтение до <xref:System.IO.BinaryReader.PeekChar%2A> находит не большее число байтов.</span><span class="sxs-lookup"><span data-stu-id="2414c-117"><xref:System.IO.BinaryReader.ReadByte%2A> reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="2414c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2414c-118">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
