---
title: Практическое руководство. Удаление файла
ms.date: 07/20/2015
helpviewer_keywords:
- Delete method [Visual Basic]
- files [Visual Basic], deleting
- files [Visual Basic], manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
ms.openlocfilehash: 57182f1a1d92b7fe954fd26b32c5e4b1107823ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348782"
---
# <a name="how-to-delete-a-file-in-visual-basic"></a>Практическое руководство. Удаление файла в Visual Basic

Метод `DeleteFile` объекта `My.Computer.FileSystem` позволяет удалить файл. Параметры метода позволяют указать, следует ли отправлять удаленный файл в **корзину**, следует ли запрашивать у пользователя подтверждение удаления файла и что делать при отмене пользователем операции.  
  
### <a name="to-delete-a-text-file"></a>Удаление текстового файла  
  
- Для удаления файла используйте метод `DeleteFile`. В следующем коде показано, как удалить файл с именем `test.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#22)]  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a>Удаление текстового файла с запросом подтверждения удаления файла  
  
- Для удаления файла используйте метод `DeleteFile`, присвоив параметру`showUI` значение `AllDialogs`. В следующем коде демонстрируется удаление файла `test.txt` с запросом у пользователя подтверждения удаления файла.  
  
     [!code-vb[VbFileIOMisc#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#9)]  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a>Удаление текстового файла и отправка его в корзину  
  
- Для удаления файла используйте метод `DeleteFile`, присвоив параметру `SendToRecycleBin` значение `recycle`. В следующем коде демонстрируется удаление файла `test.txt` и отправка его в **корзину**.  
  
     [!code-vb[VbFileIOMisc#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#10)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 При следующих условиях возможно возникновение исключения:  
  
- Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).  
  
- Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).  
  
- Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).  
  
- Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
- Файл уже используется (<xref:System.IO.IOException>).  
  
- У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
- Файл не существует (<xref:System.IO.FileNotFoundException>).  
  
- Пользователь не имеет разрешения на удаление файла, или файл доступен только для чтения (<xref:System.UnauthorizedAccessException>).  
  
- Существует ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений для доступа к файлу (<xref:System.Security.SecurityException>).  
  
- Пользователь отменил действие и `onUserCancel` задано `ThrowException` (<xref:System.OperationCanceledException>).  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.UIOption>
- <xref:Microsoft.VisualBasic.FileIO.RecycleOption>
- [Практическое руководство. Получение коллекции содержащихся в каталоге файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
