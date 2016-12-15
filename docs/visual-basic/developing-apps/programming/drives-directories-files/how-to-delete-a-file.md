---
title: "Практическое руководство. Удаление файла в Visual Basic | Microsoft Docs"
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
  - "Delete - метод"
  - "File - объект"
  - "файлы, удаление"
  - "файлы, обработка"
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Удаление файла в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Метод `DeleteFile` объекта `My.Computer.FileSystem` позволяет удалить файл.  Параметры метода позволяют указать, следует ли отправлять удаленный файл в **корзину**, следует ли запрашивать у пользователя подтверждение удаления файла и что делать при отмене пользователем операции.  
  
### Удаление текстового файла  
  
-   Для удаления файла используйте метод `DeleteFile`.  В следующем коде показано, как удалить файл `test.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]  
  
### Удаление текстового файла с запросом подтверждения удаления файла  
  
-   Для удаления файла используйте метод `DeleteFile`, присваивая параметру `showUI` значение `AllDialogs`.  В следующем коде демонстрируется удаление файла `test.txt` с запросом у пользователя подтверждения удаления файла.  
  
     [!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]  
  
### Удаление текстового файла и отправка его в корзину  
  
-   Для удаления файла используйте метод `DeleteFile`, присваивая параметру `recycle` значение `SendToRecycleBin`.  В следующем коде демонстрируется удаление файла `test.txt` и отправка его в **корзину**.  
  
     [!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Путь может являться недопустимым по одной из следующих причин: путь представляет собой строку нулевой длины \(пустую строку\); путь содержит только пробелы; путь содержит недопустимые знаки; или путь представляет собой путь к устройству \(начинается с \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   Имя файла или папки в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   Файл уже используется \(<xref:System.IO.IOException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\).  
  
-   Файл не существует \(<xref:System.IO.FileNotFoundException>\).  
  
-   Пользователь не имеет разрешения на удаление файла, или файл доступен только для чтения \(<xref:System.UnauthorizedAccessException>\).  
  
-   Возникла ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений \(<xref:System.Security.SecurityException>\).  
  
-   Пользователь отменил операцию, и для параметра `onUserCancel` установлено значение `ThrowException` \(<xref:System.OperationCanceledException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.UIOption>   
 <xref:Microsoft.VisualBasic.FileIO.RecycleOption>   
 [Практическое руководство. Получение коллекции содержащихся в каталоге файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)