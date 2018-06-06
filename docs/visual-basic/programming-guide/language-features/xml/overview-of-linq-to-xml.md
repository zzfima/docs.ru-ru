---
title: Общие сведения о LINQ to XML в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 65df48112834be04dc8d3b62b8b163316b06c4a6
ms.sourcegitcommit: d8bf4976eafe3289275be3811e7cb721bfff7e1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753413"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Общие сведения о LINQ to XML в Visual Basic
Visual Basic предоставляет поддержку для [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] через литералы XML и свойства оси XML. Это позволяет использовать знакомый, удобный синтаксис для работы с XML в коде Visual Basic. *XML-литералы* позволяют включать XML непосредственно в коде. *Свойства оси XML* позволяют доступа к дочерним узлам, узлов-потомков и атрибуты XML-литерала. Дополнительные сведения см. в разделе [Общие сведения о литералах XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) и [доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] является API-Интерфейс позволяет воспользоваться преимуществами программирования XML в памяти [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Несмотря на то, что вы можете вызвать [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] API-интерфейсов напрямую, только Visual Basic можно объявить XML-литералы и прямой доступ к свойства оси XML.  
  
> [!NOTE]
>  Литералы XML и свойства оси XML не поддерживаются в коде объявлений на странице ASP.NET. Для использования возможностей XML в Visual Basic поместите код на страница с выделенным кодом в приложении ASP.NET.  
  
 ![ссылка на видео](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") связанные демонстрационные видеоролики, в разделе [инструкции начать работу с LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) и [как мне создать электронную таблицу Excel с помощью LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).  
  
## <a name="creating-xml"></a>Создание XML  
 Существует два способа создания XML-деревьев в Visual Basic. Можно объявить XML-литерал непосредственно в коде, или можно использовать [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] API-интерфейсы для создания дерева. Оба процесса позволяют код с учетом окончательной структуры XML-дерева. Например в следующем примере кода создается элемент XML:  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 Дополнительные сведения см. в разделе [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Доступ и переходы в XML  
 Visual Basic предоставляет свойства оси XML для доступа и перемещения по XML-структур. Эти свойства позволяют получить доступ к XML-элементов и атрибутов, указав имена XML дочерних элементов. Кроме того, можно явно вызывать [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] методы для навигации и поиска элементов и атрибутов. Например в следующем примере кода используются свойства оси XML для ссылки на атрибуты и дочерние элементы элемента XML. В примере кода используется [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запрос для получения дочерних элементов и вывода их в виде XML-элементов, эффективно выполняя преобразование.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 Дополнительные сведения см. в разделе [доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 Visual Basic позволяет указать псевдоним для глобального пространства имен XML с помощью `Imports` инструкции. В следующем примере показано, как использовать `Imports` инструкцию, чтобы импортировать пространство имен XML:  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 При доступе к свойствам оси XML и объявить XML-литералы для XML-документов и элементы можно использовать псевдоним пространства имен XML.  
  
 Вы можете получить <xref:System.Xml.Linq.XNamespace> объект для конкретного префикса пространства имен с помощью [оператор GetXmlNamespace](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Использование пространств имен XML в XML-литералах  
 В следующем примере показано, как создать <xref:System.Xml.Linq.XElement> объект, который использует глобального пространства имен `ns`:  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 Компилятор Visual Basic преобразует XML-литералы, содержащие псевдонимы пространства имен XML, в эквивалентный код, содержащий XML-представление для использования пространств имен XML, с `xmlns` атрибута. При компиляции кода в примере в предыдущем разделе выводятся по существу же исполняемый код в следующем примере:  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Использование пространств имен XML в свойства оси XML  
 Пространства имен XML, объявленные в XML-литералах для использования в свойства оси XML недоступны. Тем не менее глобальные пространства имен можно использовать с свойства оси XML. Используйте точкой с запятой для разделения префикс пространства имен XML от имени локального элемента. Ниже представлен пример.  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [Работа с XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
