---
title: "Практическое руководство. Запись символов в строку | Microsoft Docs"
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
  - "потоки данных, запись знаков в строку"
  - "запись знаков в строки"
  - "потоки , запись знаков в строки"
  - "ввод-вывод [платформа .NET Framework], запись знаков в строки"
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Запись символов в строку
Следующие примеры кода синхронно и асинхронно записывают символы из массива символов в строку.  
  
## Пример  
 Следующий пример записывает синхронно 5 символов из массива в строку.  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## Пример  
 В следующем примере асинхронно считываются все символы из элемента управления <xref:System.Windows.Controls.TextBox> и сохраняются в массиве.  Затем каждая буква или символ пробела асинхронно записываются в отдельную строку элемента управления <xref:System.Windows.Controls.TextBlock>, в конец которой добавляется символ разрыва строки.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## См. также  
 <xref:System.IO.StringWriter>   
 <xref:System.IO.StringWriter.Write%2A?displayProperty=fullName>   
 <xref:System.Text.StringBuilder>   
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)   
 [Асинхронный файловый ввод\-вывод](../../../docs/standard/io/асинхронный-файловый-ввод-вывод.md)   
 [Практическое руководство. Перечисление каталогов и файлов](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [Практическое руководство. Считывание из нового файла данных и запись в этот файл](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Практическое руководство. Открытие файла журнала и добавление в него данных](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Практическое руководство. Считывание текста из файла](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Практическое руководство. Считывание символов из строки](../../../docs/standard/io/how-to-read-characters-from-a-string.md)