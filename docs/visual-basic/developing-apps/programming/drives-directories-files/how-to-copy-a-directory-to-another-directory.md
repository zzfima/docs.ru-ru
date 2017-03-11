---
title: "Практическое руководство. Копирование каталога в другой каталог в Visual Basic | Microsoft Docs"
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
  - "каталоги [Visual Basic], копирование"
  - "папки [Visual Basic], копирование"
  - "ввод-вывод [Visual Basic], копирование каталогов"
  - "ввод-вывод [Visual Basic], копирование папок"
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Практическое руководство. Копирование каталога в другой каталог в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> можно использовать для копирования каталога в другой каталог.  Этот метод копирует содержимое каталога, а также сам каталог.  Если каталог назначения не существует, он будет создан.  Если каталог с тем же именем существует в местоположении назначения, а параметру `overwrite` присвоено значение `False`, то содержимое двух каталогов будут объединено.  Можно указать новое имя каталога во время выполнения операции.  
  
 При копировании файлов в каталоге могут создаваться исключения, например, если при объединении каталогов тот или иной файл уже существует в каталоге, а параметру `overwrite` присвоено значение `False`.  В случае возникновения таких исключений они объединяются в одно исключение. Свойство `Data` такого исключения содержит записи, в которых ключ представляет путь к файлу или каталогу, а значение — сообщение исключения.  
  
### Чтобы скопировать каталог в другой каталог  
  
-   Используйте метод `CopyDirectory`, указав имена исходного каталога и каталога назначения.  В следующем примере каталог `TestDirectory1` копируется в каталог `TestDirectory2`, при этом происходит перезапись существующих файлов.  
  
     [!code-vb[VbVbcnMyFileSystem#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-copy-a-directory-_1.vb)]  
  
     Данный пример кода доступен также в качестве фрагмента кода IntelliSense.  В окне выбора фрагмента кода он находится в разделе **Файловая система — Обработка дисков, папок и файлов**.  Дополнительные сведения см. в разделе [Фрагменты кода](/visual-studio/ide/code-snippets).  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Новое имя каталога содержит двоеточие \(:\) или косую черту \(\\ или \/\) \(<xref:System.ArgumentException>\).  
  
-   Путь может являться недопустимым по одной из следующих причин: путь представляет собой строку нулевой длины \(пустую строку\); путь содержит только пробелы; путь содержит недопустимые знаки; или путь представляет собой путь к устройству \(начинается с \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Параметр `destinationDirectoryName` равен `Nothing` или является пустой строкой \(<xref:System.ArgumentNullException>\).  
  
-   Исходный каталог не существует \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   Исходный каталог является корневым \(<xref:System.IO.IOException>\).  
  
-   Объединенный путь указывает на существующий файл \(<xref:System.IO.IOException>\).  
  
-   Исходный и конечный пути совпадают \(<xref:System.IO.IOException>\).  
  
-   Параметр `ShowUI` имеет значение `UIOption.AllDialogs`, а пользователь отменил операцию, или один или несколько файлов в каталоге не могут быть скопированы \(<xref:System.OperationCanceledException>\).  
  
-   Операция является циклической \(<xref:System.InvalidOperationException>\).  
  
-   Путь содержит двоеточие \(:\) \(<xref:System.NotSupportedException>\).  
  
-   Длина пути превышает максимальную длину, определенную в системе \(<xref:System.IO.PathTooLongException>\).  
  
-   Имя файла или папки в пути содержит двоеточие \(:\) или имеет недопустимый формат \(<xref:System.NotSupportedException>\).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути \(<xref:System.Security.SecurityException>\).  
  
-   Конечный файл существует, но к нему нет доступа \(<xref:System.UnauthorizedAccessException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>   
 [Практическое руководство. Поиск подкаталогов по шаблону](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [Практическое руководство. Получение коллекции содержащихся в каталоге файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)