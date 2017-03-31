---
title: "Практическое руководство. Переименование файла в Visual Basic | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- I/O [Visual Basic], renaming files
- files, renaming
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a0a31353ce3ee0c48907f9550f6961260f92b64a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-rename-a-file-in-visual-basic"></a>Практическое руководство. Переименование файла в Visual Basic
Метод `RenameFile` объекта `My.Computer.FileSystem` можно использовать, чтобы переименовать файл, указав текущее расположение, имя файла и новое имя файла. Этот метод нельзя использовать для перемещения файла. Для перемещения и переименования файла используется метод `MoveFile`.  
  
### <a name="to-rename-a-file"></a>Переименование файла  
  
-   Используйте метод `My.Computer.FileSystem.RenameFile`, чтобы переименовать файл. В этом примере переименовывается файл с именем `Test.txt` в `SecondTest.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-rename-a-file_1.vb)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагментов кода фрагмент находится в разделе **файловая система: обработка дисков, папок и файлов**. Дополнительные сведения см. в статье [Фрагменты кода](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Путь является недопустимым, так как представляет собой строку нулевой длины (пустую строку), содержит только пробелы, содержит недопустимые символы или представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).  
  
-   `newName` содержит сведения о пути (<xref:System.ArgumentException>).  
  
-   Путь является недопустимым, поскольку это `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `newName` — `Nothing` или пустая строка (<xref:System.ArgumentNullException>).  
  
-   Исходный файл недопустим или не существует (<xref:System.IO.FileNotFoundException>).  
  
-   Имеется существующий файл или каталог с именем, указанным в `newName` (<xref:System.IO.IOException>).  
  
-   Длина пути превышает максимальную длину, определенную системой (<xref:System.IO.PathTooLongException>).  
  
-   Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
-   Пользователь не имеет необходимых разрешений (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>   
 [Практическое руководство. Перемещение файла](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md)   
 [Создание, удаление и перемещение файлов и каталогов](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)   
 [Практическое руководство. Создание копии файла в том же каталоге](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)   
 [Практическое руководство. Создание копии файла в другом каталоге](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)
