---
title: LINQ to XML Annotations2
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ca84af7cd750529eadb9d0967f4d5570b7038a07
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
 [Дополнительно LINQ to XML, программирования (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
