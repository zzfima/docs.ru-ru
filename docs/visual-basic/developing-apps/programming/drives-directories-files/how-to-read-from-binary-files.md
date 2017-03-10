---
title: "Практическое руководство. Чтение из двоичного файла в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "двоичные файлы, чтение из"
  - "ввод-вывод [Visual Basic], чтение из двоичных файлов"
  - "My.Computer.FileSystem - объект, чтение из двоичных файлов"
  - "ReadAllBytes - метод, чтение из двоичных файлов"
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Практическое руководство. Чтение из двоичного файла в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Объект `My.Computer.FileSystem` предоставляет метод `ReadAllBytes` для чтения данных из двоичных файлов.  
  
### Чтение данных из двоичного файла.  
  
-   Используйте метод `ReadAllBytes`, который возвращает содержимое файла в виде массива байтов.  В этом примере производится чтение данных из файла `C:/Documents and Settings/selfportrait.jpg`.  
  
     [!code-vb[VbVbcnMyFileSystem#78](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-binary-_1.vb)]  
  
-   При работе с большими двоичными файлами можно использовать метод <xref:System.IO.FileStream.Read%2A> объекта <xref:System.IO.FileStream>, чтобы за раз считывать из файла только заданный объем данных.  Затем можно ограничить объем файла, загружаемый в память во время каждой операции чтения.  В следующем примере кода показано копирование файла, причем вызывающий объект задает, какая часть файла помещается в память при выполнении каждой операции чтения.  
  
     [!code-vb[VbVbcnMyFileSystem#91](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-binary-_2.vb)]  
  
## Отказоустойчивость  
 Исключение может возникнуть в следующих случаях.  
  
-   Путь является недопустимым, поскольку путь представляет собой строку нулевой длины \(пустую строку\), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Файл не существует \(<xref:System.IO.FileNotFoundException>\).  
  
-   Файл уже используется другим процессом или происходит ошибка ввода\-вывода \(<xref:System.IO.IOException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   Имя файла или каталога в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   Не хватает памяти для записи строки в буфер \(<xref:System.OutOfMemoryException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\).  
  
 По имени файла не всегда можно с уверенностью судить о его содержимом.  Например, файл с именем Form1.vb может и не являться исходным файлом Visual Basic.  
  
 Следует проверять все входные данные перед использованием их в приложении.  Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>   
 [Чтение из файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Практическое руководство. Чтение текстовых файлов различных форматов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Запись данных в буфер обмена и чтение их оттуда](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)