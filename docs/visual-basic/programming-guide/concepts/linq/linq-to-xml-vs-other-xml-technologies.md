---
title: "LINQ to XML или Другие XML Technologies2 | Документы Microsoft"
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
ms.assetid: 72ce3a82-ffc6-488c-98e7-b9b40f3591ec
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
ms.openlocfilehash: 0254788fb9efa018e735a57990144c6b176d30d6
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-vs-other-xml-technologies"></a>LINQ to XML или Другие XML-технологии
В этом разделе сравнивается [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] со следующими технологиями XML: <xref:System.Xml.XmlReader>, XSLT, MSXML и XmlLite.</xref:System.Xml.XmlReader> Данные сведения могут помочь в выборе технологии.  
  
 Сравнение [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] для объекта модели DOM документа, в разделе [LINQ to XML или. Модель DOM (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-dom.md).  
  
## <a name="linq-to-xml-vs-xmlreader"></a>LINQ to XML или XmlReader  
 <xref:System.Xml.XmlReader>Представляет средство синтаксического анализа быстрое однопроходный, без кэширования.</xref:System.Xml.XmlReader>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]реализована на основе <xref:System.Xml.XmlReader>, и тесно интегрированы.</xref:System.Xml.XmlReader> Однако можно также использовать <xref:System.Xml.XmlReader>сама по себе.</xref:System.Xml.XmlReader>  
  
 Предположим, что необходимо создать веб-службу, которая будет выполнять в каждую секунду анализ сотен XML-документов, имеющих одинаковую структуру, так что для анализа XML потребуется записать лишь одну реализацию кода. В этом случае вы, вероятно, хотите использовать <xref:System.Xml.XmlReader>сама по себе.</xref:System.Xml.XmlReader>  
  
 Напротив, если вы создаете систему, которая анализирует множества небольших XML-документов, и каждый из них отличается, следует воспользоваться средствами повышения производительности, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] предоставляет.  
  
## <a name="linq-to-xml-vs-xslt"></a>LINQ to XML или XSLT  
 Оба [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] и язык XSLT предоставляют широкие возможности по преобразованию документа XML. XSLT представляет собой декларативный подход, основанный на правилах. Опытные XSLT-программисты записывают код XSLT в стиле функционального программирования, в основе которого лежит подход без сохранения состояния. Преобразования могут быть написаны с использованием чистых функций, реализованных без побочных эффектов. С этим подходом, основанным на правилах или функциональным, незнакомы многие разработчики, и для его изучения потребуется много времени и усилий.  
  
 Технология XSLT может стать основой весьма продуктивной системы, позволяющей создавать высокопроизводительные приложения. Например, несколько крупных компаний, работающих в сфере веб-технологий, используют XSLT для создания HTML-кода из XML-кода, полученного из различных хранилищ данных. Управляемое ядро XSLT компилирует XSLT в код CLR и в некоторых сценариях работает даже лучше собственного ядра XSLT.  
  
 Однако многие разработчики, переходя к использованию языка XSLT, теряют такое свое преимущество, как знание языков C# и Visual Basic. Разработчики вынуждены использовать при написании кода совсем другой и сложный язык программирования. Использование двух не связанных между собой систем разработки, таких как C# (или Visual Basic) и XSLT, приводит к появлению программных систем, которые сложнее разрабатывать и поддерживать.  
  
 После успешного овладения [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] выражений, запросов [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] преобразования — это мощная технология, которая проста в использовании. По сути, процесс формирования XML-документ с помощью функционального построения извлечения данных из различных источников, создав <xref:System.Xml.Linq.XElement>динамически объектов и сборки всех элементов в новое XML-дерево.</xref:System.Xml.Linq.XElement> Это преобразование позволяет создать совершенно новый документ. Создание преобразований в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] происходит относительно легко и интуитивно понятно, а конечный код легко читается. Это снижает расходы на разработку и обслуживание.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] не предназначен для замены XSLT. XSLT все еще является лучшим средством для сложных XML-преобразований, в основе которых лежат документы, особенно если структура документа определена не полностью.  
  
 Преимущество XSLT заключается в том, что эта технология определена стандартом консорциума W3C. Поэтому если должно быть учтено требование по использованию только тех технологий, которые являются стандартными, то XSLT может оказаться более подходящей.  
  
 Код XSLT представляет собой код XML, поэтому с ним можно проводить манипуляции программным путем.  
  
## <a name="linq-to-xml-vs-msxml"></a>LINQ to XML или MSXML  
 MSXML - это основанная на модели COM технология обработки XML, включенная в ОС Microsoft Windows. MSXML обеспечивает собственную реализацию DOM с поддержкой XPath и XSLT. Она также содержит средство синтаксического анализа SAX2, основанное на событиях, без кэширования.  
  
 MSXML обеспечивает высокую производительность, по умолчанию обеспечивает безопасность в большинстве сценариев и может использоваться в обозревателе Internet Explorer для выполнения обработки XML на стороне клиента в приложениях AJAX. Возможность применения технологии MSXML предусмотрена в любом языке программирования, поддерживающем COM, включая C++, JavaScript и [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 6.0.  
  
 Не рекомендуется использовать MSXML в управляемом коде, основанном на среде CLR.  
  
## <a name="linq-to-xml-vs-xmllite"></a>LINQ to XML или XmlLite  
 XmlLite представляет собой запрашивающее средство синтаксического анализа с последовательным доступом, без кэширования. В основном разработчики используют XmlLite с языком C++. Не рекомендуется использовать XmlLite с управляемым кодом.  
  
 Основным преимуществом такого средства синтаксического анализа XML, как XmlLite, является его простота, быстродействие и безопасность в большинстве сценариев. Его контактная зона, подверженная угрозам, очень мала. Если требуется проведение анализа документов, не заслуживающих доверия, и необходимо защититься от атак типа «отказ в обслуживании» или раскрытия данных, то XmlLite является хорошим выбором.  
  
 XmlLite не поддерживает интеграцию с [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]. Он не приводит повышению производительности программиста, побудительных мотивов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Начало работы (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
