---
title: Создание потоков
ms.date: 01/21/2019
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
ms.openlocfilehash: 452071e9726a95b4b3d9bb9cefe720d39bbc3e0c
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674351"
---
# <a name="compose-streams"></a><span data-ttu-id="e341f-102">Создание потоков</span><span class="sxs-lookup"><span data-stu-id="e341f-102">Compose streams</span></span>
<span data-ttu-id="e341f-103">*Резервное хранилище* — это устройство хранения информации, например диск или память.</span><span class="sxs-lookup"><span data-stu-id="e341f-103">A *backing store* is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="e341f-104">Каждое из резервных хранилищ использует собственную реализацию потока, основанную на классе <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="e341f-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> 

<span data-ttu-id="e341f-105">Каждый тип потока считывает и записывает байты в собственное резервное хранилище.</span><span class="sxs-lookup"><span data-stu-id="e341f-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="e341f-106">Потоки, которые связаны с резервными хранилищами, называются *базовыми*.</span><span class="sxs-lookup"><span data-stu-id="e341f-106">Streams that connect to backing stores are called *base streams*.</span></span> <span data-ttu-id="e341f-107">Базовые потоки имеют конструкторы, которые используют параметры для подключения к соответствующему резервному хранилищу.</span><span class="sxs-lookup"><span data-stu-id="e341f-107">Base streams have constructors with the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="e341f-108">Например, конструкторы класса <xref:System.IO.FileStream> задают параметр пути, который определяет порядок совместного использования этого файла в процессах.</span><span class="sxs-lookup"><span data-stu-id="e341f-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes.</span></span>  

<span data-ttu-id="e341f-109">В структуре классов <xref:System.IO> реализовано упрощенное составление потоков.</span><span class="sxs-lookup"><span data-stu-id="e341f-109">The design of the <xref:System.IO> classes provides simplified stream composition.</span></span> <span data-ttu-id="e341f-110">Базовые потоки могут присоединяться к одному или нескольким транзитным потокам, которые предоставляют нужные возможности.</span><span class="sxs-lookup"><span data-stu-id="e341f-110">You can attach base streams to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="e341f-111">Вы можете прикрепить в конце цепочки средство чтения или записи, что позволяет удобно читать и записывать нужные типы.</span><span class="sxs-lookup"><span data-stu-id="e341f-111">You can attach a reader or writer to the end of the chain, so the preferred types can be read or written easily.</span></span>  

<span data-ttu-id="e341f-112">В следующем примере кода создается поток **FileStream** на основе существующего *MyFile.txt*, предназначенный для буферизации *MyFile.txt*.</span><span class="sxs-lookup"><span data-stu-id="e341f-112">The following code examples create a **FileStream** around the existing *MyFile.txt* in order to buffer *MyFile.txt*.</span></span> <span data-ttu-id="e341f-113">Обратите внимание, что потоки **FileStreams** буферизуются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e341f-113">Note that **FileStreams** are buffered by default.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e341f-114">В примерах предполагается, что файл с именем *MyFile.txt* уже существует в той же папке, что и приложение.</span><span class="sxs-lookup"><span data-stu-id="e341f-114">The examples assume that a file named *MyFile.txt* already exists in the same folder as the app.</span></span>  

## <a name="example-use-streamreader"></a><span data-ttu-id="e341f-115">Пример Использование StreamReader</span><span class="sxs-lookup"><span data-stu-id="e341f-115">Example: Use StreamReader</span></span>
<span data-ttu-id="e341f-116">В следующем примере создается <xref:System.IO.StreamReader> для чтения символов из **FileStream** и передается в качестве аргумента конструктора в **StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="e341f-116">The following example creates a <xref:System.IO.StreamReader> to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="e341f-117"><xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> выполняет чтение, пока <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> обнаруживает символы.</span><span class="sxs-lookup"><span data-stu-id="e341f-117"><xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> then reads until <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> finds no more characters.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
## <a name="example-use-binaryreader"></a><span data-ttu-id="e341f-118">Пример Использование BinaryReader</span><span class="sxs-lookup"><span data-stu-id="e341f-118">Example: Use BinaryReader</span></span>
<span data-ttu-id="e341f-119">В следующем примере создается <xref:System.IO.BinaryReader> для чтения байтов из **FileStream** и передается в качестве аргумента конструктора в **BinaryReader**.</span><span class="sxs-lookup"><span data-stu-id="e341f-119">The following example creates a <xref:System.IO.BinaryReader> to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="e341f-120"><xref:System.IO.BinaryReader.ReadByte%2A> выполняет чтение, пока <xref:System.IO.BinaryReader.PeekChar%2A> обнаруживает байты.</span><span class="sxs-lookup"><span data-stu-id="e341f-120"><xref:System.IO.BinaryReader.ReadByte%2A> then reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="e341f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e341f-121">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>
- <xref:System.IO.FileStream>
- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
