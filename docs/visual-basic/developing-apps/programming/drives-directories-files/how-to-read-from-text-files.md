---
title: "Практическое руководство. Чтение из текстовых файлов в Visual Basic | Документы Майкрософт"
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
- extended characters, reading
- reading text files
- reading data, text files
- examples [Visual Basic], reading text files
- text files, reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
caps.latest.revision: 27
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 362745101d1a8f7dd61b5e3aabe1c27190c46c07
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-read-from-text-files-in-visual-basic"></a>Практическое руководство. Чтение из текстовых файлов в Visual Basic
Метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> объекта `My.Computer.FileSystem` позволяет считывать данные из текстового файла. Если содержимое файла имеет определенную кодировку, например ASCII или UTF-8, ее можно указать в аргументе.  
  
 Если вы производите чтение из файла с символами национальных алфавитов, необходимо указать кодировку файла.  
  
> [!NOTE]
>  Чтобы прочитать файл по одной строке, используйте метод <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> объекта `My.Computer.FileSystem`. Метод `OpenTextFileReader` возвращает объект <xref:System.IO.StreamReader>. С помощью метода <xref:System.IO.StreamReader.ReadLine%2A> объекта `StreamReader` можно прочитать файл по одной строке. Проверить, достигнут ли конец файла, можно с помощью метода <xref:System.IO.StreamReader.EndOfStream%2A> объекта `StreamReader`.  
  
### <a name="to-read-from-a-text-file"></a>Чтение данных из текстового файла  
  
-   Для считывания содержимого текстового файла в строку используйте метод `ReadAllText` объекта `My.Computer.FileSystem`, указав путь. В следующем примере содержимое файла test.txt считывается в строку и затем отображается в окне сообщения.  
  
     [!code-vb[VbFileIORead#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files_1.vb)]  
  
### <a name="to-read-from-a-text-file-that-is-encoded"></a>Чтение данных из зашифрованного текстового файла  
  
-   Для считывания содержимого текстового файла в строку используйте метод `ReadAllText` объекта `My.Computer.FileSystem`, указав путь и тип кодировки файла. В следующем примере содержимое файла test.txt в кодировке UTF32 считывается в строку и затем отображается в окне сообщения.  
  
     [!code-vb[VbFileIORead#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files_2.vb)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Путь является недопустимым, так как представляет собой строку нулевой длины (пустую строку), содержит только пробелы, содержит недопустимые символы или представляет собой путь к устройству (<xref:System.ArgumentException>).  
  
-   Путь является недопустимым, поскольку это `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Файл не существует (<xref:System.IO.FileNotFoundException>).  
  
-   Файл уже используется другим процессом, или возникла ошибка ввода-вывода (<xref:System.IO.IOException>).  
  
-   Длина пути превышает максимальную длину, определенную системой (<xref:System.IO.PathTooLongException>).  
  
-   Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
-   Не хватает памяти для записи строки в буфер (<xref:System.OutOfMemoryException>).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
 По имени файла не всегда можно с уверенностью судить о его содержимом. Например, файл Form1.vb может не быть исходным файлом [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Следует проверять все входные данные перед использованием их в приложении. Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>   
 [Чтение из файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [Практическое руководство. Чтение из текстовых файлов с полями фиксированного размера](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [Практическое руководство. Чтение из текстовых файлов различных форматов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Пошаговое руководство. Операции с файлами и каталогами в Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Кодировки файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
