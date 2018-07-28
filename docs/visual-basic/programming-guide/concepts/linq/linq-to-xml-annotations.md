---
title: LINQ to XML Annotations2
ms.date: 07/20/2015
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
ms.openlocfilehash: a7b81b8c1856c11cb0c5e777f31986a330cf115f
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332926"
---
# <a name="linq-to-xml-annotations"></a>Примечания LINQ to XML
Заметки в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяют ассоциировать любой произвольный объект любого произвольного типа с любым XML-компонентом XML-дерева.  
  
 Чтобы добавить заметку к компоненту XML, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute>, следует вызвать метод <xref:System.Xml.Linq.XObject.AddAnnotation%2A>. Заметки получаются по типу.  
  
 Обратите внимание, что заметки не являются частью набора сведений XML, они не могут быть сериализованы или десериализованы.  
  
## <a name="methods"></a>Методы  
 При работе с заметками можно использовать следующие методы.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|Добавляет объект к списку заметок <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|Извлекает первый объект заметки указанного типа из <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|Извлекает коллекцию заметок указанного типа для <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|Удаляет заметки указанного типа из <xref:System.Xml.Linq.XObject>.|  
  
## <a name="see-also"></a>См. также  
 [Расширенные программированию LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
