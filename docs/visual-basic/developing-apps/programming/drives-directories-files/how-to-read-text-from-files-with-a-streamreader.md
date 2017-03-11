---
title: "Практическое руководство. Чтение текста из файлов с помощью StreamReader (Visual Basic) | Microsoft Docs"
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
  - "файлы, чтение"
  - "чтение файлов, текст"
  - "чтение текста из файлов"
  - "текст, чтение из файлов"
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Практическое руководство. Чтение текста из файлов с помощью StreamReader (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Объект `My.Computer.FileSystem` предоставляет методы для открытия <xref:System.IO.TextReader> и <xref:System.IO.TextWriter>.  Методы `OpenTextFileWriter` и `OpenTextFileReader` являются дополнительными методами и отображаются в IntelliSense, только если выбрана вкладка **Все**.  
  
### Чтобы считать строку из файла с использованием средства чтения текста  
  
-   Используйте метод `OpenTextFileReader` для открытия <xref:System.IO.TextReader>, указав файл.  В этом примере открывается файл `testfile.txt`, считывается строка из него и отображается в окне сообщения.  
  
     [!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-text-from-fi_1.vb)]  
  
## Отказоустойчивость  
 Этот файл должен быть текстовым файлом.  
  
 По имени файла не всегда можно с уверенностью судить о его содержимом.  Например, файл с именем Form1.vb может и не являться исходным файлом Visual Basic.  
  
 Следует проверять все входные данные перед использованием их в приложении.  Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.  
  
## Безопасность платформы .NET Framework  
 Для чтения из файла сборке требуется уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.FileIOPermission>.  Если код выполняется в контексте частичного доверия, исключение может возникнуть из\-за недостатка прав доступа.  Дополнительные сведения см. в разделе [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  Пользователь также должен иметь доступ к файлу.  Дополнительные сведения см. в разделе [ACL Technology Overview](http://msdn.microsoft.com/ru-ru/06fbf66d-6f02-4378-b863-b2f12e349045).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:System.Windows.Forms.OpenFileDialog>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>   
 [Компонент SaveFileDialog](../Topic/SaveFileDialog%20Component%20\(Windows%20Forms\).md)   
 [Чтение из файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)