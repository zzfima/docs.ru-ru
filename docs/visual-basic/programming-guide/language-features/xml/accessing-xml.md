---
title: "Доступ к XML в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 79c7b8a94731e151a803a041d91dd1e240ddeb97
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-xml-in-visual-basic"></a>Доступ к XML в Visual Basic
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]предоставляет свойства оси XML для доступа и перемещения по [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] структуры. Эти свойства используют специальный синтаксис для доступа к элементам и атрибутам, указав имена XML.  
  
 В следующей таблице перечислены возможности языка, которые позволяют получить доступ к XML-элементов и атрибутов в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
### <a name="xml-axis-properties"></a>Свойства оси XML  
  
|Описание свойства|Пример|Описание|  
|--------------------------|-------------|-----------------|  
|*дочерняя ось*|`contact.<phone>`|Возвращает все `phone` элементы, которые являются дочерними элементами `contact` элемента.|  
|*ось атрибутов*|`phone.@type`|Возвращает все `type` атрибуты `phone` элемента.|  
|*оси-потомка*|`contacts...<name>`|Возвращает все `name` элементы `contacts` элемент, независимо от того, насколько глубоко в иерархии.|  
|*индексатор расширения*|`contacts...<name>(0)`|Возвращает первый `name` элемента последовательности.|  
|*value*|`contacts...<name>.Value`|Возвращает строковое представление первого объекта в последовательности, или `Nothing` Если последовательность пуста.|  
  
## <a name="in-this-section"></a>Содержание  
 [Практическое руководство. Доступ к элементам-потомкам XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Показано, как использовать свойство дочерней оси для доступа ко всем элементам XML, которые имеют указанное имя и расположены под указанным элементом XML.  
  
 [Практическое руководство. Доступ к дочерним XML-элементам](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Демонстрируется использование дочернего свойства оси для доступа к все дочерние элементы XML, которые имеют указанное имя в элементе XML.  
  
 [Практическое руководство. Доступ к XML-атрибутам](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Показано, как использовать свойство оси атрибута для доступа ко всем атрибутам XML, которые имеют указанное имя в элементе XML.  
  
 [Практическое руководство. Объявление и использование префиксов пространств имен XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Показано, как объявить префикс пространства имен XML и использовать его для создания и доступа к XML-элементов.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Свойства оси XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 Ссылки на разделы, описывающие различные свойства XML доступа.  
  
 [Общие сведения о LINQ to XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Предоставляет сведения об использовании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.  
  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Предоставляет сведения об использовании XML-литералов в Visual Basic.  
  
 [Работа с XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Ссылки на разделы о загрузке и изменении XML в Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Содержит ссылки на разделы, в которых описываются способы использования [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.
