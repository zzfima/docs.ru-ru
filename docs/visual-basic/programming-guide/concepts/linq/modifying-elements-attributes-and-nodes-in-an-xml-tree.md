---
title: Изменение элементов, атрибутов и узлов в XML Tree1
ms.date: 07/20/2015
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
ms.openlocfilehash: d548e6f5912437e5c5df27f55fcdb28990e92c8d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814904"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a>Изменение элементов, атрибутов и узлов в дереве XML
В следующей таблице приведена сводка методов и свойств, используемых для изменения элемента, его дочерних элементов или его атрибутов.  
  
 Следующие методы используются для изменения <xref:System.Xml.Linq.XElement>.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|Заменяет элемент проанализированным XML.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|Удаляет все содержимое (дочерние узлы и атрибуты) элемента.|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|Удаляет атрибуты элемента.|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|Заменяет все содержимое (дочерние узлы и атрибуты) элемента.|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|Заменяет атрибуты элемента.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|Устанавливает значение атрибута. Создает атрибут, если он не существует. Если значение устанавливается в `null`, удаляет атрибут.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|Задает значение дочернего элемента. Создает элемент, если он не существует. Если значение устанавливается в `null`, удаляет элемент.|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|Заменяет содержимое (дочерние узлы) элемента заданным текстом.|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|Задает значение элемента.|  
  
 Следующие методы используются для изменения <xref:System.Xml.Linq.XAttribute>.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|Устанавливает значение атрибута.|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|Устанавливает значение атрибута.|  
  
 Следующие методы предназначены для изменения <xref:System.Xml.Linq.XNode> (включая <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|Заменяет узел новым содержимым.|  
  
 Следующие методы предназначены для изменения <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|Заменяет дочерние узлы новым содержимым.|  
  
## <a name="see-also"></a>См. также

- [Изменение деревьев XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
