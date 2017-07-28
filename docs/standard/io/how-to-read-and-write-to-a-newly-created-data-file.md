---
title: "Практическое руководство. Считывание из нового файла данных и запись в этот файл | Microsoft Docs"
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
  - "BinaryReader - класс, примеры"
  - "BinaryWriter - класс, примеры"
  - "ввод-вывод [платформа .NET Framework], чтение данных"
  - "ввод-вывод [платформа .NET Framework], запись данных"
  - "потоки, чтение и запись данных"
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Считывание из нового файла данных и запись в этот файл
Классы <xref:System.IO.BinaryWriter> и <xref:System.IO.BinaryReader?displayProperty=fullName> используются для записи и чтения данных вместо строк символов.  В следующем примере показано, как записывать данные и считывать данные из нового пустого файлового потока `Test.data`.  После создания файла данных в текущем каталоге создаются соответствующие классы <xref:System.IO.BinaryWriter> и <xref:System.IO.BinaryReader>. Класс <xref:System.IO.BinaryWriter> используется для записи целых чисел от 0 до 10 в файл `Test.data`, при этом указатель устанавливается в конец файла.  После установки файлового указателя в исходную позицию объекта <xref:System.IO.BinaryReader> считывает заданное содержимое.  
  
## Пример  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## Отказоустойчивость  
 Если файл `Test.data` уже существует в текущем каталоге, создается исключение <xref:System.IO.IOException>.  Используйте параметр <xref:System.IO.FileMode?displayProperty=fullName> файлового режима при инициализации файлового потока, чтобы создавать новый файл без вызова исключения.  
  
## См. также  
 <xref:System.IO.BinaryReader>   
 <xref:System.IO.BinaryWriter>   
 <xref:System.IO.FileStream>   
 <xref:System.IO.FileStream.Seek%2A?displayProperty=fullName>   
 <xref:System.IO.SeekOrigin>   
 [Практическое руководство. Перечисление каталогов и файлов](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [Практическое руководство. Открытие файла журнала и добавление в него данных](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Практическое руководство. Считывание текста из файла](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Практическое руководство. Считывание символов из строки](../../../docs/standard/io/how-to-read-characters-from-a-string.md)   
 [Практическое руководство. Запись символов в строку](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)