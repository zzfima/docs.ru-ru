---
title: "Доступ к XML в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 215f057f0b4d884369aad53cbbdbb98f240b56c4
ms.lasthandoff: 03/13/2017

---
# <a name="accessing-xml-in-visual-basic"></a>Доступ к XML в Visual Basic
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет свойства осей XML для доступа и перемещения по [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] структуры. Эти свойства используют специальный синтаксис для доступа к элементам и атрибутам, указав имена XML.  
  
 В следующей таблице перечислены средства языка, которые позволяют получить доступ к XML-элементов и атрибутов в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### <a name="xml-axis-properties"></a>Свойства оси XML  
  
|Описание свойства|Пример|Описание|  
|--------------------------|-------------|-----------------|  
|*дочерняя ось*|`contact.<phone>`|Возвращает все `phone` элементы, которые являются дочерними элементами элемента `contact` элемент.|  
|*ось атрибутов*|`phone.@type`|Возвращает все `type` атрибуты `phone` элемента.|  
|*оси-потомка*|`contacts...<name>`|Возвращает все `name` элементы `contacts` элемент, независимо от того, насколько глубоко в иерархии.|  
|*индексатор расширения*|`contacts...<name>(0)`|Возвращает первый `name` элемент из последовательности.|  
|*value*|`contacts...<name>.Value`|Возвращает строковое представление первого объекта в последовательности, или `Nothing` , если последовательность пуста.|  
  
## <a name="in-this-section"></a>Содержание  
 [Практическое руководство. Доступ к элементам-потомкам XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Показано, как использовать свойство дочерней оси для доступа ко всем элементам XML, которые имеют указанное имя и расположены под указанным элементом XML.  
  
 [Практическое руководство. Доступ к дочерним XML-элементам](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Демонстрируется использование дочернего свойства ось для доступа к все дочерние элементы XML, которые имеют указанное имя в элементе XML.  
  
 [Практическое руководство. Доступ к XML-атрибутам](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Показано, как использовать свойство оси атрибута для доступа ко всем атрибутам XML, которые имеют указанное имя в элементе XML.  
  
 [Практическое руководство. Объявление и использование префиксов пространств имен XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Показано, как объявить префикс пространства имен XML и использовать его для создания и доступа к XML-элементов.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Свойства оси XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 Ссылки на разделы, описывающие различные свойства XML доступа.  
  
 [Общие сведения о LINQ to XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Введение в использование [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] в Visual Basic.  
  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Введение в использование литералов XML в Visual Basic.  
  
 [Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Содержит ссылки на разделы о загрузке и изменении XML в Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Содержит ссылки на разделы, описывающие, как использовать [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] в Visual Basic.
