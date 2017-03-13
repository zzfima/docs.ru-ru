---
title: "Практическое руководство. Доступ к производным XML элементам (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "descendant axis - свойство [Visual Basic]"
  - "XML [Visual Basic], доступ"
  - "оси XML [Visual Basic], потомок"
  - "XML descendant axis - свойство [Visual Basic]"
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Практическое руководство. Доступ к производным XML элементам (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Этот пример демонстрирует использование свойства оси\-потомка для доступа ко всем элементам XML, которые имеют указанное имя и расположены под указанным элементом XML.  В частности, в нем используется свойство `Value` для получения значения первого элемента в коллекции, которое возвращает свойство дочерней оси `name`.  Свойство дочерней оси `name` возвращает все элементы с именем `name`, которые содержатся в объекте `contacts`.  В примере также используется свойство дочерней оси `phone` для доступа ко всем потомкам с именем `phone`, содержащимся в объекте `contacts`.  
  
## Пример  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылка на пространство имен <xref:System.Xml.Linq>.  
  
## См. также  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName>   
 [Свойство дочерней оси XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [Свойство значения XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)   
 [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)