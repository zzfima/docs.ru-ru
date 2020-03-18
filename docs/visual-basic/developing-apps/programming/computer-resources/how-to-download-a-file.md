---
title: Практическое руководство. Загрузка файла
ms.date: 07/20/2015
helpviewer_keywords:
- downloading Internet resources [Visual Basic], files
- downloading files [Visual Basic]
- remote computers [Visual Basic], downloading from
- files [Visual Basic], downloading
- files [Visual Basic], transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
ms.openlocfilehash: 4923feb46ff638de9514a4d70fc00367491a6f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345624"
---
# <a name="how-to-download-a-file-in-visual-basic"></a>Практическое руководство. Загрузка файла в Visual Basic

Метод <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> можно использовать для скачивания удаленного файла и сохранения его в определенном месте. Если для параметра `ShowUI` установлено значение `True`, отображается диалоговое окно, показывающее ход загрузки и позволяющее пользователю отменить операцию. По умолчанию существующие файлы с тем же именем не перезаписываются. Если требуется перезаписывать существующие файлы, установите для параметра `overwrite` значение `True`.

При следующих условиях возможно возникновение исключения:

- Недопустимое имя диска (<xref:System.ArgumentException>).

- Не была предоставлена необходимая аутентификация (<xref:System.UnauthorizedAccessException> или <xref:System.Security.SecurityException>).

- Сервер не отвечает в пределах указанного `connectionTimeout` (<xref:System.TimeoutException>).

- Запрос отклонен веб-сайтом (<xref:System.Net.WebException>).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

> [!IMPORTANT]
> По имени файла не всегда можно с уверенностью судить о его содержимом. Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic. Следует проверять все входные данные перед использованием их в приложении. Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.

### <a name="to-download-a-file"></a>Загрузка файла

- Используйте метод `DownloadFile`, чтобы скачать файл, указав расположение конечного файла в виде строки или URI и задав расположение для сохранения файла. В этом примере выполняется загрузка файла `WineList.txt` из `http://www.cohowinery.com/downloads` и его сохранение в `C:\Documents and Settings\All Users\Documents`:

  [!code-vb[VbResourceTasks#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#9)]

### <a name="to-download-a-file-specifying-a-time-out-interval"></a>Загрузка файла с указанием времени ожидания

- Используйте метод `DownloadFile`, чтобы скачать файл, указав расположение конечного файла в виде строки или URI, задав расположение для сохранения файла и интервал времени ожидания в миллисекундах (значение по умолчанию 1000). В этом примере выполняется загрузка файла `WineList.txt` из `http://www.cohowinery.com/downloads` и его сохранение в `C:\Documents and Settings\All Users\Documents` с указанием интервала ожидания 500 миллисекунд:

  [!code-vb[VbResourceTasks#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#10)]

### <a name="to-download-a-file-supplying-a-user-name-and-password"></a>Загрузка файла с указанием имени пользователя и пароля

- Используйте метод `DownLoadFile`, чтобы скачать файл, указав расположение конечного файла в виде строки или URI и задав расположение для сохранения файла, имени пользователя и пароля. В этом примере выполняется загрузка файла `WineList.txt` из `http://www.cohowinery.com/downloads` и его сохранение в `C:\Documents and Settings\All Users\Documents` с именем пользователя `anonymous` и пустым паролем.

  [!code-vb[VbResourceTasks#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#11)]

  > [!IMPORTANT]
  > Протокол FTP, используемый методом `DownLoadFile`, отправляет данные, включая пароли, в формате обычного текста и не должен использоваться для передачи важных сведений.

## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Devices.Network>
- <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>
- [Практическое руководство. Передача файла](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)
- [Практическое руководство. Анализ путей к файлам](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
