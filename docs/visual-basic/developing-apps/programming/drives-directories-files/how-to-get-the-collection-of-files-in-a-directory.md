---
title: "Практическое руководство. Получение коллекции содержащихся в каталоге файлов в Visual Basic | Microsoft Docs"
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
  - "файлы, доступ"
  - "папки, работа с"
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Практическое руководство. Получение коллекции содержащихся в каталоге файлов в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Перегрузка метода <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> вернет доступную только для чтения коллекцию строк, представляющих собой имена файлов в каталоге:  
  
-   Перегрузка метода <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> позволяет найти простой файл в указанном каталоге без поиска подкаталогов.  
  
-   Перегрузка метода [GetFiles\(String, SearchOption, String\<xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%2CMicrosoft.VisualBasic.FileIO.SearchOption%2CSystem.String%5B%5D%29> позволяет указать дополнительные параметры поиска.  Для указания шаблона поиска можно использовать параметр `wildCards`.  Чтобы включить подкаталоги в поиск, присвойте параметру `searchType` значение <xref:Microsoft.VisualBasic.FileIO.SearchOption?displayProperty=fullName>.  
  
 Если файлы, соответствующие указанному шаблону, не найдены, возвращается пустая коллекция.  
  
### Составление списка файлов в каталоге  
  
-   Используйте перегрузки одного из методов <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName>, указывая имя и путь к каталогу для поиска в параметре `directory`.  В следующем примере возвращаются и добавляются в список  `ListBox1` все файлы, находящиеся в каталоге.  
  
     [!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-get-the-collection-of-files-in-a-directory_1.vb)]  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Путь является недопустимым, поскольку путь представляет собой строку нулевой длины \(пустую строку\), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству \(начинается с символов \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   `directory` не существует \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   `directory` указывает на существующий файл \(<xref:System.IO.IOException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   Имя файла или каталога в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\).  
  
-   У пользователя отсутствуют необходимые разрешения \(<xref:System.UnauthorizedAccessException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>   
 [Практическое руководство. Поиск файлов по конкретному шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)   
 [Практическое руководство. Поиск подкаталогов по шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)