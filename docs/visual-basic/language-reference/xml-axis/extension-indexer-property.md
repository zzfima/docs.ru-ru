---
title: "Свойство-индексатор расширения (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyExtensionIndexer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "индексатор расширения [Visual Basic]"
  - "код Visual Basic, доступ к XML"
  - "XML [Visual Basic], доступ"
  - "индексатор расширения XML [Visual Basic]"
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Свойство-индексатор расширения (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Предоставляет доступ к отдельным элементам в коллекции.  
  
## Синтаксис  
  
```  
  
object(index)  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`object`|Обязательный.  Коллекция, доступная для запросов.  Это коллекция, которая реализует <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>.|  
|\(|Обязательный.  Обозначает начало свойства индексатора.|  
|`index`|Обязательный.  Целочисленное выражение, задающее позицию элемента коллекции \(индексация ведется от нуля\).|  
|\)|Обязательный.  Обозначает конец свойства индексатора.|  
  
## Возвращаемое значение  
 Возвращает объект из указанного места в коллекции, или `Nothing`, если индекс находится вне допустимого диапазона.  
  
## Заметки  
 Для доступа к отдельным элементам в коллекции можно использовать свойство индексатора расширения.  Это свойство индексатора обычно используются на выходе свойства XML\-оси.  Свойства оси дочерних XML и XML\-потомков возвращают коллекцию объектов <xref:System.Xml.Linq.XElement> или значение атрибута.  
  
 Для вызова метода [!INCLUDE[ElementAtOrDefault]()] компилятор `vbprvb` преобразует свойства индексатора расширения. В отличие от индексатора массива метод`ElementAtOrDefault` возвращает `Nothing`, если индекс находится вне диапазона.  Это полезно, когда не удается легко определить число элементов в коллекции.  
  
 Это свойство индексатора напоминает свойство для коллекций, которые реализуют <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>: оно используется, только если в коллекции нет индексатора или свойства по умолчанию.  
  
 Для доступа к значению первого элемента в коллекции объектов <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute>, можно использовать XML\-свойство `Value`.  Дополнительные сведения см. в разделе [Свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## Пример  
 В следующем примере показано использование индексатора расширения для доступа ко второму дочернему узлу в коллекции объектов <xref:System.Xml.Linq.XElement>.  Доступ к коллекции осуществляется с помощью свойства дочерней оси, которое возвращает все дочерние элементы с именем `phone` в объекте `contact`.  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 В этом коде отображается следующий текст:  
  
 `Second phone number: 425-555-0145`  
  
## См. также  
 <xref:System.Xml.Linq.XElement>   
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)