---
title: "Анализ текстовых файлов с помощью объекта TextFieldParser (Visual Basic) | Документы Майкрософт"
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
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files, parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 570a5218ce2d750eb5f3a1a1b57e1e05f7fc0cbd
ms.lasthandoff: 03/13/2017

---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a>Анализ текстовых файлов с помощью объекта TextFieldParser (Visual Basic)
Объект `TextFieldParser` позволяет анализировать и обрабатывать файлы очень большого размера, по своей структуре имеющие вид столбцов текста с разделителями, например файлы журнала или старые базы данных. Анализ текстового файла с помощью объекта `TextFieldParser` похож на итерацию содержимого текстового файла, а метод анализа, связанный с извлечением полей текста, напоминает методы работы со строками, используемые для маркировки разделенных строк.  
  
## <a name="parsing-different-types-of-text-files"></a>Анализ различных типов текстовых файлов  
 Текстовые файлы могут иметь поля различной ширины, разделенные тем или иными символом, например запятой или знаком табуляции. Определите `TextFieldType` и разделитель, как в следующем примере, в котором с помощью метода `SetDelimiters` определяется текстовый файл со знаком табуляции в качестве разделителя:  
  
 [!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]  
  
 Другие текстовые файлы могут иметь поля фиксированной ширины. В этом случае необходимо определить `TextFieldType` как `FixedWidth` и задать ширину каждого поля, как в примере ниже. В этом примере столбцы текста определяются с помощью метода `SetFieldWidths`: первый столбец имеет ширину 5 символов, второй — 10, третий — 11, а четвертый столбец имеет переменную ширину.  
  
 [!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]  
  
 После определения формата можно обработать весь файл в цикле, используя для обработки каждой строки метод `ReadFields`.  
  
 Если поле не соответствует указанному формату, возникает исключение <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>. При возникновении таких исключений в свойства `ErrorLine` и `ErrorLineNumber` записывается текст, вызвавший исключение, и номер строки, в которой находится этот текст.  
  
## <a name="parsing-files-with-multiple-formats"></a>Анализ файлов с содержимым в нескольких форматах  
 Метод `PeekChars` объекта `TextFieldParser` можно использовать для проверки каждого поля до его чтения, что позволяет определить несколько форматов для полей и отреагировать соответствующим образом. Дополнительные сведения см. в разделе [Практическое руководство. Чтение из текстовых файлов различных форматов](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).  
  
## <a name="see-also"></a>См. также  
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
