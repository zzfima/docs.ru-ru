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
ms.openlocfilehash: 689cc9537cd7a5fe6a677d42e5790bbcf1b3aefa
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708152"
---
# <a name="compose-streams"></a>Создание потоков
*Резервное хранилище* — это устройство хранения информации, например диск или память. Каждое из резервных хранилищ использует собственную реализацию потока, основанную на классе <xref:System.IO.Stream>. 

Каждый тип потока считывает и записывает байты в собственное резервное хранилище. Потоки, которые связаны с резервными хранилищами, называются *базовыми*. Базовые потоки имеют конструкторы, которые используют параметры для подключения к соответствующему резервному хранилищу. Например, конструкторы класса <xref:System.IO.FileStream> задают параметр пути, который определяет порядок совместного использования этого файла в процессах.  

В структуре классов <xref:System.IO> реализовано упрощенное составление потоков. Базовые потоки могут присоединяться к одному или нескольким транзитным потокам, которые предоставляют нужные возможности. Вы можете прикрепить в конце цепочки средство чтения или записи, что позволяет удобно читать и записывать нужные типы.  

В следующем примере кода создается поток **FileStream** на основе существующего *MyFile.txt*, предназначенный для буферизации *MyFile.txt*. Обратите внимание, что потоки **FileStreams** буферизуются по умолчанию.

>[!IMPORTANT]
>В примерах предполагается, что файл с именем *MyFile.txt* уже существует в той же папке, что и приложение.  

## <a name="example-use-streamreader"></a>Пример. Использование StreamReader
В следующем примере создается <xref:System.IO.StreamReader> для чтения символов из **FileStream** и передается в качестве аргумента конструктора в **StreamReader**. <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> выполняет чтение, пока <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> обнаруживает символы.  
  
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
## <a name="example-use-binaryreader"></a>Пример. Использование BinaryReader
В следующем примере создается <xref:System.IO.BinaryReader> для чтения байтов из **FileStream** и передается в качестве аргумента конструктора в **BinaryReader**. <xref:System.IO.BinaryReader.ReadByte%2A> выполняет чтение, пока <xref:System.IO.BinaryReader.PeekChar%2A> обнаруживает байты.  
  
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>См. также

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>
- <xref:System.IO.FileStream>
- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
