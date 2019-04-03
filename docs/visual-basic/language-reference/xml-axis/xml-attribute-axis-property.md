---
title: Свойство оси атрибута XML (Visual Basic)
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
ms.openlocfilehash: a7a93608d14bcbec316228b59467b23e9247e043
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828814"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>Свойство оси атрибута XML (Visual Basic)
Предоставляет доступ к значению атрибута для <xref:System.Xml.Linq.XElement> объект или на первый элемент в коллекцию <xref:System.Xml.Linq.XElement> объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Части  
 `object`  
 Обязательный. <xref:System.Xml.Linq.XElement> Объект или коллекция <xref:System.Xml.Linq.XElement> объектов.  
  
 .@  
 Обязательный. Обозначает начало свойства оси атрибута.  
  
 <  
 Необязательный параметр. Обозначает начало имени атрибута при `attribute` не является допустимым идентификатором в Visual Basic.  
  
 `attribute`  
 Обязательный. Имя атрибута, чтобы открыть окно, в формате [`prefix`:]`name`.  
  
|Отделение|Описание|  
|----------|-----------------|  
|`prefix`|Необязательный параметр. Префикс пространства имен XML для атрибута. Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.|  
|`name`|Обязательный. Имя локального атрибута. См. в разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Необязательный параметр. Обозначает конец имя атрибута при `attribute` не является допустимым идентификатором в Visual Basic.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая значение `attribute`. Если имя атрибута не существует, `Nothing` возвращается.  
  
## <a name="remarks"></a>Примечания  
 Свойства оси атрибута XML можно использовать для доступа к значению атрибута по имени из <xref:System.Xml.Linq.XElement> объекта или с первого элемента в коллекции <xref:System.Xml.Linq.XElement> объектов. Можно извлечь значение атрибута по имени или добавить новый атрибут в элемент, указав новое имя, начинающееся с идентификатора @.  
  
 При ссылке на атрибут XML с помощью идентификатора @, возвращается значение атрибута как строку и необходимо явно указать <xref:System.Xml.Linq.XAttribute.Value%2A> свойство.  
  
 Правила именования для XML-атрибутов отличаются от правилам именования идентификаторов Visual Basic. Чтобы получить доступ к XML-атрибут с именем, который не является допустимым идентификатором Visual Basic, заключите имя в угловых скобках (\< и >).  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 Имя в свойстве оси атрибута можно использовать только префиксы пространства имен XML, объявленные глобально с помощью `Imports` инструкции. В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML-элемента. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как для получения значений атрибутов XML с именем `type` из коллекции XML-элементов, которые называются `phone`.  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 Этот пример кода отображает следующий текст:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как создать атрибуты для XML-элемента как декларативно, как часть XML и динамически путем добавления атрибута к экземпляру <xref:System.Xml.Linq.XElement> объекта. `type` Атрибут создается декларативно и `owner` атрибута создается динамически.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 Этот пример кода отображает следующий текст:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере используется синтаксис угловых скобок, чтобы получить значение атрибута XML с именем `number-type`, который не является допустимым идентификатором в Visual Basic.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone type: work`  
  
## <a name="example"></a>Пример  
 В следующем примере `ns` объявляется как префикс пространства имен XML. Затем используется префикс пространства имен для создания литерала XML и доступа к первому дочернему узлу с полным именем "`ns:name`«.  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
