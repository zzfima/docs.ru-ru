---
title: "Практическое руководство. Перемещение файла в Visual Basic | Microsoft Docs"
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
  - "файлы, перемещение"
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Перемещение файла в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Метод `My.Computer.FileSystem.MoveFile` может использоваться для перемещения файла в другую папку. Если целевая структура не существует, она будет создана.  
  
### Перемещение файла  
  
-   Используйте метод `MoveFile`, чтобы переместить файл, указав имя и расположение исходного и целевого файлов. В данном примере перемещается файл с именем `test.txt` из `TestDir1` в `TestDir2`. Обратите внимание, что имя целевого файла указывается даже несмотря на то, что оно совпадает с именем исходного файла.  
  
     [!code-vb[VbVbcnMyFileSystem#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_1.vb)]  
  
### Перемещение и переименование файла  
  
-   Используйте метод `MoveFile`, чтобы переместить файл, указав имя и расположение исходного файла, целевое расположение и новое имя в целевом расположении. В данном примере файл с именем `test.txt` перемещается из `TestDir1` в `TestDir2` и переименовывается в `nexttest.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#25](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_2.vb)]  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Путь является недопустимым, так как он представляет собой строку нулевой длины \(пустую строку\), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству \(начинается с символов \\\\.\\\) \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Параметр `destinationFileName` имеет значение `Nothing` или является пустой строкой \(<xref:System.ArgumentNullException>\).  
  
-   Исходный файл является недопустимым или не существует \(<xref:System.IO.FileNotFoundException>\).  
  
-   Объединенный путь указывает на существующий каталог, целевой файл существует и `overwrite` имеет значение `False`, файл в целевом каталоге с тем же именем уже используется или пользователь не имеет необходимых разрешений для доступа к файлу \(<xref:System.IO.IOException>\).  
  
-   Имя файла или каталога в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   `showUI` имеет значение `True`, `onUserCancel` имеет значение `ThrowException`, и либо пользователь отменил операцию, либо произошла неопределенная ошибка ввода\-вывода \(<xref:System.OperationCanceledException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\).  
  
-   У пользователя отсутствует необходимое разрешение \(<xref:System.UnauthorizedAccessException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A>   
 [Практическое руководство. Переименование файла](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)   
 [Практическое руководство. Создание копии файла в другом каталоге](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)   
 [Практическое руководство. Анализ путей к файлам](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)