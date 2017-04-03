---
title: "Практическое руководство. Загрузка файла в Visual Basic | Документы Майкрософт"
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
- downloading Internet resources, files
- downloading files
- remote computers, downloading from
- files, downloading
- files, transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
caps.latest.revision: 22
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
ms.openlocfilehash: bd37b52d12876dad6ec4b2a1bb34f4987f933c08
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-download-a-file-in-visual-basic"></a>Практическое руководство. Загрузка файла в Visual Basic
Метод <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> можно использовать для загрузки удаленного файла и его сохранения в определенное расположение. Если для параметра `ShowUI` установлено значение `True`, отображается диалоговое окно, показывающее ход загрузки и позволяющее пользователю отменить операцию. По умолчанию существующие файлы с тем же именем не перезаписываются. Если требуется перезаписывать существующие файлы, установите для параметра `overwrite` значение `True`.  
  
 При следующих условиях возможно возникновение исключения:  
  
-   Недопустимое имя диска (<xref:System.ArgumentException>).  
  
-   Не предоставлена необходимая проверка подлинности (<xref:System.UnauthorizedAccessException> или <xref:System.Security.SecurityException>).  
  
-   Сервер не отвечает в пределах указанного `connectionTimeout` (<xref:System.TimeoutException>).  
  
-   Запрос отклонен веб-сайтом (<xref:System.Net.WebException>).  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
> [!IMPORTANT]
>  По имени файла не всегда можно с уверенностью судить о его содержимом. Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic. Следует проверять все входные данные перед использованием их в приложении. Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.  
  
### <a name="to-download-a-file"></a>Загрузка файла  
  
-   Используйте метод `DownloadFile`, чтобы скачать файл, указав расположение конечного файла в виде строки или URI и задав расположение для сохранения файла. В этом примере выполняется загрузка файла `WineList.txt` из `http://www.cohowinery.com/downloads` и его сохранение в `C:\Documents and Settings\All Users\Documents`:  
  
     [!code-vb[VbResourceTasks#9](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_1.vb)]  
  
### <a name="to-download-a-file-specifying-a-time-out-interval"></a>Загрузка файла с указанием времени ожидания  
  
-   Используйте метод `DownloadFile`, чтобы скачать файл, указав расположение конечного файла в виде строки или URI, задав расположение для сохранения файла и интервал времени ожидания в миллисекундах (значение по умолчанию 1000). В этом примере выполняется загрузка файла `WineList.txt` из `http://www.cohowinery.com/downloads` и его сохранение в `C:\Documents and Settings\All Users\Documents` с указанием интервала ожидания 500 миллисекунд:  
  
     [!code-vb[VbResourceTasks#10](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_2.vb)]  
  
### <a name="to-download-a-file-supplying-a-user-name-and-password"></a>Загрузка файла с указанием имени пользователя и пароля  
  
-   Используйте метод `DownLoadFile`, чтобы скачать файл, указав расположение конечного файла в виде строки или URI и задав расположение для сохранения файла, имени пользователя и пароля. В этом примере выполняется загрузка файла `WineList.txt` из `http://www.cohowinery.com/downloads` и его сохранение в `C:\Documents and Settings\All Users\Documents` с именем пользователя `anonymous` и пустым паролем.  
  
     [!code-vb[VbResourceTasks#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_3.vb)]  
  
    > [!IMPORTANT]
    >  Протокол FTP, используемый методом `DownLoadFile`, отправляет данные, включая пароли, в формате обычного текста и не должен использоваться для передачи важных сведений.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Devices.Network>   
 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>   
 [Практическое руководство. Передача файла](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)   
 [Практическое руководство. Анализ путей к файлам](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)

