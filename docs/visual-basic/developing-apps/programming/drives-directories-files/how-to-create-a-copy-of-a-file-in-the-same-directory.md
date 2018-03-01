---
title: "Практическое руководство. Создание копии файла в том же каталоге в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- File.Copy
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af592e16bb1f7f0bbb188b2ea39394ec1074d302
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-copy-of-a-file-in-the-same-directory-in-visual-basic"></a>Практическое руководство. Создание копии файла в том же каталоге в Visual Basic
Для копирования файлов используйте метод `My.Computer.FileSystem.CopyFile`. Эти параметры обеспечивают возможность перезаписи существующих файлов, переименования файлов и отображения хода выполнения операции, а также отмены операции пользователем.  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder"></a>Создание копии файла в том же каталоге  
  
-   Используйте метод `CopyFile`, указав конечный файл и расположение. В следующем примере создается копия `test.txt` с именем `test2.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#51](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-the-same-directory_1.vb)]  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder-overwriting-existing-files"></a>Создание копии файла в том же каталоге, перезапись существующих файлов  
  
-   Используйте метод `CopyFile`, указав конечный файл и расположение и задав для параметра `overwrite` значение `True`. В следующем примере создается копия `test.txt` с именем `test2.txt` и перезаписываются существующие файлы с этим именем.  
  
     [!code-vb[VbVbcnMyFileSystem#52](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-the-same-directory_2.vb)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Исключение может возникнуть в следующих случаях:  
  
-   Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Системе не удалось получить абсолютный путь (<xref:System.ArgumentException>).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Исходный файл является недопустимым или не существует (<xref:System.IO.FileNotFoundException>).  
  
-   Объединенный путь указывает на существующий каталог (<xref:System.IO.IOException>).  
  
-   Конечный файл существует, а параметр `overwrite` имеет значение `False` (<xref:System.IO.IOException>).  
  
-   Пользователь не имеет необходимых разрешений для доступа к файлу (<xref:System.IO.IOException>).  
  
-   Файл в папке назначения с тем же именем уже используется (<xref:System.IO.IOException>).  
  
-   Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
-   Параметр `ShowUI` имеет значение `True`, параметр `onUserCancel` имеет значение `ThrowException`, и пользователь отменил операцию (<xref:System.OperationCanceledException>).  
  
-   `ShowUI` имеет значение `True`, параметр `onUserCancel` имеет значение `ThrowException`, и возникла неопределенная ошибка ввода-вывода (<xref:System.OperationCanceledException>).  
  
-   Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).  
  
-   У пользователя отсутствует необходимое разрешение (<xref:System.UnauthorizedAccessException>).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>  
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>  
 [Практическое руководство. Копирование файлов по заданному шаблону в каталог](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)  
 [Практическое руководство. Создание копии файла в другом каталоге](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)  
 [Практическое руководство. Копирование каталога в другой каталог](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)  
 [Практическое руководство. Переименование файла](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
