---
title: "Свойство дочерней оси XML (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyDescendantsAxis"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "descendant axis - свойство [Visual Basic]"
  - "код Visual Basic, доступ к XML"
  - "XML [Visual Basic], доступ"
  - "оси XML [Visual Basic], потомок"
  - "XML descendant axis - свойство [Visual Basic]"
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Свойство дочерней оси XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Предоставляет доступ к дочерним элементам одного из следующих объектов: объект <xref:System.Xml.Linq.XElement>, объект <xref:System.Xml.Linq.XDocument>, коллекция объектов <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XDocument>.  
  
## Синтаксис  
  
```  
  
object...<descendant>  
```  
  
## Части  
 `object`  
 Обязательный.  Объект <xref:System.Xml.Linq.XElement>, объект <xref:System.Xml.Linq.XDocument>, коллекция объектов <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XDocument>.  
  
 ...\<  
 Обязательный.  Обозначает начало свойства дочерней оси.  
  
 `descendant`  
 Обязательный.  Имя дочерних узлов для доступа, формы \[`prefix``:`\]`name`.  
  
|Часть|Описание|  
|-----------|--------------|  
|`prefix`|Необязательный.  Префикс пространства имен XML для дочернего узла.  Должно быть глобальное пространство имен XML, которое определяется с помощью оператора `Imports`.|  
|`name`|Обязательный.  Локальное имя дочернего узла.  Дополнительные сведения см. в разделе [Имена объявляемых элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Обязательный.  Обозначает конец свойства дочерней оси.  
  
## Возвращаемое значение  
 Коллекция объектов <xref:System.Xml.Linq.XElement>.  
  
## Заметки  
 Можно использовать свойства дочерней оси XML, чтобы получить доступ по имени к дочерним узлам из объекта <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> или из коллекции объектов <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>.  Для доступа к значению первого дочернего узла в возвращаемой коллекции используется свойство `Value` XML.  Дополнительные сведения см. в разделе [Свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] преобразует свойства дочерней оси в вызовы метода <xref:System.Xml.Linq.XContainer.Descendants%2A>.  
  
## Пространства имен XML  
 Имя в свойстве дочерней оси может использовать только пространства имен, объявленных глобально оператором `Imports`.  Оно не может использовать пространства имен XML, объявленные локально с помощью литералов XML\-элемента.  Дополнительные сведения см. в разделе [Оператор Imports \(пространство имен XML\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## Пример  
 В следующем примере показано, как получить доступ к значению первого потомка узла с именем `name` и значения всех узлов, являющихся потомками с именем `phone` из объекта `contacts`.  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 В этом коде отображается следующий текст:  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## Пример  
 В следующем примере `ns` объявляется как префикс пространства имен XML.  Затем используется префикс пространства имен для создания литерала XML и доступа к значению первого дочернего узла, имеющего полное имя `ns:name`.  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 В этом коде отображается следующий текст:  
  
 `Name: Patrick Hines`  
  
## См. также  
 <xref:System.Xml.Linq.XElement>   
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Имена объявляемых элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)