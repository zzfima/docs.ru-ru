---
title: Практическое руководство. Перемещение файла
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], moving
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
ms.openlocfilehash: 29c64a7a81028d47bf489212e6d8faec5e8dda75
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74335358"
---
# <a name="how-to-move-a-file-in-visual-basic"></a>Практическое руководство. Перемещение файла в Visual Basic

Метод `My.Computer.FileSystem.MoveFile` может использоваться для перемещения файла в другую папку. Если целевая структура не существует, она будет создана.  
  
### <a name="to-move-a-file"></a>Перемещение файла  
  
- Используйте метод `MoveFile` , чтобы переместить файл, указав имя и расположение исходного и целевого файлов. В данном примере перемещается файл с именем `test.txt` из `TestDir1` в `TestDir2`. Обратите внимание, что имя целевого файла указывается даже несмотря на то, что оно совпадает с именем исходного файла.  
  
     [!code-vb[VbVbcnMyFileSystem#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#24)]  
  
### <a name="to-move-a-file-and-rename-it"></a>Перемещение и переименование файла  
  
- Используйте метод `MoveFile` , чтобы переместить файл, указав имя и расположение исходного файла, целевое расположение и новое имя в целевом расположении. В данном примере файл с именем `test.txt` перемещается из `TestDir1` в `TestDir2` и переименовывается в `nexttest.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#25)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 При следующих условиях возможно возникновение исключения:  
  
- Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).  
  
- Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).  
  
- Параметр`destinationFileName` имеет значение `Nothing` или является пустой строкой (<xref:System.ArgumentNullException>).  
  
- Исходный файл является недопустимым или не существует (<xref:System.IO.FileNotFoundException>).  
  
- Объединенный путь указывает на существующий каталог, целевой файл существует и `overwrite` имеет значение `False`, файл в целевом каталоге с тем же именем уже используется или пользователь не имеет необходимых разрешений для доступа к файлу (<xref:System.IO.IOException>).  
  
- Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
- `showUI` имеет значение `True`, `onUserCancel` имеет значение `ThrowException`, и либо пользователь отменил операцию, либо произошла неопределенная ошибка ввода-вывода (<xref:System.OperationCanceledException>).  
  
- Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).  
  
- У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
- У пользователя отсутствует необходимое разрешение (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A>
- [Практическое руководство. Переименование файла](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
- [Практическое руководство. Создание копии файла в другом каталоге](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)
- [Практическое руководство. Анализ путей к файлам](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
