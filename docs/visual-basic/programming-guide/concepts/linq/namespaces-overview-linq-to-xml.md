---
title: "Обзор пространств имен (LINQ to XML) | Документы Microsoft"
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
ms.assetid: b8eb31fa-4b26-4acf-8050-6e705687f458
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cec2efd31c96af17ad717abaa8f4359210e99a78
ms.lasthandoff: 03/13/2017

---
# <a name="namespaces-overview-linq-to-xml"></a>Обзор пространств имен (LINQ to XML)
Этот раздел знакомит с пространствами имен, <xref:System.Xml.Linq.XName>класс и <xref:System.Xml.Linq.XNamespace>класса.</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName>  
  
## <a name="xml-names"></a>Имена XML  
 Имена XML часто становятся источником сложности при программировании на XML. Имя XML состоит из пространства имен XML (которое также называется URI-кодом пространства имен XML) и локального имени. Пространство имен XML аналогично пространству имен в программах на основе [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Позволяет уникально квалифицировать имена элементов и атрибутов. Это помогает избежать конфликтов имен в разных частях XML-документа. При задании пространства имен XML можно выбрать локальное имя, которое должно быть уникальным только по значению пространства имен.  
  
 Другим аспектом имен XML являются XML *префиксы пространства имен*. Именно префиксы создают основную сложность в работе с именами XML. Эти префиксы позволяют создавать ярлык пространства имен XML, что делает XML-документ более организованным и понятным. Однако, чтобы префиксы XML несли значение, необходимо, чтобы они были соотнесены с определенным контекстом, а это вносит дополнительную сложность. Например, префикс XML `aw` можно ассоциировать с одним пространством имен XML в одной части XML-дерева и с другим пространством имен XML в другой его части.  
  
 При использовании [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] с Visual Basic и XML-литералы, необходимо использовать префиксы пространств имен при работе с документами в пространствах имен.  
  
 В [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> — класс, который представляет имена XML Имена XML часто появляются [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API, и когда требуется имя XML, вы увидите <xref:System.Xml.Linq.XName>параметр.</xref:System.Xml.Linq.XName> Тем не менее редко работать непосредственно с <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> <xref:System.Xml.Linq.XName>содержит неявное преобразование из строки.</xref:System.Xml.Linq.XName>  
  
 Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XNamespace>и <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace>  
  
## <a name="see-also"></a>См. также  
 [Работа с пространствами имен XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
