---
title: XML-литерал документа (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: 86780d53c2261b6440f515fc09512fba313667dc
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56964959"
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
|`encoding`|Необязательный параметр. Использует литеральный текст, определения кодировки документа.|  
|`standalone`|Необязательный параметр. Литеральный текст. Должен быть «yes» или «no».|  
|`piCommentList`|Необязательный параметр. Список инструкции по обработке XML и XML-комментариев. Имеет следующий формат:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Каждый `piComment` может принимать одно из следующих:<br /><br /> -   [Литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Обязательный. Корневой элемент документа. Одно из следующих имеет следующий формат:<br /><br /> <ul><li>[XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Внедренные выражения вида `<%=` `elementExp` `%>`. `elementExp` Возвращает одно из следующих:<br /><br /> <ul><li>Объект <xref:System.Xml.Linq.XElement>.</li><li>Коллекция, содержащая один <xref:System.Xml.Linq.XElement> объекта и любое количество <xref:System.Xml.Linq.XProcessingInstruction> и <xref:System.Xml.Linq.XComment> объектов.</li></ul></li></ul><br /> Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XDocument>.  
  
## <a name="remarks"></a>Примечания  
 Литерала XML-документа определяется с помощью объявления XML в начале литерала. Несмотря на то, что каждый XML-литерала документа должен иметь ровно один корневой элемент XML, он может иметь любое количество инструкций по обработке XML и XML-комментариев.  
  
 Литерал XML-документа не может присутствовать в XML-элемента.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.  
  
 Компилятор Visual Basic преобразует XML-литерала документа в вызовы <xref:System.Xml.Linq.XDocument.%23ctor%2A> и <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> конструкторы.  
  
## <a name="example"></a>Пример  
 В следующем примере создается документ XML с XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [XML-литерал инструкции обработки](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
