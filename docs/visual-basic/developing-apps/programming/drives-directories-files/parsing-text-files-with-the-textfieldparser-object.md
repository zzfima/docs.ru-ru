---
title: "Анализ текстовых файлов с помощью объекта TextFieldParser (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "файлы, синтаксический разбор"
  - "ввод-вывод [Visual Basic], синтаксический анализ файлов"
  - "TextFieldParser - объект, использование"
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Анализ текстовых файлов с помощью объекта TextFieldParser (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объект `TextFieldParser` позволяет анализировать и обрабатывать файлы очень большого размера, по своей структуре имеющие вид столбцов текста с разделителями, например файлы журнала или старые базы данных.  Анализ текстового файла с помощью объекта `TextFieldParser` похож на итерацию содержимого текстового файла, а метод анализа, связанный с извлечением полей текста, напоминает методы работы со строками, используемые для маркировки разделенных строк.  
  
## Анализ различных типов текстовых файлов  
 Текстовые файлы могут иметь поля различной ширины, разделенные тем или иными символом, например запятой или знаком табуляции.  Определите `TextFieldType` и разделитель, как в следующем примере, в котором с помощью метода `SetDelimiters` определяется текстовый файл со знаком табуляции в качестве разделителя:  
  
 [!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]  
  
 Другие текстовые файлы могут иметь поля фиксированной ширины.  В этом случае необходимо определить `TextFieldType` как `FixedWidth` и задать ширину каждого поля, как в следующем примере.  В этом примере столбцы текста определяются с помощью метода `SetFieldWidths`: первый столбец имеет ширину 5 символов, второй 10, третий 11, а четвертый столбец имеет переменную ширину.  
  
 [!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]  
  
 После определения формата можно обработать весь файл в цикле, используя для обработки каждой строки метод `ReadFields`.  
  
 Если поле не соответствует указанному формату, возникает исключение <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>.  При возникновении таких исключений в свойства `ErrorLine` и `ErrorLineNumber` записывается текст, вызвавший исключение и номер строки, на которой находится этот текст.  
  
## Анализ файлов с содержимым в нескольких форматах  
 Метод `PeekChars` объекта `TextFieldParser` может использоваться для проверки каждого поля до его чтения, позволяя определить несколько форматов для полей и реагировать соответствующим образом.  Дополнительные сведения см. в разделе [Практическое руководство. Чтение текстовых файлов различных форматов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>   
 [Разрешение вопросов, связанных с исключениями: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)