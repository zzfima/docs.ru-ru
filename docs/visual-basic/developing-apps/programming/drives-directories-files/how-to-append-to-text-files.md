---
title: "Практическое руководство. Дозапись в текстовый файл в Visual Basic | Microsoft Docs"
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
  - "ввод-вывод [Visual Basic], добавление к файлам"
  - "ввод-вывод [Visual Basic], My.Computer.FileSystem.WriteAllText - метод"
  - "ввод-вывод [Visual Basic], WriteAllText - метод"
ms.assetid: bbbd7fb5-f169-41a9-b53f-520ea9613913
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Практическое руководство. Дозапись в текстовый файл в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Для добавления данных к текстовому файлу можно использовать метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>, задав для параметра `append` значение `True`.  
  
### Добавление данных в текстовый файл  
  
-   Используйте метод `WriteAllText`, указав конечный файл и добавляемую строку и установив для параметра `append` значение `True`.  
  
     В это примере в файл с именем `Testfile.txt` записывается строка `"This is a test string."`.  
  
     [!code-vb[VbFileIOWrite#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-append-to-text-files_1.vb)]  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Путь может являться недопустимым по одной из следующих причин: путь представляет собой строку нулевой длины \(пустую строку\); путь содержит только пробелы; путь содержит недопустимые знаки; или путь представляет собой путь к устройству \(начинается с \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Параметр `File` содержит несуществующий путь \(<xref:System.IO.FileNotFoundException> или <xref:System.IO.DirectoryNotFoundException>\).  
  
-   Файл уже используется другим процессом или происходит ошибка ввода\-вывода \(<xref:System.IO.IOException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   Имя файла или каталога в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 [Запись в файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)