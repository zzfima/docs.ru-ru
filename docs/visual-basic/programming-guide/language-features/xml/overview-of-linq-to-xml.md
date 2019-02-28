---
title: Общие сведения о LINQ to XML в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: d2f9ca8fe453f120dd52f4c4b20e75b9f933b251
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974124"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Общие сведения о LINQ to XML в Visual Basic
Visual Basic предоставляет поддержку для [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] через литералы XML и свойства оси XML. Это позволяет использовать знакомый и удобный синтаксис для работы с XML в коде Visual Basic. *XML-литералов* позволяют включать XML непосредственно в коде. *Свойства оси XML* позволяют осуществлять доступ дочерних узлов, узлов-потомков и атрибуты XML-литерала. Дополнительные сведения см. в разделе [Общие сведения о литералах XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) и [доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API-Интерфейс специально для того, чтобы воспользоваться преимуществами программирования XML в памяти [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Несмотря на то, что вы можете вызвать [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] напрямую интерфейсы API, только Visual Basic позволяет объявить XML-литералы и напрямую обращаться к свойства оси XML.  
  
> [!NOTE]
>  Литералы XML и свойства оси XML не поддерживаются в декларативном коде страницы ASP.NET. Для использования функций XML в Visual Basic поместите код в страницы с выделенным кодом в приложении ASP.NET.  
  
 ![ссылка на видео](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") связанные демонстрационные видеоролики см. в разделе [инструкции начать работу с LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) и [инструкции создания таблицы Excel, с помощью LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).  
  
## <a name="creating-xml"></a>Создание XML  
 Существует два способа создания деревьев XML в Visual Basic. Можно объявить XML-литерал непосредственно в коде, или воспользоваться [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] API-интерфейсы для создания дерева. Оба процесса включить код в соответствии с окончательная структура XML-дерева. Например в следующем примере кода создается элемент XML:  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Дополнительные сведения см. в разделе [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Доступ и переходы в XML  
 Visual Basic предоставляет свойства оси XML для доступа и перемещения по XML-структур. Эти свойства позволяют получить доступ к XML-элементов и атрибутов, указав имена дочерних элементов XML. Кроме того, можно явно вызывать [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] методы для навигации и поиска элементов и атрибутов. Например в следующем примере кода используются свойства оси XML для ссылки на атрибуты и дочерние элементы элемента XML. В примере кода используется [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запрос для получения дочерних элементов и вывода их в виде XML-элементов, фактически выполняет преобразование.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Дополнительные сведения см. в разделе [доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 Visual Basic позволяет указать псевдоним для глобального пространства имен XML с помощью `Imports` инструкции. В следующем примере показано, как использовать `Imports` инструкцию, чтобы импортировать пространство имен XML:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 При доступе к свойствам оси XML и объявить литералы XML для XML-документов и элементов можно использовать псевдоним пространства имен XML.  
  
 Вы можете получить <xref:System.Xml.Linq.XNamespace> объект для определенного префикса с помощью [оператор GetXmlNamespace](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Использование пространств имен XML в XML-литералах  
 В следующем примере показано, как создать <xref:System.Xml.Linq.XElement> объект, который использует глобальное пространство имен `ns`:  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 Компилятор Visual Basic преобразует XML-литералы, содержащие псевдонимы пространств имен XML, в эквивалентный код, содержащий XML-представление для использования пространства имен XML, с помощью `xmlns` атрибута. При компиляции кода в примере в предыдущем разделе создается по сути тот же исполнимый код в приведенном ниже примере:  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Использование пространств имен XML в свойства оси XML  
 Пространства имен XML, объявленные в XML-литералах для использования в свойства оси XML недоступны. Тем не менее глобальные пространства имен можно использовать со свойствами оси XML. Для разделения префикс пространства имен XML от имени локального элемента, используйте двоеточия. Ниже представлен пример.  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>См. также
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [Работа с XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
