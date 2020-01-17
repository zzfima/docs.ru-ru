---
title: Общие сведения об осях LINQ to XML (C#)
ms.date: 07/20/2015
ms.assetid: 516792fb-461d-40a8-8a50-9993a51258fc
ms.openlocfilehash: c8b64731925f37d54bded62fae4ccae9933ffbe9
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635526"
---
# <a name="linq-to-xml-axes-overview-c"></a>Общие сведения об осях LINQ to XML (C#)
После создания XML-дерева или загрузки XML-документа в XML-дерево можно опросить его для поиска элементов и атрибутов и извлечения их значений. Коллекции получают с помощью *методов оси*, называемых также *осями*. Некоторые оси являются методами в классах <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XDocument>, которые возвращают коллекции <xref:System.Collections.Generic.IEnumerable%601>. Некоторые оси являются методами расширений в классе <xref:System.Xml.Linq.Extensions>. Оси, которые реализованы как методы расширений, работают с коллекциями и возвращают коллекции.  
  
 Как описано в разделе [Общие сведения о классе XElement](./xelement-class-overview.md), объект <xref:System.Xml.Linq.XElement> представляет собой узел с одним элементом. Содержимое элемента может быть сложным (иногда называется структурированным содержимым), или это может быть простой элемент. Простой элемент может быть пустым или содержать значение. Если узел содержит структурированное содержимое, можно использовать различные методы оси, чтобы получить перечисление элементов-потомков. Наиболее часто используемыми методами оси являются <xref:System.Xml.Linq.XContainer.Elements%2A> и <xref:System.Xml.Linq.XContainer.Descendants%2A>.  
  
 В дополнение к методам оси, которые возвращают коллекции, есть еще два метода, которые обычно используются в запросах [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Метод <xref:System.Xml.Linq.XContainer.Element%2A> возвращает одиночный <xref:System.Xml.Linq.XElement>. Метод <xref:System.Xml.Linq.XElement.Attribute%2A> возвращает одиночный <xref:System.Xml.Linq.XAttribute>.  
  
 Во многих случаях запросы LINQ обеспечивают самый эффективный способ проверки и преобразования дерева, а также извлечения из него данных. Запросы LINQ работают с объектами, которые реализуют <xref:System.Collections.Generic.IEnumerable%601>, а оси [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] возвращают <xref:System.Collections.Generic.IEnumerable%601> коллекций <xref:System.Xml.Linq.XElement> и <xref:System.Collections.Generic.IEnumerable%601> коллекций <xref:System.Xml.Linq.XAttribute>. Эти коллекции нужны для выполнения запросов.  
  
 В дополнение к методам оси, получающим коллекции элементов и атрибутов, существуют методы оси, которые позволяют проходить по всему дереву максимально подробно. Например, вместо того чтобы иметь дело с элементами и атрибутами, можно работать с узлами дерева. Узлы - это более глубокий уровень гранулярности, чем элементы и атрибуты. При работе с узлами можно просматривать комментарии XML, текстовые узлы XML, инструкции по обработке XML и др. Эти возможности важны, например, для разработчика текстового процессора, который хочет сохранить документы как XML. Обычно большинство программистов на XML в первую очередь связаны с элементами, атрибутами и их значениями.  
  
## <a name="methods-for-retrieving-a-collection-of-elements"></a>Методы получения коллекции элементов  
 Ниже приведена сводка методов класса <xref:System.Xml.Linq.XElement> (а также его базовых классов), которые можно вызвать в экземпляре <xref:System.Xml.Linq.XElement>, чтобы вернуть коллекцию элементов.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|Возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601> предков экземпляра <xref:System.Xml.Linq.XElement>. Перегрузка возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601> предков экземпляра <xref:System.Xml.Linq.XElement>, имеющих указанный атрибут <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>|Возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601> потомков экземпляра <xref:System.Xml.Linq.XElement>. Перегрузка возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601> потомков экземпляра <xref:System.Xml.Linq.XElement>, имеющих указанный атрибут <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|Возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601> дочерних элементов экземпляра <xref:System.Xml.Linq.XElement>. Перегрузка возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601> дочерних элементов экземпляра <xref:System.Xml.Linq.XElement>, имеющих указанный атрибут <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType>|Возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601> элементов, идущих после экземпляра <xref:System.Xml.Linq.XElement>. Перегрузка возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601> элементов, идущих после экземпляра <xref:System.Xml.Linq.XElement>, имеющих указанный атрибут <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>|Возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601> элементов, идущих перед экземпляром <xref:System.Xml.Linq.XElement>. Перегрузка возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601> элементов, идущих перед экземпляром <xref:System.Xml.Linq.XElement>, имеющих указанный атрибут <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|Возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601>, состоящую из самого экземпляра <xref:System.Xml.Linq.XElement> и его предков. Перегрузка возвращает <xref:System.Collections.Generic.IEnumerable%601> из <xref:System.Xml.Linq.XElement> для элементов с указанным <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType>|Возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601>, состоящую из самого экземпляра <xref:System.Xml.Linq.XElement> и его потомков. Перегрузка возвращает <xref:System.Collections.Generic.IEnumerable%601> из <xref:System.Xml.Linq.XElement> для элементов с указанным <xref:System.Xml.Linq.XName>.|  
  
## <a name="method-for-retrieving-a-single-element"></a>Метод получения одного элемента  
 Следующий метод позволяет получить один дочерний элемент из объекта <xref:System.Xml.Linq.XElement>.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=nameWithType>|Возвращает первый дочерний элемент объекта <xref:System.Xml.Linq.XElement>, имеющий указанный атрибут <xref:System.Xml.Linq.XName>.|  
  
## <a name="method-for-retrieving-a-collection-of-attributes"></a>Метод получения коллекции атрибутов  
 Следующий метод позволяет получить атрибуты из объекта <xref:System.Xml.Linq.XElement>.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|Возвращает коллекцию <xref:System.Collections.Generic.IEnumerable%601> всех атрибутов <xref:System.Xml.Linq.XAttribute>.|  
  
## <a name="method-for-retrieving-a-single-attribute"></a>Метод получения одного атрибута  
 Следующий метод позволяет получить один атрибут из объекта <xref:System.Xml.Linq.XElement>.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>|Возвращает атрибут <xref:System.Xml.Linq.XAttribute>, имеющий указанный атрибут <xref:System.Xml.Linq.XName>.|  
  
## <a name="see-also"></a>См. также

- [Оси LINQ to XML (C#)](linq-to-xml-axes-overview.md)
