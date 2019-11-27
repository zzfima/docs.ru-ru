---
title: Доступ к XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 1fa1d94fc710272ac0ba9ea7167989da42a51fcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351751"
---
# <a name="accessing-xml-in-visual-basic"></a>Доступ к XML в Visual Basic
Visual Basic предоставляет свойства осей XML для доступа и навигации по структурам [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Эти свойства используют специальный синтаксис, позволяющий получить доступ к элементам и атрибутам, указав имена XML.  
  
 В следующей таблице перечислены функции языка, позволяющие получать доступ к XML-элементам и атрибутам в Visual Basic.  
  
### <a name="xml-axis-properties"></a>Свойства оси XML  
  
|Описание свойства|Пример|Описание|  
|--------------------------|-------------|-----------------|  
|*дочерняя ось*|`contact.<phone>`|Возвращает все элементы `phone`, являющиеся дочерними элементами элемента `contact`.|  
|*ось атрибутов*|`phone.@type`|Возвращает все атрибуты `type` элемента `phone`.|  
|*ось потомков*|`contacts...<name>`|Возвращает все элементы `name` элемента `contacts`, независимо от того, насколько глубоко они находятся в иерархии.|  
|*индексатор расширения*|`contacts...<name>(0)`|Возвращает первый элемент `name` из последовательности.|  
|*значение*|`contacts...<name>.Value`|Возвращает строковое представление первого объекта в последовательности или `Nothing`, если последовательность пуста.|  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Доступ к элементам-потомкам XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Показывает, как использовать свойство оси потомков для доступа ко всем XML-элементам с указанным именем и содержащимся в указанном XML-элементе.  
  
 [Практическое руководство. Доступ к дочерним XML-элементам](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Показывает, как использовать свойство дочерней оси для доступа ко всем дочерним элементам XML с указанным именем в элементе XML.  
  
 [Практическое руководство. Доступ к XML-атрибутам](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Показывает, как использовать свойство оси атрибута для доступа ко всем XML-атрибутам, имеющим указанное имя в элементе XML.  
  
 [Практическое руководство. Объявление и использование префиксов пространств имен XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Показывает, как объявить префикс пространства имен XML и использовать его для создания и доступа к XML-элементам.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Свойства оси XML](../../../../visual-basic/language-reference/xml-axis/index.md)  
 Содержит ссылки на разделы, описывающие различные свойства доступа к XML.  
  
 [Общие сведения о LINQ to XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Общие сведения об использовании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.  
  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Общие сведения об использовании литералов XML в Visual Basic.  
  
 [Работа с XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Содержит ссылки на разделы, посвященные загрузке и изменению XML в Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Содержит ссылки на разделы, описывающие использование [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.
