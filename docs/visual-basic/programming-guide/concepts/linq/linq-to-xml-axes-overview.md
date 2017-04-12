---
title: "LINQ to XML оси Обзор (Visual Basic) | Документы Microsoft"
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
ms.assetid: 9161f151-cfa8-4408-94ba-08a9ba3a486d
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b127aa6b443e865c76831d886f110550ec785e9b
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-axes-overview-visual-basic"></a>LINQ to XML Обзор осей (Visual Basic)
После создания XML-дерева или загрузки XML-документа в XML-дерево можно опросить его для поиска элементов и атрибутов и извлечения их значений. Коллекции получают с помощью *методы оси*, который также называется *осей*. Некоторые оси являются методами в <xref:System.Xml.Linq.XElement>и <xref:System.Xml.Linq.XDocument>классы, которые возвращают <xref:System.Collections.Generic.IEnumerable%601>коллекций.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Некоторые оси являются методами расширений в <xref:System.Xml.Linq.Extensions>класс.</xref:System.Xml.Linq.Extensions> Оси, которые реализованы как методы расширений, работают с коллекциями и возвращают коллекции.  
  
 Как описано в [о классе XElement](http://msdn.microsoft.com/library/d35180fe-7016-4895-9bfc-ba1e3f7875ec), <xref:System.Xml.Linq.XElement>объект представляет собой узел одного элемента.</xref:System.Xml.Linq.XElement> Содержимое элемента может быть сложным (иногда называется структурированным содержимым), или это может быть простой элемент. Простой элемент может быть пустым или содержать значение. Если узел содержит структурированное содержимое, можно использовать различные методы оси, чтобы получить перечисление элементов-потомков. Наиболее часто используемыми методами оси являются <xref:System.Xml.Linq.XContainer.Elements%2A>и <xref:System.Xml.Linq.XContainer.Descendants%2A>.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XContainer.Elements%2A>  
  
 В дополнение к методам оси, которые возвращают коллекции, есть еще два метода, как правило, используются в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] запросов. <xref:System.Xml.Linq.XContainer.Element%2A>Метод возвращает одиночный <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Element%2A> <xref:System.Xml.Linq.XElement.Attribute%2A>Метод возвращает одиночный <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement.Attribute%2A>  
  
 Во многих случаях запросы [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] обеспечивают самый эффективный способ проверки и преобразования дерева и извлечения из него данных. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]запросы работают с объектами, реализующими <xref:System.Collections.Generic.IEnumerable%601>и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] осей возвращают <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>коллекций, и <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XAttribute>коллекций.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.IEnumerable%601> Эти коллекции нужны для выполнения запросов.  
  
 В дополнение к методам оси, получающим коллекции элементов и атрибутов, существуют методы оси, которые позволяют проходить по всему дереву максимально подробно. Например, вместо того чтобы иметь дело с элементами и атрибутами, можно работать с узлами дерева. Узлы - это более глубокий уровень гранулярности, чем элементы и атрибуты. При работе с узлами можно просматривать комментарии XML, текстовые узлы XML, инструкции по обработке XML и др. Эти возможности важны, например, для разработчика текстового процессора, который хочет сохранить документы как XML. Обычно большинство программистов на XML в первую очередь связаны с элементами, атрибутами и их значениями.  
  
## <a name="methods-for-retrieving-a-collection-of-elements"></a>Методы получения коллекции элементов  
 Ниже приводится сводка методов <xref:System.Xml.Linq.XElement>класса (или его базовых классов), вызываемый на <xref:System.Xml.Linq.XElement>для возврата коллекции элементов.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement>  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName>|Возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>предков элемента.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Перегрузка возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>предков, у которых есть указанный <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName>|Возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>потомков этого элемента.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Перегрузка возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>потомков, у которых есть указанный <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>|Возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>дочерних элементов данного элемента.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Перегрузка возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>дочерних элементов, имеющих указанный <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName>|Возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>элементов, идущих после.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Перегрузка возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>элементов, после этого элемента, имеющих указанный <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName>|Возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>элементов, идущих перед экземпляром.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Перегрузка возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>элементов перед данным элементом, имеющих указанный <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName>|Возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>этот элемент и его предки.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Перегрузка возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>элементов, имеющих указанный <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName>|Возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>этого элемента и его потомков.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Перегрузка возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>элементов, имеющих указанный <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
  
## <a name="method-for-retrieving-a-single-element"></a>Метод получения одного элемента  
 Следующий метод получает один дочерний элемент из <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement>  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>|Возвращает первый дочерний <xref:System.Xml.Linq.XElement>объект, который имеет указанный <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement>|  
  
## <a name="method-for-retrieving-a-collection-of-attributes"></a>Метод получения коллекции атрибутов  
 Следующий метод позволяет получить атрибуты из <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement>  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName>|Возвращает <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XAttribute>всех атрибутов.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601>|  
  
## <a name="method-for-retrieving-a-single-attribute"></a>Метод получения одного атрибута  
 Следующий метод получает один атрибут из <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement>  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>|Возвращает <xref:System.Xml.Linq.XAttribute>с указанного <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XAttribute>|  
  
## <a name="see-also"></a>См. также  
 [Оси LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
