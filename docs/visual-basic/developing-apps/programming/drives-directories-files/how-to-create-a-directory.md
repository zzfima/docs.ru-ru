---
title: "Практическое руководство. Создание каталога в Visual Basic | Microsoft Docs"
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
  - "каталоги [Visual Basic], создание"
  - "папки [Visual Basic], создание"
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Практическое руководство. Создание каталога в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Для создания каталогов можно использовать метод `CreateDirectory` объекта `My.Computer.FileSystem`.  
  
 Если каталог уже существует, исключение не создается.  
  
### Чтобы создать каталог  
  
-   Используйте метод `CreateDirectory`, указав полный путь расположения создаваемого каталога.  В этом примере создается каталог `NewDirectory` в каталоге `C:\Documents and Settings\All Users\Documents`.  
  
     [!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Неверное имя каталога.  Например, в нем содержатся недопустимые знаки, или имя состоит из одних пробелов \(<xref:System.ArgumentException>\).  
  
-   Родительский каталог создаваемого каталога доступен только для чтения \(<xref:System.IO.IOException>\).  
  
-   Именем каталога является `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Имя каталога имеет слишком большую длину \(<xref:System.IO.PathTooLongException>\).  
  
-   Имя каталога состоит из двоеточия \(<xref:System.NotSupportedException>\).  
  
-   У пользователя нет разрешения на создание каталога \(<xref:System.UnauthorizedAccessException>\).  
  
-   У пользователя нет разрешений в ситуации частичного доверия \(<xref:System.Security.SecurityException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>   
 [Создание, удаление и перемещение файлов и папок](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)