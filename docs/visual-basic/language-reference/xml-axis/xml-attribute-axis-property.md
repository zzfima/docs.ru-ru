---
title: Свойство оси атрибута XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a286c70f57128d0406b3a300610fea5e1c44b32d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
 Обязательный. <xref:System.Xml.Linq.XElement> Объект или коллекцию <xref:System.Xml.Linq.XElement> объектов.  
  
 .@  
 Обязательный. Обозначает начало свойства оси атрибута.  
  
 <  
 Необязательно. Обозначает начало имени атрибута при `attribute` не является допустимым идентификатором в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
 `attribute`  
 Обязательный. Имя атрибута для доступа к формы [`prefix`:]`name`.  
  
|Отделение|Описание|  
|----------|-----------------|  
|`prefix`|Необязательно. Префикс пространства имен XML для атрибута. Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.|  
|`name`|Обязательный. Имя локального атрибута. В разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Необязательно. Обозначает конец имени атрибута при `attribute` не является допустимым идентификатором в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
## <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая значение `attribute`. Если имя атрибута не существует, `Nothing` возвращается.  
  
## <a name="remarks"></a>Примечания  
 Свойство оси атрибута XML можно использовать для доступа к значению атрибута по имени из <xref:System.Xml.Linq.XElement> объекта или с первого элемента в коллекции <xref:System.Xml.Linq.XElement> объектов. Можно извлечь значение атрибута по имени или добавить новый атрибут в элемент, указав новое имя, начинающееся с идентификатора @.  
  
 При ссылке на XML-атрибутов с помощью идентификатора @, значение атрибута возвращается в виде строки, и необходимо явно указать <xref:System.Xml.Linq.XAttribute.Value%2A> свойство.  
  
 Правила именования для XML-атрибутов отличаются от правила именования для [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] идентификаторы. Чтобы получить доступ к XML-атрибут, который имеет имя, которое не является допустимым идентификатором Visual Basic, заключите имя в угловые скобки (\< и >).  
  
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
 В следующем примере используется синтаксис угловых скобок, необходимо получить значение атрибута XML с именем `number-type`, который не является допустимым идентификатором в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
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
