---
title: "Свойство дочерней оси XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyChildAxis"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "child axis - свойство [Visual Basic]"
  - "код Visual Basic, доступ к XML"
  - "XML [Visual Basic], доступ"
  - "оси XML [Visual Basic], дочерний"
  - "XML child axis - свойство [Visual Basic]"
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Свойство дочерней оси XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Предоставляет доступ к дочерним элементам одного из следующих: объекта <xref:System.Xml.Linq.XElement>, объекта <xref:System.Xml.Linq.XDocument>, коллекции объектов <xref:System.Xml.Linq.XElement> или коллекции объектов <xref:System.Xml.Linq.XDocument>.  
  
## Синтаксис  
  
```  
  
object.<child>  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`object`|Обязательный.  Объект <xref:System.Xml.Linq.XElement>, объект <xref:System.Xml.Linq.XDocument>, коллекция объектов <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XDocument>.|  
|.\<|Обязательный.  Обозначает начало свойства дочерней оси.|  
|`child`|Обязательный.  Имя дочерних узлов для доступа в форме \[`prefix``:`\]`name`.<br /><br /> -   `Prefix` \- необязательный.  Префикс пространства имен XML для дочернего узла.  Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.<br />-   `Name` — обязательный.  Имя локального дочернего узла.  См. раздел [Имена объявляемых элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
|\>|Обязательный.  Обозначает конец свойства дочерней оси.|  
  
## Возвращаемое значение  
 Коллекция объектов <xref:System.Xml.Linq.XElement>.  
  
## Заметки  
 Свойство дочерней оси XML можно использовать для доступа к дочерним узлам по имени из объекта <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> или из коллекции объектов <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>.  Используйте XML\-свойство `Value` для доступа к значению первого дочернего узла в возвращаемой коллекции.  Подробнее [Свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] преобразует свойства дочерней оси для вызовов метода <xref:System.Xml.Linq.XContainer.Elements%2A>.  
  
## Пространства имен XML  
 Имя в свойстве дочерней оси может использовать только префиксы пространства имен XML, объявленные глобально с помощью метода `Imports`.  В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML\-элемента.  Подробнее: [Оператор Imports \(пространство имен XML\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## Пример  
 В следующем примере показано, как получить доступ к дочерним узлам `phone` из объекта `contact`.  
  
 [!code-vb[VbXMLSamples#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Home Phone = 206-555-0144`  
  
## Пример  
 В следующем примере показано, как получить доступ к дочерним узлам с именем `phone` из коллекции, возвращенной свойством дочерней оси `contact` объекта `contacts`.  
  
 [!code-vb[VbXMLSamples#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Home Phone = 206-555-0144`  
  
## Пример  
 В следующем примере `ns` объявляется как префикс пространства имен XML.  Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Patrick Hines`  
  
## См. также  
 <xref:System.Xml.Linq.XElement>   
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Имена объявляемых элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)