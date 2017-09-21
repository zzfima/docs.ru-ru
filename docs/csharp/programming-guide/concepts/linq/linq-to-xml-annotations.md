---
title: "Примечания LINQ to XML3"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3fa8715deac8776f7a512439ee055be6faf4649f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

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
 [Расширенные методы программирования LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

