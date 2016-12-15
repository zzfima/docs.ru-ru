---
title: "Практическое руководство. Доступ к дочерним XML-элементам (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "child axis - свойство [Visual Basic]"
  - "XML [Visual Basic], доступ"
  - "оси XML [Visual Basic], дочерний"
  - "XML child axis - свойство [Visual Basic]"
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Доступ к дочерним XML-элементам (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Этот пример демонстрирует использование свойства дочерней оси для доступа ко всем дочерним XML\-элементам, имеющим указанное имя в XML\-элементе.  В частности, в нем используется свойство <xref:System.Xml.Linq.XElement.Value%2A>, чтобы получить значение первого элемента в коллекции, которое возвращает свойство дочерней оси `name`.  Свойство дочерней оси `name` получает все дочерние элементы с именем `phone` в объекте `contact`.  Кроме того, в этом примере используется свойство дочерней оси `phone` для доступа ко всем дочерним элементам с именем `phone`, которые содержатся в объекте `contact`.  
  
## Пример  
 [!code-vb[VbXMLSamples#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-child-elements_1.vb)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылка на пространство имен <xref:System.Xml.Linq>.  
  
## См. также  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>   
 [Свойство дочерней оси XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)   
 [Свойство значения XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)   
 [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)