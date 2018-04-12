---
title: XML-литерал документа (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 008b5857418a572046797bf061a05f265669d427
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xml-document-literal-visual-basic"></a>XML-литерал документа (Visual Basic)
Объект литерал, представляющий <xref:System.Xml.Linq.XDocument> объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`encoding`|Необязательно. Использует литеральный текст определения кодировки документа.|  
|`standalone`|Необязательно. Литеральный текст. Должен быть «yes» или «no».|  
|`piCommentList`|Необязательно. Список инструкций по обработке XML и XML-комментариев. Имеет следующий формат:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Каждый `piComment` может принимать одно из следующих действий:<br /><br /> -   [Литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Обязательный. Корневой элемент документа. Имеет одно из следующих:<br /><br /> <ul><li>[Элемент XML-литерала](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Встроенные выражения формы `<%=` `elementExp` `%>`. `elementExp` Возвращает одно из следующих действий:<br /><br /> <ul><li>Объект <xref:System.Xml.Linq.XElement>.</li><li>Коллекция, содержащая один <xref:System.Xml.Linq.XElement> объектов и любое количество <xref:System.Xml.Linq.XProcessingInstruction> и <xref:System.Xml.Linq.XComment> объектов.</li></ul></li></ul><br /> Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XDocument>.  
  
## <a name="remarks"></a>Примечания  
 Литерал XML-документа определяется по XML-декларация в начале литерала. Несмотря на то, что каждый XML-литерала документа должен иметь ровно один корневой элемент XML, он может иметь любое количество инструкций по обработке XML и XML-комментариев.  
  
 Литерал XML-документа не может присутствовать в XML-элемента.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] программы.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Компилятор преобразует XML-литерала документа в вызовы <xref:System.Xml.Linq.XDocument.%23ctor%2A> и <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> конструкторы.  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-документ с XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 <xref:System.Xml.Linq.XComment>  
 <xref:System.Xml.Linq.XDocument>  
 [XML-литерал инструкции обработки](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)  
 [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
