---
title: "Практическое руководство. Удаление файла в Visual Basic | Документы Майкрософт"
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
- Delete method
- files, deleting
- files, manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
caps.latest.revision: 24
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
ms.openlocfilehash: f6cf3192d6983b6222815c5c77a3dfd0b3845650
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-delete-a-file-in-visual-basic"></a>Практическое руководство. Удаление файла в Visual Basic
Метод `DeleteFile` объекта `My.Computer.FileSystem` позволяет удалить файл. Параметры метода позволяют указать, следует ли отправлять удаленный файл в **корзину**, следует ли запрашивать у пользователя подтверждение удаления файла и что делать при отмене пользователем операции.  
  
### <a name="to-delete-a-text-file"></a>Удаление текстового файла  
  
-   Для удаления файла используйте метод `DeleteFile`. В следующем коде показано, как удалить файл с именем `test.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a>Удаление текстового файла с запросом подтверждения удаления файла  
  
-   Для удаления файла используйте метод `DeleteFile`, присвоив параметру`showUI` значение `AllDialogs`. В следующем коде демонстрируется удаление файла `test.txt` с запросом у пользователя подтверждения удаления файла.  
  
     [!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a>Удаление текстового файла и отправка его в корзину  
  
-   Для удаления файла используйте метод `DeleteFile`, присвоив параметру `SendToRecycleBin` значение `recycle`. В следующем коде демонстрируется удаление файла `test.txt` и отправка его в **корзину**.  
  
     [!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Путь является недопустимым, так как представляет собой строку нулевой длины (пустую строку), содержит только пробелы, содержит недопустимые символы или представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Путь является недопустимым, поскольку это `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Длина пути превышает максимальную длину, определенную системой (<xref:System.IO.PathTooLongException>).  
  
-   Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
-   Файл уже используется (<xref:System.IO.IOException>).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
-   Файл не существует (<xref:System.IO.FileNotFoundException>).  
  
-   Пользователь не имеет разрешения на удаление файла, или файл доступен только для чтения (<xref:System.UnauthorizedAccessException>).  
  
-   Возникла ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений (<xref:System.Security.SecurityException>).  
  
-   Пользователь отменил операцию, и для параметра `onUserCancel` установлено значение `ThrowException` (<xref:System.OperationCanceledException>).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.UIOption>   
 <xref:Microsoft.VisualBasic.FileIO.RecycleOption>   
 [Практическое руководство. Получение коллекции содержащихся в каталоге файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
