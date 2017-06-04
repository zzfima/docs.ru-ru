---
title: "Практическое руководство. Открытие файла журнала и добавление в него данных | Microsoft Docs"
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
  - "файлы журнала, открытие"
  - "потоки, открытие и добавление в файл журнала"
  - "файлы журнала, добавление в"
  - "ввод-вывод [платформа .NET Framework], файлы журнала"
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Открытие файла журнала и добавление в него данных
Классы <xref:System.IO.StreamWriter> и <xref:System.IO.StreamReader> предназначены для записи и чтения знаков из потоков.  В следующем примере кода открывается файл `log.txt` в режиме ввода данных \(если такого файла не существует, то он будет создан\) и добавляется информация в конец файла.  Затем содержимое файла передается для отображения в стандартный поток вывода.  В качестве альтернативы данные здесь могут храниться как одна строка или как массив строк, а для обеспечения той же функциональности может быть использован метод <xref:System.IO.File.WriteAllText%2A> <xref:System.IO.File.WriteAllLines%2A>.  
  
> [!NOTE]
>  Для создания файлов журналов и их ведения пользователи Visual Basic могут использовать методы и свойства, предоставляемые классом <xref:Microsoft.VisualBasic.Logging.Log> или <xref:Microsoft.VisualBasic.FileIO.FileSystem>.  
  
## Пример  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## См. также  
 <xref:System.IO.StreamWriter>   
 <xref:System.IO.StreamReader>   
 <xref:System.IO.File.AppendText%2A?displayProperty=fullName>   
 <xref:System.IO.File.OpenText%2A?displayProperty=fullName>   
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>   
 [Практическое руководство. Перечисление каталогов и файлов](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [Практическое руководство. Считывание из нового файла данных и запись в этот файл](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Практическое руководство. Считывание текста из файла](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Практическое руководство. Считывание символов из строки](../../../docs/standard/io/how-to-read-characters-from-a-string.md)   
 [Практическое руководство. Запись символов в строку](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)