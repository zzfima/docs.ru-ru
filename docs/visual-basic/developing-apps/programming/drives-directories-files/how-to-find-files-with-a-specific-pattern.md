---
title: "Практическое руководство. Поиск файлов по конкретному шаблону в Visual Basic | Microsoft Docs"
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
  - "файлы, поиск"
  - "соответствие шаблону"
  - "шаблоны, соответствие"
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Поиск файлов по конкретному шаблону в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> возвращает доступную только для чтения коллекцию строк, представляющих имена путей к файлам.  Для указания конкретного шаблона можно использовать параметр `wildCards`.  Если требуется включить в поиск содержимое вложенных каталогов, следует присвоить параметру `searchType` значение `SearchOption.SearchAllSubDirectories`.  
  
 Пустая коллекция возвращается, если файлы, соответствующие заданному шаблону, не найдены.  
  
> [!NOTE]
>  Дополнительные сведения о возвращение списка файлов с помощью класса `DirectoryInfo` пространства имен `System.IO` см. в разделе <xref:System.IO.DirectoryInfo.GetFiles%2A>.  
  
### Поиск файлов по указанному шаблону  
  
-   Используйте метод `GetFiles`, указывая имя и путь каталога, в котором требуется выполнить поиск, и шаблон.  Следующий пример возвращает все файлы с расширением `.dll`, имеющиеся в каталоге, и добавляет их в список `ListBox1`.  
  
     [!code-vb[VbFileIOMisc#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-files-with-a-specific-pattern_1.vb)]  
  
## Безопасность платформы .NET Framework  
 При следующих условиях возможно возникновение исключения.  
  
-   Путь может являться недопустимым по одной из следующих причин: путь представляет собой строку нулевой длины \(пустую строку\); путь содержит только пробелы; путь содержит недопустимые знаки; или путь представляет собой путь к устройству \(начинается с \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   `directory` не существует \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   Параметр `directory` указывает на существующий файл \(<xref:System.IO.IOException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   Имя файла или папки в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\).  
  
-   Пользователь не имеет необходимых разрешений \(<xref:System.UnauthorizedAccessException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>   
 [Практическое руководство. Поиск подкаталогов по шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Практическое руководство. Получение коллекции содержащихся в каталоге файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)