---
title: "Практическое руководство. Запись текста в файлы с помощью StreamWriter в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "файлы, запись в"
  - "текст, запись в файлы"
  - "запись в файлы, StreamWriter"
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Запись текста в файлы с помощью StreamWriter в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом примере при помощи метода `My.Computer.FileSystem.OpenTextFileWriter` открывается объект <xref:System.IO.StreamWriter>, который используется для записи строки в текстовый файл с помощью метода <xref:System.IO.TextWriter.WriteLine%2A> класса <xref:System.IO.StreamWriter>.  
  
## Пример  
 [!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Файл существует и является файлом только для чтения \(<xref:System.IO.IOException>\).  
  
-   Диск переполнен \(<xref:System.IO.IOException>\).  
  
-   Путь имеет слишком большую длину \(<xref:System.IO.PathTooLongException>\).  
  
## Безопасность платформы .NET Framework  
 Если такого файла не существует, этот пример создает новый файл.  Если приложению требуется создать файл, оно должно иметь доступ к каталогу для создания файлов \(`Create`\).  Если файл уже существует, то приложению достаточно иметь лишь доступ для записи файлов \(`Write`\), т. е. меньшие привилегии.  Безопаснее создавать файл во время развертывания, если это возможно, а также предоставлять доступ `Read` к отдельному файлу вместо доступа `Create` к каталогу.  
  
## См. также  
 <xref:System.IO.StreamWriter>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>   
 [Практическое руководство. Чтение из текстовых файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)   
 [Запись в файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)