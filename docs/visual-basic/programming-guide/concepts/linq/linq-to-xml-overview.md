---
title: "LINQ to XML Обзор (Visual Basic) | Документы Microsoft"
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
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
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
ms.openlocfilehash: 05d756bc5cd7655a5220c3564d120f90a59ce901
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-overview-visual-basic"></a>LINQ to XML Обзор (Visual Basic)
XML широко используется для форматирования данных в целом ряде контекстов. Примеры XML можно обнаружить в веб-среде, в файлах конфигурации, в файлах Microsoft Office Word и в базах данных.  
  
 В [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] реализован современный пересмотренный подход к программированию средствами XML. Кроме того, реализованы встроенные в память возможности модификации документов модели DOM, поддерживаются выражения запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. Хотя в синтаксическом отношении эти выражения запросов отличаются от XPath, они предоставляют аналогичные функциональные возможности.  
  
## <a name="linq-to-xml-developers"></a>Разработчики, использующие LINQ to XML  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] предназначен для различных категорий разработчиков. С точки зрения среднестатистического разработчика, заинтересованного в решении той или иной задачи, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] облегчает обработку XML, поскольку дает возможность получить опыт работы с запросами, аналогичный опыту работы с языком SQL. Посвятив совсем немного времени изучению предмета, программисты могут научиться составлять сжатые и мощные запросы на предпочитаемом ими языке программирования.  
  
 Профессиональные разработчики могут с помощью [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] существенно повысить производительность своего труда. Используя [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], они могут сократить объемы необходимого кода и сделать его более выразительным, более компактным и более мощным. Они могут одновременно использовать выражения запросов из нескольких доменов данных.  
  
## <a name="what-is-linq-to-xml"></a>Что такое LINQ to XML?  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] - это оснащенный средствами LINQ и встроенный в память программный интерфейс XML, позволяющий работать с XML-файлами внутри языков программирования [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]действует как объектной модели документов (DOM), что загружает XML-документа в памяти. К такому документу можно направить запрос, его можно изменить, а после изменения его можно сохранить в файле или сериализовать и передать через Интернет. Однако [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] отличается от модели DOM: он предоставляет модель объектов легкую и простую в работе, и в Visual Basic, используются преимущества функций языка.  
  
 Важнейшее достоинство [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] состоит в его интеграции с [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]. Эта интеграция дает возможность создавать запросы к загруженному в память XML-документу с целью получения коллекций элементов и атрибутов. По своей функциональности (но не по синтаксису) реализованные в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] возможности формирования запросов сопоставимы с возможностями XPath и XQuery. Интеграция [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] в Visual Basic обеспечивается более строгая типизация, компиляции время проверки и улучшенная поддержка отладчика.  
  
 Другим преимуществом [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] является возможность использования результатов запроса в качестве параметров <xref:System.Xml.Linq.XElement>и <xref:System.Xml.Linq.XAttribute>Конструкторы объектов позволяет применять мощный подход к созданию XML-деревьев.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Этот подход, именуемый *функциональное построение*, дает разработчикам возможность легко преобразовывать XML-деревья из одной формы в другую.  
  
 Например, может потребоваться типичный XML заказа на покупку, как описано в [пример XML-файла: типичный заказ на покупку (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348). С помощью интерфейса [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] можно выполнить следующий запрос для получения значения атрибута артикула для каждого элемента в заказе на покупку:  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 Еще один пример. Пусть требуется сформировать отсортированный в соответствии с номерами деталей список продуктов стоимостью выше&100; долл. Для получения этих сведений можно выполнить следующий запрос:  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 Помимо этих [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] возможности, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] предоставляет усовершенствованный интерфейс программирования XML. Благодаря [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] появляются следующие возможности:  
  
-   Загрузка XML из файлов или из потоков.  
  
-   Сериализация XML в файлы или в потоки.  
  
-   Создание XML-кодов «с чистого листа» с помощью функционального построения.  
  
-   Обращение с запросами к XML с помощью XPath-подобных осей.  
  
-   Управлять XML-дерева в памяти с помощью методов, таких как <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>и <xref:System.Xml.Linq.XElement.SetValue%2A>.</xref:System.Xml.Linq.XElement.SetValue%2A> </xref:System.Xml.Linq.XNode.ReplaceWith%2A> </xref:System.Xml.Linq.XNode.Remove%2A> </xref:System.Xml.Linq.XContainer.Add%2A>  
  
-   Проверка XML-деревьев с помощью XSD.  
  
-   Использование сочетания этих функций для преобразования XML-деревьев из одной формы в другую.  
  
## <a name="creating-xml-trees"></a>Создание деревьев XML  
 Одним из наиболее важных преимуществ программирования с использованием [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] является простота создания XML-деревьев. Например для создания небольшого XML-дерева, можно написать код следующим образом:  
  
```vb  
Dim contacts = _  
<Contacts>  
    <Contact>  
        <Name>Patrick Hines</Name>  
        <Phone Type="Home">206-555-0144</Phone>  
        <Phone Type="Work">425-555-0145</Phone>  
        <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
        </Address>  
    </Contact>  
</Contacts>  
```  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует XML-литералы в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] вызовов методов.  
  
 Дополнительные сведения см. в разделе [Создание XML-деревьев (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq>   
 [Приступая к работе (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)   
 [Общие сведения о LINQ to XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
