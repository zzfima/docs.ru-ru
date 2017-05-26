---
title: "Практическое руководство. Создание копии файла в том же каталоге в Visual Basic | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- File.Copy
dev_langs:
- VB
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files, copying
- CopyFile method, copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c7078edf6822cc06c7d3c7933c5df7fdd2a73e6f
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

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
  
-   Путь является недопустимым, так как представляет собой строку нулевой длины (пустую строку), содержит только пробелы, содержит недопустимые символы или представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Системе не удалось получить абсолютный путь (<xref:System.ArgumentException>).  
  
-   Путь является недопустимым, поскольку это `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Исходный файл недопустим или не существует (<xref:System.IO.FileNotFoundException>).  
  
-   Объединенный путь указывает на существующий каталог (<xref:System.IO.IOException>).  
  
-   Конечный файл существует, а параметр `overwrite` имеет значение `False` (<xref:System.IO.IOException>).  
  
-   Пользователь не имеет необходимых разрешений для доступа к файлу (<xref:System.IO.IOException>).  
  
-   Файл в папке назначения с тем же именем уже используется (<xref:System.IO.IOException>).  
  
-   Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
-   Параметр `ShowUI` имеет значение `True`, параметр `onUserCancel` — значение `ThrowException`, и пользователь отменил операцию (<xref:System.OperationCanceledException>).  
  
-   Параметр `ShowUI` имеет значение `True`, параметр `onUserCancel` — значение `ThrowException`, и возникла неопределенная ошибка ввода-вывода (<xref:System.OperationCanceledException>).  
  
-   Длина пути превышает максимальную длину, определенную системой (<xref:System.IO.PathTooLongException>).  
  
-   Пользователь не имеет необходимых разрешений (<xref:System.UnauthorizedAccessException>).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>   
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 [Практическое руководство. Копирование файлов по заданному шаблону в каталог](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)   
 [Практическое руководство. Создание копии файла в другом каталоге](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)   
 [Практическое руководство. Копирование каталога в другой каталог](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)   
 [Практическое руководство. Переименование файла](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
