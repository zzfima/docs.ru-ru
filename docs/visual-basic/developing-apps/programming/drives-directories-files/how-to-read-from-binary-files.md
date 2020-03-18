---
title: Практическое руководство. Чтение из двоичного файла
ms.date: 07/20/2015
helpviewer_keywords:
- binary files [Visual Basic], reading from
- I/O [Visual Basic], reading from binary files
- ReadAllBytes method [Visual Basic], reading from binary files
- My.Computer.FileSystem object, reading from binary files
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
ms.openlocfilehash: c33bc72a5c79901e3715ed6a587ffdb8e3565e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74335291"
---
# <a name="how-to-read-from-binary-files-in-visual-basic"></a>Практическое руководство. Чтение из двоичного файла в Visual Basic

Объект `My.Computer.FileSystem` предоставляет метод `ReadAllBytes` для чтения данных из двоичных файлов.  
  
### <a name="to-read-from-a-binary-file"></a>Чтение данных из двоичного файла  
  
- Используйте метод `ReadAllBytes`, который возвращает содержимое файла в виде массива байтов. В этом примере производится чтение данных из файла `C:/Documents and Settings/selfportrait.jpg`.  
  
     [!code-vb[VbVbcnMyFileSystem#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#78)]  
  
- При работе с большими двоичными файлами можно использовать метод <xref:System.IO.FileStream.Read%2A> объекта <xref:System.IO.FileStream>, чтобы за раз считывать из файла только заданный объем данных. Затем можно ограничить объем файла, загружаемый в память во время каждой операции чтения. В следующем примере кода показано копирование файла, причем вызывающий объект задает, какая часть файла помещается в память при выполнении каждой операции чтения.  
  
     [!code-vb[VbVbcnMyFileSystem#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#91)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 Исключение может возникнуть в следующих случаях:  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [Чтение из файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Практическое руководство. Чтение из текстовых файлов различных форматов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [Запись данных в буфер обмена и чтение их оттуда](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)
