---
title: "Обзор пространств имен (LINQ to XML) | Документы Майкрософт"
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
ms.assetid: 16283322-8238-4918-ab11-802ac6748eb7
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 73eb9d0808666238e55abdf53888ec0f9b501fe2
ms.lasthandoff: 03/13/2017

---
# <a name="namespaces-overview-linq-to-xml"></a>Обзор пространств имен (LINQ to XML)
Этот раздел рассказывает о пространствах имен, классе <xref:System.Xml.Linq.XName> и классе <xref:System.Xml.Linq.XNamespace>.  
  
## <a name="xml-names"></a>Имена XML  
 Имена XML часто становятся источником сложности при программировании на XML. Имя XML состоит из пространства имен XML (которое также называется URI-кодом пространства имен XML) и локального имени. Пространство имен XML аналогично пространству имен в программах на основе [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Позволяет уникально квалифицировать имена элементов и атрибутов. Это помогает избежать конфликтов имен в разных частях XML-документа. При задании пространства имен XML можно выбрать локальное имя, которое должно быть уникальным только по значению пространства имен.  
  
 Другим аспектом имен XML являются *префиксы пространств имен* XML. Именно префиксы создают основную сложность в работе с именами XML. Эти префиксы позволяют создавать ярлык пространства имен XML, что делает XML-документ более организованным и понятным. Однако, чтобы префиксы XML несли значение, необходимо, чтобы они были соотнесены с определенным контекстом, а это вносит дополнительную сложность. Например, префикс XML `aw` можно ассоциировать с одним пространством имен XML в одной части XML-дерева и с другим пространством имен XML в другой его части.  
  
 Одним из преимуществ использования [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] в C# является отсутствие необходимости использования префиксов XML. Когда [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] выполняет загрузку или синтаксический анализ XML-документа, каждый префикс XML соотносится с соответствующим пространством имен XML. После этого при работе с документом, в котором используются пространства имен, почти всегда можно оценить пространство имен при помощи URI-кода пространства имен, а не по префиксу. Когда разработчики работают с именами XML на [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], они всегда работают с полностью выраженными именами XML (т. е. пространство имен XML и локальное имя). Однако при необходимости [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] позволяет управлять префиксами пространства имен и обрабатывать их.  
  
 В [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] следующий класс представляет имена XML: <xref:System.Xml.Linq.XName>. Имена XML часто появляются в API [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], и, когда требуется использовать имя XML, обнаруживается параметр <xref:System.Xml.Linq.XName>. При этом работать непосредственно с <xref:System.Xml.Linq.XName> приходится крайне редко. <xref:System.Xml.Linq.XName> содержит неявное преобразование строки.  
  
 Дополнительные сведения см. в разделах <xref:System.Xml.Linq.XNamespace> и <xref:System.Xml.Linq.XName>.  
  
## <a name="see-also"></a>См. также  
 [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
