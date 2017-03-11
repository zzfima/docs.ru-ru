---
title: "Доступ к XML в Visual Basic | Microsoft Docs"
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
  - "доступ к XML [Visual Basic], свойства оси"
  - "LINQ to XML [Visual Basic], доступ к XML"
  - "код Visual Basic, XML"
  - "XML [Visual Basic], доступ"
  - "XML [Visual Basic], свойства оси"
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Доступ к XML в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет свойства координат XML для доступа и перемещения по [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] структурам.  Эти свойства используют специальный синтаксис для предоставления доступа к элементам и атрибутам с помощью указания имен XML.  
  
 В следующей таблице перечислены средства языка, которые позволяют получить доступ к элементам XML и атрибутам в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
### Свойства оси XML  
  
|Описание свойства|Пример|Описание|  
|-----------------------|------------|--------------|  
|*дочерняя ось*|`contact.<phone>`|Дает все элементы `phone`, которые являются дочерними элемента `contact`.|  
|*ось атрибутов*|`phone.@type`|Дает все атрибуты `type` элемента `phone`.|  
|*ось потомков*|`contacts...<name>`|Дает все элементы `name` элемента `contacts` независимо от степени их вложенности в иерархии.|  
|*индексатор расширения*|`contacts...<name>(0)`|Дает первый элемент `name` из последовательности.|  
|*value*|`contacts...<name>.Value`|Дает строковое представление первого объекта в последовательности или `Nothing`, если последовательность пуста.|  
  
## В этом подразделе  
 [Практическое руководство. Доступ к элементам\-потомкам XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Демонстрация использования свойства оси потомков для доступа ко всем элементам XML, которые имеют указанное имя и расположены под указанным элементом XML.  
  
 [Практическое руководство. Доступ к дочерним XML\-элементам](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Демонстрация использования свойства дочерней оси для доступа ко всем дочерним XML\-элементам, имеющим указанное имя в XML\-элементе.  
  
 [Практическое руководство. Доступ к XML\-атрибутам](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Демонстрация использования свойства атрибута оси для доступа ко всем XML\-атрибутам, которые имеют указанное имя в элементе XML.  
  
 [Практическое руководство. Объявление и использование префиксов пространств имен XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Описание способов объявления префикса пространства имен XML и его использования для создания XML\-элементов и доступа к ним.  
  
## Связанные подразделы  
 [Свойства оси XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 Содержит ссылки на разделы, описывающие различные свойства XML доступа.  
  
 [Общие сведения о LINQ to XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Введение в использование [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] в Visual Basic.  
  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Введение в использование литералов XML в Visual Basic.  
  
 [Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Содержит ссылки на разделы о загрузке и изменении XML в Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Содержит ссылки на разделы, описывающие использование [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] в Visual Basic.