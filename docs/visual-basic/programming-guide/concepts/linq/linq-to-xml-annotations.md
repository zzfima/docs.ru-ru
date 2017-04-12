---
title: "LINQ to XML Annotations2 | Документы Microsoft"
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
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1f2e5bea1cde74548daa1697b6a0a819e3eba3e4
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-annotations"></a>Примечания LINQ to XML
Заметки в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] позволяют ассоциировать любой произвольный объект любого произвольного типа с любой компонент XML в XML-дерева.  
  
 Чтобы добавить заметку к компоненту XML, такие как <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>, можно вызвать <xref:System.Xml.Linq.XObject.AddAnnotation%2A>метод.</xref:System.Xml.Linq.XObject.AddAnnotation%2A> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Заметки получаются по типу.  
  
 Обратите внимание, что заметки не являются частью набора сведений XML, они не могут быть сериализованы или десериализованы.  
  
## <a name="methods"></a>Методы  
 При работе с заметками можно использовать следующие методы.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A></xref:System.Xml.Linq.XObject.AddAnnotation%2A>|Добавляет объект к списку заметок <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject>|  
|<xref:System.Xml.Linq.XObject.Annotation%2A></xref:System.Xml.Linq.XObject.Annotation%2A>|Возвращает первый объект заметки указанного типа из <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject>|  
|<xref:System.Xml.Linq.XObject.Annotations%2A></xref:System.Xml.Linq.XObject.Annotations%2A>|Получает коллекцию заметок указанного типа для <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject>|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|Удаляет заметки указанного типа из <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject>|  
  
## <a name="see-also"></a>См. также  
 [Дополнительно программированию LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
