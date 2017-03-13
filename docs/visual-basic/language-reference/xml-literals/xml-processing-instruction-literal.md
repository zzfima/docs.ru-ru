---
title: "Литерал инструкции обработки XML (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralProcessingInstruction"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "инструкция по обработке литерала [Visual Basic]"
  - "XML-литералы [Visual Basic], инструкция по обработке"
  - "инструкция по обработке литерала XML [Visual Basic]"
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Литерал инструкции обработки XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Литеральный символ, представляющий объект <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## Синтаксис  
  
```  
<?piName [ = piData ] ?>  
```  
  
## Части  
 `<?`  
 Обязательный.  Обозначает начало XML литерала инструкции обработки.  
  
 `piName`  
 Обязательный.  Имя, указывающее целевое приложение инструкции обработки.  Не может начинаться с "xml" или "XML".  
  
 `piData`  
 Необязательный.  Строка, указывающая, как приложение, на которое указывает `piName`, должно обрабатывать XML\-документ.  
  
 `?>`  
 Обязательный.  Обозначает конец инструкции обработки.  
  
## Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## Заметки  
 XML литералы инструкции обработки указывают, как приложения должны обрабатывать XML\-документ.  Когда приложение загружает XML\-документ, оно может проверить инструкции обработки XML для определения способа обработки документа.  Приложение интерпретирует значение `piName` и `piData`.  
  
 Литерал XML\-документа использует синтаксис, схожий с инструкцией обработки XML.  Дополнительные сведения см. в разделе [XML\-литерал документа](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  Элемент `piName` не может начинаться со строки "xml" или "XML", поскольку спецификация XML 1.0 резервирует эти идентификаторы.  
  
 Можно назначить литерал инструкции обработки XML переменной или включить ее в литерал XML\-документа.  
  
> [!NOTE]
>  XML\-литерал может занимать несколько строк без необходимости в символах продолжения строки.  Это позволяет скопировать содержимое из XML\-документа и вставить его непосредственно в программу [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] компилятор преобразует литерал инструкции обработки XML для вызова конструктора <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>.  
  
## Пример  
 В следующем примере создается инструкция обработки, определяющая таблицу стилей для XML\-документа.  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## См. также  
 <xref:System.Xml.Linq.XProcessingInstruction>   
 [XML\-литерал документа](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)