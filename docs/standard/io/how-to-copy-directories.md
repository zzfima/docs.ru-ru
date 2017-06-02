---
title: "Практическое руководство. Копирование каталогов | Microsoft Docs"
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
  - "копирование каталогов"
  - "каталоги [платформа .NET Framework], копирование"
  - "копирование каталогов"
  - "ввод-вывод [платформа .NET Framework], копирование каталогов"
  - "копирование подкаталогов"
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Копирование каталогов
В этом примере демонстрируется использование классов ввода\-вывода для синхронного копирования содержимого каталога в другое место. В этом примере пользователь может указать, следует ли также копировать подкаталоги. Если подкаталоги копируются, метод в этом примере рекурсивно копирует их путем вызова самого себя для каждого последующего подкаталога, пока не будет скопировано все.  
  
 Пример асинхронного копирования файлов см. в разделе[Асинхронный файловый ввод\-вывод](../../../docs/standard/io/асинхронный-файловый-ввод-вывод.md).  
  
## Пример  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## См. также  
 <xref:System.IO.FileInfo>   
 <xref:System.IO.DirectoryInfo>   
 <xref:System.IO.FileStream>   
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)   
 [Распространенные задачи ввода\-вывода](../../../docs/standard/io/commons-tasks.md)   
 [Асинхронный файловый ввод\-вывод](../../../docs/standard/io/асинхронный-файловый-ввод-вывод.md)