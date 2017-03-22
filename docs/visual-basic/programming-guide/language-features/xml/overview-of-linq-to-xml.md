---
title: "Общие сведения о LINQ to XML в Visual Basic | Документы Microsoft"
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
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 508d4a97b0636f10607326eb35c4c5d8c7860873
ms.lasthandoff: 03/13/2017

---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Общие сведения о LINQ to XML в Visual Basic
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]обеспечивает поддержку для [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] через XML-литералы и свойства оси XML. Это позволяет использовать знакомый, удобный синтаксис для работы с XML в вашей [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] кода. *XML-литералы* позволяют включать XML непосредственно в коде. *Свойства оси XML* позволяют доступ дочерних узлов, узлов-потомков и атрибутов XML-литерал. Дополнительные сведения см. в разделе [Общие сведения о литералах XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) и [доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]XML в памяти API-Интерфейс позволяет воспользоваться преимуществами программирования [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]. Несмотря на то, что может вызвать [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] интерфейсов API непосредственно, только [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] позволяет объявить XML-литералы и прямой доступ к свойствам осей XML.  
  
> [!NOTE]
>  XML-литералы и свойства оси XML не поддерживаются в декларативном коде страницы ASP.NET. Для использования возможностей XML в Visual Basic, поместите код на странице фонового кода в приложении ASP.NET.  
  
 ![ссылка на видео](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") связанные демонстрационные видеоролики, в разделе [инструкции Приступая к работе с LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) и [инструкции создания таблицы Excel с помощью LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536).  
  
## <a name="creating-xml"></a>Создание XML  
 Существует два способа создания XML-деревьев в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Можно объявить XML-литерал непосредственно в коде или использовать [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] интерфейсы API для создания дерева. Оба процесса позволяют коду окончательная структура XML-дерева. Например в следующем примере кода создается элемент XML:  
  
 [!code-vb[VbXmlSamples&#5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 Дополнительные сведения см. в разделе [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Доступ и переходы в XML  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет свойства осей XML для доступа и перемещения по XML-структур. Эти свойства позволяют получить доступ к XML-элементов и атрибутов, указав имена дочерних элементов XML. Кроме того, можно явно вызывать [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] методов для навигации и поиска элементов и атрибутов. Например в следующем примере кода используются свойства оси XML для ссылки на атрибуты и дочерние элементы элемента XML. В примере кода используется [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запрос для извлечения дочерних элементов и вывода их в виде XML-элементов, эффективно выполняя преобразование.  
  
 [!code-vb[VbXmlSamples №&8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 Дополнительные сведения см. в разделе [доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]позволяет указать псевдоним для глобального пространства имен XML с помощью `Imports` инструкции. В следующем примере показано, как использовать `Imports` инструкцию, чтобы импортировать пространство имен XML:  
  
 [!code-vb[VbXMLSamples&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 При доступе к свойствам осей XML и объявить XML-литералы для документов и элементов XML, можно использовать псевдоним пространства имен XML.  
  
 Вы можете получить <xref:System.Xml.Linq.XNamespace>объект для конкретного префикса пространства имен с помощью [оператор GetXmlNamespace](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).</xref:System.Xml.Linq.XNamespace>  
  
 Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Использование пространств имен XML в XML-литералах  
 Следующий пример демонстрирует создание <xref:System.Xml.Linq.XElement>объекта с помощью глобального пространства имен `ns`:</xref:System.Xml.Linq.XElement>  
  
 [!code-vb[VbXMLSamples&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует XML-литералы, содержащие псевдонимы пространства имен XML, в эквивалентный код, содержащий XML-представление для использования пространств имен XML, с `xmlns` атрибута. При компиляции кода в примере предыдущего раздела формирует по существу тот же исполнимый код в следующем примере:  
  
 [!code-vb[VbXMLSamples&#3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Использование пространств имен XML в свойствах осей XML  
 Пространства имен, объявленные в XML-литералах недоступны для использования в свойствах осей XML. Однако глобальные пространства имен могут использоваться со свойствами оси XML. Используйте двоеточие для отделения префикса пространства имен XML от имени локального элемента. Ниже представлен пример:  
  
 [!code-vb[VbXMLSamples&#4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
