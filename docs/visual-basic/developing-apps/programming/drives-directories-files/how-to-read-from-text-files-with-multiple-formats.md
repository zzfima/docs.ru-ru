---
title: "Практическое руководство. Чтение текстовых файлов различных форматов в Visual Basic | Microsoft Docs"
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
  - "ввод-вывод [Visual Basic], чтение текстовых файлов"
  - "My.Computer.FileSystem.WriteAllText - метод, синтаксический анализ структурированных текстовых файлов"
  - "PeekChars - метод, определение формата текста"
  - "чтение текстовых файлов, несколько форматов"
  - "текстовые файлы, чтение"
  - "TextFieldParser - объект, чтение из файла"
  - "TextFieldType - перечисление"
  - "WriteAllText - метод, синтаксический анализ структурированных текстовых файлов"
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Практическое руководство. Чтение текстовых файлов различных форматов в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Объект <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> позволяет легко и эффективно анализировать структурированные текстовые файлы, например файлы журналов.  Обработать файл, имеющий содержимое в нескольких форматах, можно с помощью метода `PeekChars`, который позволяет определять формат каждой анализируемой строки на протяжении всего файла.  
  
### Анализ текстового файла с содержимым в нескольких форматах  
  
1.  Добавьте текстовый файл с именем testfile.txt в проект.  Добавьте в текстовый файл следующее содержимое.  
  
    ```  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2.  Определите ожидаемый формат и формат, используемый при сообщении об ошибке.  Последним элементом в каждом массиве является \-1, поэтому предполагается, что ширина последнего поля может изменяться.  Это происходит, когда последний элемент массива меньше либо равен нулю.  
  
     [!code-vb[VbFileIORead#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-text-fi_0_1.vb)]  
  
3.  Создайте новый объект <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>, определив ширину и формат.  
  
     [!code-vb[VbFileIORead#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-text-fi_0_2.vb)]  
  
4.  Переберите в цикле строки, проверяя формат перед чтением.  
  
     [!code-vb[VbFileIORead#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-text-fi_0_3.vb)]  
  
5.  Выведите сообщения об ошибках на консоль.  
  
     [!code-vb[VbFileIORead#7](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-text-fi_0_4.vb)]  
  
## Пример  
 Далее приведен полный пример, считывающий из файла `testfile.txt`..  
  
 [!code-vb[VbFileIORead#8](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-text-fi_0_5.vb)]  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Строка не может быть проанализирована с использованием указанного формата \(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  Сообщение исключения задает строку, вызвавшую исключение, а свойство <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> присвоено тексту, который содержится в строке.  
  
-   Заданный файл не существует \(<xref:System.IO.FileNotFoundException>\).  
  
-   Ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений для доступа к файлу.  \(<xref:System.Security.SecurityException>\).  
  
-   Путь слишком длинный \(<xref:System.IO.PathTooLongException>\).  
  
-   Пользователь не имеет необходимых разрешений для доступа к файлу \(<xref:System.UnauthorizedAccessException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 [Практическое руководство. Чтение из текстовых файлов с разделителями\-запятыми](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [Практическое руководство. Чтение из текстовых файлов с фиксированной шириной полей](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [Анализ текстовых файлов с помощью объекта TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)