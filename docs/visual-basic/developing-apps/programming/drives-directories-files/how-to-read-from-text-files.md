---
title: Практическое руководство. Чтение из текстовых файлов
ms.date: 07/20/2015
helpviewer_keywords:
- extended characters [Visual Basic], reading
- reading text files [Visual Basic]
- reading data, text files
- examples [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
ms.openlocfilehash: 8af088ad269cc77bc5c83aedb86bde9af2e37a15
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334592"
---
# <a name="how-to-read-from-text-files-in-visual-basic"></a>Практическое руководство. Чтение из текстовых файлов в Visual Basic

Метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> объекта `My.Computer.FileSystem` позволяет считывать данные из текстового файла. Если содержимое файла имеет определенную кодировку, например ASCII или UTF-8, ее можно указать в аргументе.

Если вы производите чтение из файла с символами национальных алфавитов, необходимо указать кодировку файла.

> [!NOTE]
> Чтобы прочитать файл по одной строке, используйте метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> объекта `My.Computer.FileSystem`. Метод `OpenTextFileReader` возвращает объект <xref:System.IO.StreamReader>. С помощью метода <xref:System.IO.StreamReader.ReadLine%2A> объекта `StreamReader` можно прочитать файл по одной строке. Проверить, достигнут ли конец файла, можно с помощью метода <xref:System.IO.StreamReader.EndOfStream%2A> объекта `StreamReader`.

## <a name="to-read-from-a-text-file"></a>Чтение данных из текстового файла

Для считывания содержимого текстового файла в строку используйте метод `ReadAllText` объекта `My.Computer.FileSystem`, указав путь. В следующем примере содержимое файла test.txt считывается в строку и затем отображается в окне сообщения.

[!code-vb[VbFileIORead#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#2)]

### <a name="to-read-from-a-text-file-that-is-encoded"></a>Чтение данных из зашифрованного текстового файла

Для считывания содержимого текстового файла в строку используйте метод `ReadAllText` объекта `My.Computer.FileSystem`, указав путь и тип кодировки файла. В следующем примере содержимое файла test.txt в кодировке UTF32 считывается в строку и затем отображается в окне сообщения.

[!code-vb[VbFileIORead#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#3)]

## <a name="robust-programming"></a>Отказоустойчивость

При следующих условиях возможно возникновение исключения:

- Путь является недопустимым, поскольку путь представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (<xref:System.ArgumentException>).

- Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).

- Файл не существует (<xref:System.IO.FileNotFoundException>).

- Файл уже используется другим процессом или возникла ошибка ввода-вывода (<xref:System.IO.IOException>).

- Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).

- Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).

- Не хватает памяти для записи строки в буфер (<xref:System.OutOfMemoryException>).

- У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).

По имени файла не всегда можно с уверенностью судить о его содержимом. Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.

Следует проверять все входные данные перед использованием их в приложении. Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
- [Чтение из файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [Практическое руководство. Чтение из текстовых файлов с полями фиксированного размера](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [Практическое руководство. Чтение из текстовых файлов различных форматов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [Устранение неполадок. Чтение из текстовых файлов и запись в такие файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
- [Пошаговое руководство: Операции с файлами и каталогами в Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [Кодировки файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
