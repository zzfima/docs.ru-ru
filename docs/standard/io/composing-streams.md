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
# <a name="composing-streams"></a>Составление потоков
Резервное хранилище — это устройство хранения информации, например диск или память. Каждый из резервных хранилищ используется собственный поток как реализация <xref:System.IO.Stream> класса. Каждый тип потока считывает и записывает байты в собственное резервное хранилище. Потоки, которые связаны с резервными хранилищами, называются базовыми. Базовые потоки имеют конструкторы, которые имеют параметры, необходимые для подключения к резервному хранилищу потока. Например <xref:System.IO.FileStream> имеет конструктор, задающий путь, который определяет порядок совместного использования файла процессами и т. д.  
  
 В структуре <xref:System.IO> классы предоставляет упрощенное составление потоков. Базовые потоки могут прикрепляться в один или несколько транзитных потоки, которые предоставляют функциональные возможности, которые нужно. Средство чтения или записи могут прикрепляться в конце цепочки, чтобы прочитать или записать легко предпочитаемых типов.  
  
 В следующем примере кода создается **FileStream** для существующего `MyFile.txt` в порядке буфер `MyFile.txt`. (Обратите внимание, что **файловых групп FileStream** буферизуется по умолчанию.) Далее, <xref:System.IO.StreamReader> создается для чтения символов из **FileStream**, который передается **StreamReader** аргументом конструктора. <xref:System.IO.StreamReader.ReadLine%2A>выполняет чтение до <xref:System.IO.StreamReader.Peek%2A> находит больше нет символов.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 В следующем примере кода создается **FileStream** для существующего `MyFile.txt` в порядке буфер `MyFile.txt`. (Обратите внимание, что **файловых групп FileStream** буферизуется по умолчанию.) Далее, **BinaryReader** для чтения байтов из **FileStream**, который передается **BinaryReader** аргументом конструктора. <xref:System.IO.BinaryReader.ReadByte%2A>выполняет чтение до <xref:System.IO.BinaryReader.PeekChar%2A> находит не большее число байтов.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
