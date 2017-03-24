---
title: "Практическое руководство. Создание копии файла в том же каталоге в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "File.Copy"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "CopyFile - метод, копирование файлов в Visual Basic"
  - "файлы, копирование"
  - "ввод-вывод [Visual Basic], копирование файлов"
  - "My.Computer.FileSystem.CopyFile - метод, копирование файлов [Visual Basic]"
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Практическое руководство. Создание копии файла в том же каталоге в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Для копирования файлов используйте метод `My.Computer.FileSystem.CopyFile`.  Его параметры обеспечивают возможность перезаписи существующих файлов, переименования файлов и отображения хода выполнения операции, а также отмены операции пользователем.  
  
### Создание копии файла в том же каталоге  
  
-   Используйте метод `CopyFile`, задав конечный файл и расположение.  В следующем примере создается копия файла `test.txt` с именем `test2.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#51](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-the-same-directory_1.vb)]  
  
### Создание копии файла в том же каталоге с перезаписью существующих файлов  
  
-   Используйте метод `CopyFile`, задав конечный файл и расположение и установив для параметра `overwrite` значение `True`.  В следующем примере создается копия файла `test.txt` с именем `test2.txt` и перезаписываются существующие файлы с таким именем.  
  
     [!code-vb[VbVbcnMyFileSystem#52](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-the-same-directory_2.vb)]  
  
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
 [Практическое руководство. Создание копии файла в другом каталоге](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)   
 [Практическое руководство. Копирование каталога в другой каталог](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)   
 [Практическое руководство. Переименование файла](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)