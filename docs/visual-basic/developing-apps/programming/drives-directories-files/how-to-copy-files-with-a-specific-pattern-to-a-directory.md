---
title: "Практическое руководство. Копирование файлов в каталог с использованием шаблона в Visual Basic | Microsoft Docs"
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
  - "метод My.Computer.FileSystem.CopyFile, копирование файлов [Visual Basic]"
  - "файлы, копирование"
  - "метод CopyFile, копирование файлов в Visual Basic"
  - "ввод-вывод [Visual Basic], копирование файлов"
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Копирование файлов в каталог с использованием шаблона в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> возвращает доступную только для чтения коллекцию строк, представляющих имена путей для файлов. Для указания определенного шаблона можно использовать параметр `wildCards`.  
  
 Если соответствующие файлы не найдены, возвращается пустая коллекция.  
  
 Для копирования файлов в каталог можно использовать метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>.  
  
### Копирование файлов с определенным шаблоном в каталог  
  
1.  Используйте метод `GetFiles` для возврата списка файлов. В этом примере возвращены все RTF\-файлы в указанном каталоге.  
  
     [!code-vb[VbFileIOMisc#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_1.vb)]  
  
2.  Используйте метод `CopyFile` для копирования файлов. В этом примере файлы копируются в каталог с именем `testdirectory`.  
  
     [!code-vb[VbVbcnMyFileSystem#88](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_2.vb)]  
  
3.  Закройте оператор `For` с помощью оператора `Next`.  
  
     [!code-vb[VbVbcnMyFileSystem#89](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_3.vb)]  
  
## Пример  
 В следующем примере, который представляет вышеописанные фрагменты в завершенной форме, RTF\-файлы копируются из указанного каталога в каталог с именем `testdirectory`.  
  
 [!code-vb[VbFileIOMisc#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_4.vb)]  
  
## Безопасность платформы .NET Framework  
 При следующих условиях возможно возникновение исключения:  
  
-   Путь является недопустимым, так как он представляет собой строку нулевой длины \(пустую строку\), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству \(начинается с символов \\\\.\\\) \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Каталог не существует \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   Каталог указывает на существующий файл \(<xref:System.IO.IOException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   Имя файла или каталога в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\). У пользователя отсутствуют необходимые разрешения \(<xref:System.UnauthorizedAccessException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>   
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>   
 [Практическое руководство. Поиск подкаталогов по шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Практическое руководство. Получение коллекции содержащихся в каталоге файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)