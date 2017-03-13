---
title: "Свойство оси атрибута XML (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyAttributeAxis"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "attribute axis - свойство [Visual Basic]"
  - "код Visual Basic, доступ к XML"
  - "XML [Visual Basic], доступ"
  - "XML attribute axis - свойство [Visual Basic]"
  - "оси XML [Visual Basic], атрибут"
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Свойство оси атрибута XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Предоставляет доступ к значению атрибута для объекта <xref:System.Xml.Linq.XElement> или к первому элементу в коллекции объектов <xref:System.Xml.Linq.XElement>.  
  
## Синтаксис  
  
```  
  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## Части  
 `object`  
 Обязательный.  Объект <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XElement>.  
  
 .@  
 Обязательный.  Обозначает начало свойства оси атрибута.  
  
 \<  
 Необязательный.  Обозначает начало имени атрибута, если `attribute` не является допустимым идентификатором в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 `attribute`  
 Обязательный.  Имя атрибута, к которому осуществляется доступ, в форме \[`prefix`:\]`name`.  
  
|Часть|Описание|  
|-----------|--------------|  
|`prefix`|Необязательный.  Префикс пространства имен XML для атрибута.  Должно быть глобальным пространством имен XML, определенным при помощи оператора `Imports`.|  
|`name`|Обязательный.  Имя локального атрибута.  Дополнительные сведения см. в разделе [Имена объявляемых элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Необязательный.  Обозначает конец имени атрибута, если `attribute` не является допустимым идентификатором в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## Возвращаемое значение  
 Строка, содержащая значение `attribute`.  Если атрибута с таким именем не существует, возвращается значение `Nothing`.  
  
## Заметки  
 Можно использовать свойство оси XML\-атрибута для доступа к значению атрибута по имени из объекта <xref:System.Xml.Linq.XElement> или из первого элемента в коллекции объектов <xref:System.Xml.Linq.XElement>.  Можно извлечь значение атрибута по имени или добавить новый атрибут в элемент, указав новое имя, начинающееся с идентификатора @.  
  
 При обращении к XML\-атрибуту с помощью идентификатора @, значение атрибута возвращается в виде строки, и не нужно явно задавать свойство <xref:System.Xml.Linq.XAttribute.Value%2A>.  
  
 Правила именования для XML\-атрибутов отличаются от правила именования для идентификаторов [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]. Для доступа к XML\-атрибуту с именем, которое не является допустимым идентификатором в Visual Basic, заключите имя в угловые скобки \(\< и \>\).  
  
## Пространства имен XML  
 Имя в свойстве атрибута оси может использовать только префиксы пространств имен XML, объявленные глобально с помощью инструкции `Imports`.  Оно не может использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML\-элемента.  Дополнительные сведения см. в разделе [Оператор Imports \(пространство имен XML\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## Пример  
 В следующем примере показано получение значений из XML\-атрибутов с именем `type` из коллекции XML\-элементов, которая называется `phone`.  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 В этом коде отображается следующий текст:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## Пример  
 Пример, как создать атрибуты для XML\-элемента декларативно, как часть XML, и динамически, путем добавления атрибута экземпляру объекта <xref:System.Xml.Linq.XElement>.  Атрибут `type` создается декларативно и атрибут `owne` создается динамически.  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 В этом коде отображается следующий текст:  
  
```  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## Пример  
 В следующем примере используется синтаксис угловых скобок, чтобы получить значение атрибута XML с именем `number-type`, который не является допустимым идентификатором в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 В этом коде отображается следующий текст:  
  
 `Phone type: work`  
  
## Пример  
 В следующем примере `ns` объявляется как префикс пространства имен XML.  Затем используется префикс пространства имен для создания литерала XML и доступа к первому дочернему узлу, имеющему полное имя "`ns:name`".  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 В этом коде отображается следующий текст:  
  
 `Phone type: home`  
  
## См. также  
 <xref:System.Xml.Linq.XElement>   
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Имена объявляемых элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)