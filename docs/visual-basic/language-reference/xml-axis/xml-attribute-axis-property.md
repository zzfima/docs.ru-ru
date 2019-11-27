---
title: XML Attribute Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 109c4b45a5e3ed4e3e4db49687df5cb127a5e0c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352673"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>Свойство оси атрибута XML (Visual Basic)
Предоставляет доступ к значению атрибута для <xref:System.Xml.Linq.XElement> объекта или к первому элементу в коллекции объектов <xref:System.Xml.Linq.XElement>.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Части  
 `object`  
 Обязательно. Объект <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XElement>.  
  
 .@  
 Обязательно. Обозначает начало свойства оси атрибута.  
  
 <  
 Необязательный элемент. Обозначает начало имени атрибута, если `attribute` не является допустимым идентификатором в Visual Basic.  
  
 `attribute`  
 Обязательно. Имя атрибута, к которому осуществляется доступ, в форме [`prefix`:]`name`.  
  
|Отделение|Описание|  
|----------|-----------------|  
|`prefix`|Необязательный элемент. Префикс пространства имен XML для атрибута. Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.|  
|`name`|Обязательно. Имя локального атрибута. См. [Имена объявленных XML-элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Необязательный элемент. Обозначает конец имени атрибута, если `attribute` не является допустимым идентификатором в Visual Basic.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая значение `attribute`. Если имя атрибута не существует, возвращается `Nothing`.  
  
## <a name="remarks"></a>Примечания  
 Свойство оси атрибутов XML можно использовать для доступа к значению атрибута по имени из <xref:System.Xml.Linq.XElement> объекта или из первого элемента в коллекции объектов <xref:System.Xml.Linq.XElement>. Можно получить значение атрибута по имени или добавить новый атрибут к элементу, указав новое имя перед идентификатором @.  
  
 При ссылке на XML-атрибут, используя идентификатор @, значение атрибута возвращается в виде строки и не требуется явно указывать свойство <xref:System.Xml.Linq.XAttribute.Value%2A>.  
  
 Правила именования для XML-атрибутов отличаются от правил именования для Visual Basic идентификаторов. Чтобы получить доступ к XML-атрибуту, имя которого не является допустимым Visual Basic идентификатором, заключите имя в угловые скобки (\< и >).  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 Имя в свойстве оси атрибута может использовать только префиксы пространства имен XML, объявленные глобально с помощью инструкции `Imports`. В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML-элемента. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как получить значения XML-атрибутов с именем `type` из коллекции XML-элементов с именами `phone`.  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 Этот пример кода отображает следующий текст:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как создать атрибуты для XML-элемента декларативно, как часть XML, и динамически, добавив атрибут к экземпляру объекта <xref:System.Xml.Linq.XElement>. Атрибут `type` создается декларативно, а атрибут `owner` создается динамически.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 Этот пример кода отображает следующий текст:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере используется синтаксис угловой скобки для получения значения XML-атрибута с именем `number-type`, который не является допустимым идентификатором в Visual Basic.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone type: work`  
  
## <a name="example"></a>Пример  
 В следующем примере `ns` объявляется как префикс пространства имен XML. Затем он использует префикс пространства имен для создания XML-литерала и доступа к первому дочернему узлу с полным именем "`ns:name`".  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
