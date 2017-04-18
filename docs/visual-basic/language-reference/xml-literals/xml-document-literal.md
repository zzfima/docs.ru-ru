---
title: "XML-литерал документа (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralDocument
dev_langs:
- VB
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5d64faddad66eba4029969654388ba7df17e5854
ms.lasthandoff: 03/13/2017

---
# <a name="xml-document-literal-visual-basic"></a>XML-литерал документа (Visual Basic)
Литерал представляет <xref:System.Xml.Linq.XDocument>объекта.</xref:System.Xml.Linq.XDocument>  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`encoding`|Необязательный. Использует текст литерала для определения, какая кодировка документа.|  
|`standalone`|Необязательный. Обычный текст. Должно быть «Да» или «нет».|  
|`piCommentList`|Необязательный. Список инструкций по обработке XML и XML-комментариев. Имеет следующий формат:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Каждая `piComment`может принимать одно из следующих действий:<br /><br /> -   [Литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Обязательный. Корневой элемент документа. Формат является одним из следующих:<br /><br /> <ul><li>[XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Встроенные выражения в форме `<%=` `elementExp` `%>`. `elementExp` Возвращает одно из следующих действий:<br /><br /> <ul><li><xref:System.Xml.Linq.XElement>Объект.</xref:System.Xml.Linq.XElement></li><li>Коллекция, содержащая один <xref:System.Xml.Linq.XElement>объекта и любым количеством <xref:System.Xml.Linq.XProcessingInstruction>и <xref:System.Xml.Linq.XComment>объекты.</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></li></ul></li></ul><br /> Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Возвращаемое значение  
 <xref:System.Xml.Linq.XDocument>Объект.</xref:System.Xml.Linq.XDocument>  
  
## <a name="remarks"></a>Примечания  
 Литерал XML-документа определяется XML-декларация в начале литерала. Несмотря на то, что каждый литерал XML-документа должен иметь ровно один корневой элемент XML, он может иметь любое количество инструкций по обработке XML и XML-комментариев.  
  
 Литерал XML-документа не может присутствовать в XML-элемента.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует литерала XML-документа в вызовы <xref:System.Xml.Linq.XDocument.%23ctor%2A>и <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>конструкторы.</xref:System.Xml.Linq.XDeclaration.%23ctor%2A> </xref:System.Xml.Linq.XDocument.%23ctor%2A>  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-документ, который содержит XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.  
  
 [!code-vb[VbXMLSamples&#30;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement>   
 <xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction>   
 <xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment>   
 <xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument>   
 [Литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)   
 [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)   
 [Литеральное представление XML элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
