---
title: "Практическое руководство. Создание файла в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "файлы, создание"
  - "текстовые файлы, создание"
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Создание файла в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом примере создается пустой текстовый файл по указанному пути с помощью метода <xref:System.IO.File.Create%2A> класса <xref:System.IO.File>.  
  
## Пример  
 [!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]  
  
## Компиляция кода  
 Для записи в файл используется переменная `file`.  
  
## Отказоустойчивость  
 Если файл уже существует, он заменяется.  
  
 При следующих условиях возможно возникновение исключения.  
  
-   Неверный формат имени пути.  Например, в нем содержатся недопустимые знаки, или имя состоит из одних пробелов \(<xref:System.ArgumentException>\).  
  
-   Путь доступен только для чтения \(<xref:System.IO.IOException>\).  
  
-   Имя пути равно `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Имя пути имеет слишком большую длину \(<xref:System.IO.PathTooLongException>\).  
  
-   Указан недопустимый путь \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   Путь состоит только из двоеточия \(<xref:System.NotSupportedException>\).  
  
## Безопасность платформы .NET Framework  
 Исключение <xref:System.Security.SecurityException> может быть создано в среде частичного доверия.  
  
 Вызов метода <xref:System.IO.File.Create%2A> требует <xref:System.Security.Permissions.FileIOPermission>.  
  
 Исключение <xref:System.UnauthorizedAccessException> создается, если пользователь не имеет разрешения на создание файла.  
  
## См. также  
 <xref:System.IO>   
 <xref:System.IO.File.Create%2A>   
 [Using Libraries from Partially Trusted Code](../Topic/Using%20Libraries%20from%20Partially%20Trusted%20Code.md)   
 [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md)