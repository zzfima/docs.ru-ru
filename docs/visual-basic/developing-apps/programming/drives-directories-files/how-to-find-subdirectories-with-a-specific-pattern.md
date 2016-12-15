---
title: "Практическое руководство. Поиск подкаталогов по шаблону в Visual Basic | Microsoft Docs"
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
  - "папки, поиск"
  - "соответствие шаблону"
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Поиск подкаталогов по шаблону в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> возвращает доступную только для чтения коллекцию строк, представляющих имена путей к подкаталогам каталога.  Для указания конкретного шаблона можно использовать параметр `wildCards`.  Если требуется включить в поиск содержимое подкаталогов, присвойте параметру `searchType` значение `SearchOption.SearchAllSubDirectories`.  
  
 Если каталоги, соответствующие заданному шаблону, не найдены возвращается пустая коллекция.  
  
### Поиск подкаталогов по заданному шаблону  
  
-   Используйте метод `GetDirectories`, указав имя и путь к каталогу для поиска.  В следующем примере возвращаются и отображаются в элементе управления `ListBox1` все каталоги в структуре каталогов, имена которых содержат слово "Logs".  
  
     [!code-vb[VbVbcnFileAccess#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-subdirectories-with-a-specific-pattern_1.vb)]  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Путь может являться недопустимым по одной из следующих причин: путь представляет собой строку нулевой длины \(пустую строку\); путь содержит только пробелы; путь содержит недопустимые знаки; или путь представляет собой путь к устройству \(начинается с \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Один или несколько указанных подстановочных знаков является `Nothing`, пустой строкой или содержит только пробелы \(<xref:System.ArgumentNullException>\).  
  
-   `directory` не существует \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   Параметр `directory` указывает на существующий файл \(<xref:System.IO.IOException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   Имя файла или папки в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\).  
  
-   Пользователь не имеет необходимых разрешений \(<xref:System.UnauthorizedAccessException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>   
 [Практическое руководство. Поиск файлов по конкретному шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)