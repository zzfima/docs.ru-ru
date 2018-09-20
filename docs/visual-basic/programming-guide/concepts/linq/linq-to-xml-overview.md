---
title: Обзор LINQ to XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
ms.openlocfilehash: 962fddcfec04259425c1094f07adf0e3966dfab0
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46489215"
---
# <a name="linq-to-xml-overview-visual-basic"></a>Обзор LINQ to XML (Visual Basic)
XML широко используется для форматирования данных в целом ряде контекстов. Примеры XML можно обнаружить в веб-среде, в файлах конфигурации, в файлах Microsoft Office Word и в базах данных.  
  
 В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] реализован современный пересмотренный подход к программированию средствами XML. Кроме того, реализованы встроенные в память возможности модификации документов модели DOM, поддерживаются выражения запросов [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Хотя в синтаксическом отношении эти выражения запросов отличаются от XPath, они предоставляют аналогичные функциональные возможности.  
  
## <a name="linq-to-xml-developers"></a>Разработчики, использующие LINQ to XML  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] предназначен для различных категорий разработчиков. С точки зрения среднестатистического разработчика, заинтересованного в решении той или иной задачи, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] облегчает обработку XML, поскольку дает возможность получить опыт работы с запросами, аналогичный опыту работы с языком SQL. Посвятив совсем немного времени изучению предмета, программисты могут научиться составлять сжатые и мощные запросы на предпочитаемом ими языке программирования.  
  
 Профессиональные разработчики могут с помощью [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] существенно повысить производительность своего труда. Используя [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], они могут сократить объемы необходимого кода и сделать его более выразительным, более компактным и более мощным. Они могут одновременно использовать выражения запросов из нескольких доменов данных.  
  
## <a name="what-is-linq-to-xml"></a>Что такое LINQ to XML?  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] - это оснащенный средствами LINQ и встроенный в память программный интерфейс XML, позволяющий работать с XML-файлами внутри языков программирования [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] подобен модели DOM в том отношении, что загружает XML-документ в память. К такому документу можно направить запрос, его можно изменить, а после изменения его можно сохранить в файле или сериализовать и передать через Интернет. Тем не менее [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] моделью DOM существуют отличия: он предоставляет модель объектов, легкую и простую в работе, и в нем используются преимущества функций языка в Visual Basic.  
  
 Важнейшее достоинство [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] состоит в его интеграции с [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Эта интеграция дает возможность создавать запросы к загруженному в память XML-документу с целью получения коллекций элементов и атрибутов. По своей функциональности (но не по синтаксису) реализованные в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] возможности формирования запросов сопоставимы с возможностями XPath и XQuery. Интеграция [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] в Visual Basic обеспечивается более строгая типизация, компиляции время проверки и улучшенная поддержка отладчика.  
  
 Другим преимуществом [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] является то, что возможность использования результатов запросов в качестве параметров конструкторов объектов <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XAttribute> позволяет применять мощный подход для создания XML-деревьев. Этот подход, известный как *функциональное построение*, дает разработчикам возможность легко преобразовывать деревья XML из одной формы в другую.  
  
 Пусть имеется типичный заказ на покупку в формате XML, как это описано в разделе [Пример XML-файла. Стандартный заказ на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md). С помощью интерфейса [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] можно выполнить следующий запрос для получения значения атрибута артикула для каждого элемента в заказе на покупку:  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 Еще один пример. Пусть требуется сформировать отсортированный в соответствии с номерами деталей список продуктов стоимостью выше 100 долл. Для получения этих сведений можно выполнить следующий запрос:  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 В дополнение к функциям, реализованным в [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] предоставляет усовершенствованный интерфейс программирования XML. Благодаря [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] появляются следующие возможности:  
  
-   Загрузка XML из файлов или из потоков.  
  
-   Сериализация XML в файлы или в потоки.  
  
-   Создание XML-кодов «с чистого листа» с помощью функционального построения.  
  
-   Обращение с запросами к XML с помощью XPath-подобных осей.  
  
-   Манипулирование загруженным в память XML-деревом с помощью таких методов, как <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> и <xref:System.Xml.Linq.XElement.SetValue%2A>.  
  
-   Проверка XML-деревьев с помощью XSD.  
  
-   Использование сочетания этих функций для преобразования XML-деревьев из одной формы в другую.  
  
## <a name="creating-xml-trees"></a>Создание деревьев XML  
 Одним из наиболее важных преимуществ программирования с использованием [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] является простота создания XML-деревьев. Например для создания небольшого дерева XML, можно написать код следующим образом:  
  
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
  
 Компилятор Visual Basic преобразует XML-литералы в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] вызовов методов.  
  
 Дополнительные сведения см. в разделе [Создание деревьев XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq>  
- [Начало работы (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)  
- [Общие сведения о LINQ to XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
