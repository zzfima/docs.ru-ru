---
title: "Составление потоков | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "потоки, базовые потоки"
  - "ввод-вывод [платформа .NET Framework], составление потоков"
  - "класс Stream, составление потоков"
  - "базовые потоки"
  - "потоки, резервные хранилища"
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Составление потоков
Резервное хранилище — это устройство хранения информации, например диск или память.  В каждом из резервных хранилищ используется собственный поток как реализация класса <xref:System.IO.Stream>.  Каждый тип потока считывает и записывает байты в собственное резервное хранилище.  Потоки, которые связаны с резервными хранилищами, называются базовыми.  В конструкторах базовых потоков есть параметры, необходимые для присоединения потока к резервному хранилищу.  Например, <xref:System.IO.FileStream> имеет конструктор, задающий путь, который определяет порядок совместного использования файла процессами и т. д.  
  
 Структура классов <xref:System.IO> предоставляет упрощенное составление потоков.  Базовые потоки могут быть присоединены к одному или нескольким сквозным потокам, которые обеспечивают требуемую функциональность.  Модуль чтения или записи может быть присоединен к концу цепочки, что обеспечит легкое считывание или запись предпочитаемых типов.  
  
 В следующем примере кода создается поток **FileStream** для существующего файла `MyFile.txt` с целью буферизации файла `MyFile.txt`. \(Обратите внимание, что экземпляры класса **FileStreams** буферизуются по умолчанию.\) Затем создается <xref:System.IO.StreamReader> для чтения знаков из **FileStream**, который передается в **StreamReader** в качестве аргумента его конструктора.  Метод <xref:System.IO.StreamReader.ReadLine%2A> считывает до тех пор, пока <xref:System.IO.StreamReader.Peek%2A> не перестает находить знаки.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 В следующем примере кода создается поток **FileStream** для существующего файла `MyFile.txt` с целью буферизации файла `MyFile.txt`. \(Обратите внимание, что экземпляры класса **FileStreams** буферизуются по умолчанию.\) Затем создается **BinaryReader** для чтения байтов из **FileStream**, который передается в **StreamReader** в качестве аргумента его конструктора.  Метод <xref:System.IO.BinaryReader.ReadByte%2A> считывает до тех пор, пока <xref:System.IO.BinaryReader.PeekChar%2A> не перестает находить байты.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## См. также  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>   
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=fullName>   
 <xref:System.IO.FileStream>   
 <xref:System.IO.BinaryReader>   
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=fullName>   
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=fullName>