---
title: "Практическое руководство. Запись текста в файлы в Visual Basic | Microsoft Docs"
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
  - "примеры [Visual Basic], текстовые файлы"
  - "файлы, запись в"
  - "текст, запись в файлы"
  - "запись в файлы"
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Практическое руководство. Запись текста в файлы в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> можно использовать для записи текста в файлы.  Если заданный файл не существует, он будет создан.  
  
## Процедура  
  
#### Запись текста в файл  
  
-   Используйте метод `WriteAllText` для записи текста в файл, указывая файл и текст, который требуется записать.  В этом примере строка `"This is new text."` записывается в файл `test.txt`, при этом текст добавляется к тексту, имеющемуся в файле.  
  
     [!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-text-to-files_1.vb)]  
  
#### Запись набора строк в файл  
  
-   Выполните цикл по коллекции строк.  Используйте метод `WriteAllText` для записи текста в файл, указав конечный файл, строку, которую требуется добавить, и присвоив параметру `append` значение `True`.  
  
     В этом примере имена файлов в каталоге `Documents and Settings` записываются в файл `FileList.txt`, при этом между каждой записью вставляется символ перевода строки для удобства чтения.  
  
     [!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-text-to-files_2.vb)]  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Путь может являться недопустимым по одной из следующих причин: путь представляет собой строку нулевой длины \(пустую строку\); путь содержит только пробелы; путь содержит недопустимые знаки; или путь представляет собой путь к устройству \(начинается с \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Параметр `File` содержит несуществующий путь \(<xref:System.IO.FileNotFoundException> или <xref:System.IO.DirectoryNotFoundException>\).  
  
-   Файл уже используется другим процессом или происходит ошибка ввода\-вывода \(<xref:System.IO.IOException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   Имя файла или каталога в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\).  
  
-   Диск заполнен, и вызов метода `WriteAllText` завершился неудачно \(<xref:System.IO.IOException>\).  
  
 Если код выполняется в контексте частичного доверия, исключение может возникнуть из\-за недостатка прав доступа.  Дополнительные сведения см. в разделе [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 [Практическое руководство. Чтение из текстовых файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)