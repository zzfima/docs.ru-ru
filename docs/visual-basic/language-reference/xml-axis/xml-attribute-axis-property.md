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
Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Части  
 `object`  
 Обязательный. An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.  
  
 .@  
 Обязательный. Denotes the start of an attribute axis property.  
  
 <  
 Необязательный. Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.  
  
 `attribute`  
 Обязательный. Name of the attribute to access, of the form [`prefix`:]`name`.  
  
|Отделение|Описание|  
|----------|-----------------|  
|`prefix`|Необязательный. XML namespace prefix for the attribute. Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.|  
|`name`|Обязательный. Local attribute name. See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Необязательный. Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.  
  
## <a name="return-value"></a>Возвращаемое значение  
 A string that contains the value of `attribute`. If the attribute name does not exist, `Nothing` is returned.  
  
## <a name="remarks"></a>Заметки  
 You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects. You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.  
  
 When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.  
  
 The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers. To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement. В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML-элемента. For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Пример  
 The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 Этот пример кода отображает следующий текст:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Пример  
 The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object. The `type` attribute is created declaratively and the `owner` attribute is created dynamically.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 Этот пример кода отображает следующий текст:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Пример  
 The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone type: work`  
  
## <a name="example"></a>Пример  
 В следующем примере `ns` объявляется как префикс пространства имен XML. It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
