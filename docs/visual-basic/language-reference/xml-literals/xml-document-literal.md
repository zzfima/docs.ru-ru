---
title: "XML-литерал документа (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralDocument"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "литералы документов [Visual Basic]"
  - "литералы документов XML [Visual Basic]"
  - "документы XML [Visual Basic], создание"
  - "XML-литералы [Visual Basic], документ"
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML-литерал документа (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Литерал, представляющий объект <xref:System.Xml.Linq.XDocument>.  
  
## Синтаксис  
  
```  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`encoding`|Необязательный.  Текст литерала для определения кодировки, используемой в документе.|  
|`standalone`|Необязательный.  Текст литерала.  Необходимо значение "да" или "нет".|  
|`piCommentList`|Необязательный.  Список XML\-инструкций по обработке и XML\-комментариев.  Принимает следующий формат:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Каждый параметр `piComment` `` может быть таким:<br /><br /> -   [Литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [XML\-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Обязательный.  Корневой элемент документа.  Имеет один из следующих форматов:<br /><br /> <ul><li>[Литеральное представление XML\-элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Встроенные выражения формы `<%=` `elementExp` `%>`.  `elementExp` возвращает следующее:<br /><br /> <ul><li>Объект <xref:System.Xml.Linq.XElement>.</li><li>Коллекция, содержащая один объект <xref:System.Xml.Linq.XElement> и любое число объектов <xref:System.Xml.Linq.XProcessingInstruction> и <xref:System.Xml.Linq.XComment>.</li></ul></li></ul><br /> Дополнительные сведения см. в разделе [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XDocument>.  
  
## Заметки  
 Литерал XML\-документа определяется XML\-объявлением в начале литерала.  Каждый литерал XML\-документа должен иметь ровно один корневой элемент XML и любое количество инструкций по обработке XML и XML\-комментариев.  
  
 Литерал XML\-документа не может появляться в элементе XML.  
  
> [!NOTE]
>  XML\-литерал может занимать несколько строк без использования символа продолжения строки.  Это позволяет скопировать содержимое из XML\-документа и вставить его непосредственно в программу [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] преобразует литерал XML\-документа в вызовы конструкторов <xref:System.Xml.Linq.XDocument.%23ctor%2A> и <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>.  
  
## Пример  
 В следующем примере создается XML\-документ, который содержит XML объявление, инструкции по обработке, комментарий и элемент, содержащий другие элементы.  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## См. также  
 <xref:System.Xml.Linq.XElement>   
 <xref:System.Xml.Linq.XProcessingInstruction>   
 <xref:System.Xml.Linq.XComment>   
 <xref:System.Xml.Linq.XDocument>   
 [Литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)   
 [XML\-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)   
 [Литеральное представление XML\-элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)