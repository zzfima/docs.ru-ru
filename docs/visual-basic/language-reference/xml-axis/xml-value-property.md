---
title: "Свойство значения XML (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyExtensionValue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Value - свойство [Visual Basic]"
  - "код Visual Basic, доступ к XML"
  - "оси XML [Visual Basic], Значение"
  - "XML Value - свойство [Visual Basic]"
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Свойство значения XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Предоставляет доступ к значению первого элемента из коллекции объектов <xref:System.Xml.Linq.XElement>.  
  
## Синтаксис  
  
```  
  
object.Value  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`object`|Обязательный.  Коллекция объектов <xref:System.Xml.Linq.XElement>.|  
  
## Возвращаемое значение  
 `String`, содержащая значение первого элемента коллекции, или `Nothing`, если коллекция пуста.  
  
## Заметки  
 Свойство <xref:System.Xml.Linq.XElement.Value%2A> упрощает доступ к значению первого элемента в коллекции объектов <xref:System.Xml.Linq.XElement>.  Это свойство сначала проверяет, содержит ли коллекция по крайней мере один объект.  Если коллекция пуста, это свойство возвращает `Nothing`.  В противном случае это свойство возвращает значение свойства <xref:System.Xml.Linq.XElement.Value%2A> первого элемента в коллекции.  
  
> [!NOTE]
>  При обращении к значению XML\-атрибута с помощью идентификатора '@', значение атрибута возвращается как `String` и не нужно явно задавать свойство <xref:System.Xml.Linq.XAttribute.Value%2A>.  
  
 Можно использовать свойство индексатора расширения XML для доступа к другим элементам коллекции.  Дополнительные сведения см. в разделе [Свойство\-индексатор расширения](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).  
  
## Наследование  
 Большинству пользователей не придется реализовывать <xref:System.Collections.Generic.IEnumerable%601>, следовательно, можно проигнорировать этот раздел.  
  
 Свойство <xref:System.Xml.Linq.XElement.Value%2A> является расширением свойства для типов, реализующих `IEnumerable(Of XElement)`.  Привязка этого расширенного свойства похожа на привязку методов расширения: если тип реализует один из интерфейсов и определяет свойство с именем "Value", это свойство имеет приоритет перед свойством расширения.  Другими словами, свойство <xref:System.Xml.Linq.XElement.Value%2A> можно переопределять при помощи определения нового свойства в классе, который реализует `IEnumerable(Of XElement)`.  
  
## Пример  
 В следующем примере показано использование свойства <xref:System.Xml.Linq.XElement.Value%2A> для доступа к первому узлу в коллекции объектов <xref:System.Xml.Linq.XElement>.  В примере используется свойство дочерней оси для получения коллекции всех дочерних узлов с именами `phone`, находящихся в объекте `contact`.  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-value-property_1.vb)]  
  
 В этом коде отображается следующий текст:  
  
 `Phone number: 206-555-0144`  
  
## Пример  
 В следующем примере показано получение значения XML\-атрибута из коллекции объектов <xref:System.Xml.Linq.XAttribute>.  В примере свойство атрибута оси применяется для отображения значения атрибута `type` для всех элементов `phone`.  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-value-property_2.vb)]  
  
 В этом коде отображается следующий текст:  
  
 `home`  
  
 `work`  
  
## См. также  
 <xref:System.Xml.Linq.XElement>   
 <xref:System.Collections.Generic.IEnumerable%601>   
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Свойство\-индексатор расширения](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)   
 [Свойство дочерней оси XML](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)   
 [Свойство оси атрибута XML](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)