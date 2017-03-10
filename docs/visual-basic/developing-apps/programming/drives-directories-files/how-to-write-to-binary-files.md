---
title: "Практическое руководство. Запись текста в двоичные файлы в Visual Basic | Microsoft Docs"
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
  - "двоичные файлы, написание в Visual Basic"
  - "файлы, двоичный доступ"
  - "WriteAllBytes - метод"
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Практическое руководство. Запись текста в двоичные файлы в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> записывает данные в двоичный файл.  Если параметр `append` имеет значение `True`, то данные будут добавляться в файл; в противном случае данные в файле переписываются.  
  
 Если указанный путь без имени файла является недопустимым, возникает исключение <xref:System.IO.DirectoryNotFoundException>.  Если путь является допустимым, но файл не существует, файл будет создан.  
  
### Запись в двоичный файл  
  
-   Используйте метод `WriteAllBytes`, указывая путь к файлу и имя файла и байты, которые требуется записать.  Этот пример добавляет массив данных `CustomerData` в файл `CollectedData.dat`.  
  
     [!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-to-binary-f_1.vb)]  
  
## Отказоустойчивость  
 Исключение может возникнуть при следующих условиях.  
  
-   Путь является недопустимым по одной из следующих причин: это строка нулевой длины; она содержит только пробелы; она содержит недопустимые знаки.  \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Параметр `File` содержит несуществующий путь \(<xref:System.IO.FileNotFoundException> или <xref:System.IO.DirectoryNotFoundException>\).  
  
-   Файл уже используется другим процессом или происходит ошибка ввода\-вывода \(<xref:System.IO.IOException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   Имя файла или каталога в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>   
 [Практическое руководство. Запись текста в файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)