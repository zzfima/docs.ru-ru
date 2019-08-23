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
ms.openlocfilehash: 8a489be46295c213b7a8b355eb3c9786d49dd8f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958503"
---
# <a name="xml-document-literal-visual-basic"></a>XML-литерал документа (Visual Basic)
Литерал, представляющий <xref:System.Xml.Linq.XDocument> объект.  
  
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
|`encoding`|Необязательный параметр. Литеральный текст, объявляющий кодировку, используемую в документе.|  
|`standalone`|Необязательный параметр. Текст литерала. Значение должно быть "Yes" или "No".|  
|`piCommentList`|Необязательный параметр. Список инструкций по обработке XML и XML-комментариев. Принимает следующий формат:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Каждый `piComment` из них может быть одним из следующих:<br /><br /> -   [Литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Обязательный. Корневой элемент документа. Формат может быть одним из следующих:<br /><br /> <ul><li>[Литерал XML-элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Внедренное выражение формы `<%=`. `elementExp` `%>` Метод `elementExp` возвращает одно из следующих:<br /><br /> <ul><li>Объект <xref:System.Xml.Linq.XElement>.</li><li>Коллекция, содержащая один <xref:System.Xml.Linq.XElement> объект и любое <xref:System.Xml.Linq.XProcessingInstruction> количество объектов и <xref:System.Xml.Linq.XComment> .</li></ul></li></ul><br /> Дополнительные сведения см. [в разделе внедренные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XDocument>.  
  
## <a name="remarks"></a>Примечания  
 Литерал XML-документа определяется XML-объявлением в начале литерала. Хотя каждый литерал XML-документа должен иметь ровно один корневой XML-элемент, он может иметь любое количество инструкций по обработке XML и XML-комментариев.  
  
 Литерал XML-документа не может присутствовать в элементе XML.  
  
> [!NOTE]
> XML-литерал может охватывать несколько строк без использования символов продолжения строки. Это позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.  
  
 Компилятор Visual Basic преобразует литерал XML-документа в вызовы <xref:System.Xml.Linq.XDocument.%23ctor%2A> конструкторов и. <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-документ с XML-объявлением, инструкцией по обработке, комментарием и элементом, содержащим другой элемент.  
  
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
