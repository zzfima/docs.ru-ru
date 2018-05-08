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
ms.openlocfilehash: 3e02fd2ddc3928bdd2e9741737fc31fb2b16901c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="xml-attribute-axis-property-visual-basic"></a>Свойство оси атрибута XML (Visual Basic)
Предоставляет доступ к значению атрибута для <xref:System.Xml.Linq.XElement> объекта или первый элемент в коллекцию <xref:System.Xml.Linq.XElement> объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Части  
 `object`  
 Обязательно. <xref:System.Xml.Linq.XElement> Объект или коллекцию <xref:System.Xml.Linq.XElement> объектов.  
  
 .@  
 Обязательно. Обозначает начало свойства оси атрибута.  
  
 <  
 Необязательный. Обозначает начало имени атрибута при `attribute` не является допустимым идентификатором в Visual Basic.  
  
 `attribute`  
 Обязательно. Имя атрибута для доступа к формы [`prefix`:]`name`.  
  
|Отделение|Описание|  
|----------|-----------------|  
|`prefix`|Необязательный. Префикс пространства имен XML для атрибута. Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.|  
|`name`|Обязательно. Имя локального атрибута. В разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Необязательный. Обозначает конец имени атрибута при `attribute` не является допустимым идентификатором в Visual Basic.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая значение `attribute`. Если имя атрибута не существует, `Nothing` возвращается.  
  
## <a name="remarks"></a>Примечания  
 Свойство оси атрибута XML можно использовать для доступа к значению атрибута по имени из <xref:System.Xml.Linq.XElement> объекта или с первого элемента в коллекции <xref:System.Xml.Linq.XElement> объектов. Можно извлечь значение атрибута по имени или добавить новый атрибут в элемент, указав новое имя, начинающееся с идентификатора @.  
  
 При ссылке на XML-атрибутов с помощью идентификатора @, значение атрибута возвращается в виде строки, и необходимо явно указать <xref:System.Xml.Linq.XAttribute.Value%2A> свойство.  
  
 Правила именования для XML-атрибутов отличаются от правилам именования идентификаторов Visual Basic. Чтобы получить доступ к XML-атрибут, который имеет имя, которое не является допустимым идентификатором Visual Basic, заключите имя в угловые скобки (\< и >).  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 Имя в свойство оси атрибута можно использовать только префиксы пространства имен XML, объявленные глобально с помощью `Imports` инструкции. В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML-элемента. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Пример  
 Следующий пример показывает способ получения значений атрибутов XML с именем `type` из коллекции XML-элементов, которые именуются `phone`.  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как создать атрибуты для XML-элемента как декларативно как часть XML и динамически путем добавления атрибута в экземпляр <xref:System.Xml.Linq.XElement> объекта. `type` Атрибут создается декларативно и `owner` динамически создать атрибут.  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере используется синтаксис угловых скобок, необходимо получить значение атрибута XML с именем `number-type`, который не является допустимым идентификатором в Visual Basic.  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone type: work`  
  
## <a name="example"></a>Пример  
 В следующем примере `ns` объявляется как префикс пространства имен XML. Затем используется префикс пространства имен для создания литерала XML и доступа к первым дочерним узлом с помощью полного имени «`ns:name`».  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement>  
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
