---
title: "Практическое руководство. Создание копии файла в другом каталоге в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "CopyFile - метод, копирование файлов в Visual Basic"
  - "файлы, копирование"
  - "ввод-вывод [Visual Basic], копирование файлов"
  - "My.Computer.FileSystem.CopyFile - метод, копирование файлов [Visual Basic]"
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Практическое руководство. Создание копии файла в другом каталоге в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Метод `My.Computer.FileSystem.CopyFile` позволяет копировать файлы.  Его параметры обеспечивают возможность перезаписи существующих файлов, переименования файлов и отображения хода выполнения операции, а также отмены операции пользователем.  
  
### Копирование текстового файла в другую папку  
  
-   Используйте для копирования файла метод `CopyFile`, указав файл\-источник и целевой каталог.  Параметр`overwrite` позволяет указать, следует ли перезаписывать существующие файлы.  В следующем примере кода демонстрируется использование метода `CopyFile`.  
  
     [!code-vb[VbFileIOMisc#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-a-different-directory_1.vb)]  
  
## Отказоустойчивость  
 Исключение может возникнуть в следующих случаях.  
  
-   Путь может являться недопустимым по одной из следующих причин: путь представляет собой строку нулевой длины \(пустую строку\); путь содержит только пробелы; путь содержит недопустимые знаки; или путь представляет собой путь к устройству \(начинается с \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Системе не удается извлечь абсолютный путь \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Исходный файл не является допустимым или не существует \(<xref:System.IO.FileNotFoundException>\).  
  
-   Комбинированный путь указывает на существующий каталог \(<xref:System.IO.IOException>\).  
  
-   Файл уже существует, а параметр `overwrite` имеет значение `False` \(<xref:System.IO.IOException>\).  
  
-   Пользователь не имеет необходимых разрешений для доступа к файлу \(<xref:System.IO.IOException>\).  
  
-   Файл в папке назначения с тем же именем уже используется \(<xref:System.IO.IOException>\).  
  
-   Имя файла или папки в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   Параметр `ShowUI` имеет значение `True`, параметр `onUserCancel` имеет значение `ThrowException`, а пользователь отменил операцию \(<xref:System.OperationCanceledException>\).  
  
-   Параметр `ShowUI` имеет значение `True`, параметр `onUserCancel` имеет значение `ThrowException`, и возникла неопределенная ошибка ввода\-вывода \(<xref:System.OperationCanceledException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   Пользователь не имеет необходимого разрешения \(<xref:System.UnauthorizedAccessException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>   
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 [Практическое руководство. Копирование файлов по заданному шаблону в каталог](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)   
 [Практическое руководство. Создание копии файла в том же каталоге](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)   
 [Практическое руководство. Копирование каталога в другой каталог](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)   
 [Практическое руководство. Переименование файла](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)