---
title: "Общие сведения о LINQ to XML в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "LINQ [Visual Basic], LINQ to XML"
  - "LINQ to XML [Visual Basic], сведения о LINQ to XML"
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Общие сведения о LINQ to XML в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] обеспечивает поддержку [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] с помощью XML\-литералов и свойств осей XML.  Это позволяет использовать знакомый, удобный синтаксис для работы с XML в коде [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]. *XML\-литералы* позволяют включить XML непосредственно в код.  *Свойства осей XML* позволяют получить доступ к дочерним узлам, узлам потомков и атрибутам XML\-литералов.  Дополнительные сведения см. в разделах [Общие сведения об XML\-литералах](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) и [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] — это размещаемый в памяти API\-интерфейс программирования XML, который позволяет воспользоваться преимуществами [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)].  Хотя возможен прямой вызов API [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], только в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] можно объявить XML\-литералы и получить непосредственный доступ к свойствам осей XML.  
  
> [!NOTE]
>  XML\-литералы и свойства осей XML не поддерживаются в коде объявлений на странице ASP.NET.  Чтобы использовать XML\-функции Visual Basic, поместите код на страницу с кодом программной части в приложении ASP.NET.  
  
 ![ссылка на видео](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") Демонстрационные видеоролики по теме см. на веб\-страницах [How Do I Get Started with LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) и [How Do I Create Excel Spreadsheets using LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536).  
  
## Создание XML  
 Создать XML\-деревья в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] можно двумя способами.  Можно объявить XML\-литерал непосредственно в коде или использовать API [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] для создания дерева.  Оба процесса позволяют отразить в коде заключительную структуру XML\-дерева.  Например, с помощью приведенного ниже кода создается XML\-элемент:  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 Дополнительные сведения см. в разделе [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## Доступ и переходы в XML  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет свойства осей XML для доступа к структурам XML и перемещения по ним.  С помощью этих свойств можно получить доступ к XML\-элементам и атрибутам, указывая имена дочерних XML\-элементов.  Можно также явно вызывать методы [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] для выполнения переходов и поиска элементов и атрибутов.  Например, в приведенном ниже коде свойства осей XML используются для ссылки на атрибуты и дочерние элементы XML\-элемента.  В примере кода используется запрос [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] для извлечения дочерних элементов и вывода их в виде XML\-элементов, эффективно выполняя преобразование.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 Дополнительные сведения см. в разделе [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## Пространства имен XML  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] позволяет указать псевдоним для глобального пространства имен XML, используя оператор `Imports`.  В следующем примере показано, как использовать оператор `Imports` для импорта пространства имен XML:  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 Можно использовать псевдоним пространства имен XML при доступе к свойствам осей XML и объявить XML\-литералы для документов и элементов XML.  
  
 Можно извлечь объект <xref:System.Xml.Linq.XNamespace> для конкретного префикса пространства имен, используя [Оператор GetXmlNamespace](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Дополнительные сведения см. в разделе [Оператор Imports \(пространство имен XML\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### Использование пространств имен XML в XML\-литералах  
 В следующем примере показано, как создать объект <xref:System.Xml.Linq.XElement>, в котором используется глобальное пространство имен `ns`:  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 Компилятор [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] переводит XML\-литералы, содержащие псевдонимы пространства имен XML, в эквивалентный код, содержащий XML\-представление для использования пространств имен XML, с атрибутом `xmlns`.  При компиляции код примера из предыдущего раздела формирует по существу тот же самый исполняемый код, как и в следующем примере:  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### Использование пространств имен XML в свойствах осей XML  
 Пространства имен, объявленные в XML\-литералах, недоступны для использования в свойствах осей XML.  Однако глобальные пространства имен могут использоваться со свойствами осей XML.  Используйте двоеточие для отделения префикса пространства имен XML от имени локального элемента.  Например:  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## См. также  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)