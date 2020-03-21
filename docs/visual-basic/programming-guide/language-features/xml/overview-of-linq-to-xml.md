---
title: Общие сведения о LINQ to XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 0481a140541a7f45c682c5150bc1c3d647de90bd
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266902"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Общие сведения о LINQ to XML в Visual Basic
Visual Basic обеспечивает [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] поддержку через xML буквальные свойства и свойства оси XML. Это позволяет использовать знакомый, удобный синтаксис для работы с XML в вашем визуальном базовом коде. *Буквы XML* позволяют включать XML непосредственно в свой код. *Свойства оси XML* позволяют получить доступ к детским узлам, потомкам и атрибутам буквального XML. Для получения дополнительной информации смотрите [обзор XML Literals](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) и [доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]— это API программирования xML в памяти, разработанный специально для использования в преимуществах Интегрированного запроса (LINЗ). Несмотря на то, что вы можете позвонить на aIS LIN'а напрямую, только Visual Basic позволяет декларировать буквальные буквы XML и напрямую получать доступ к свойствам оси XML.  
  
> [!NOTE]
> Свойства XML-буквели и оси XML не поддерживаются декларативным кодом на странице ASP.NET. Чтобы использовать функции Visual Basic XML, поместите код на страницу с кодом в ASP.NET приложении.  
  
 [Кнопка воспроизведения](./media/overview-of-linq-to-xml/play-video-icon-example.gif) Для соответствующих видео-демонстраций см., [как я могу начать работу с LIN'а к XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) и как я могу создать [таблицы Excel с помощью LIN' к XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).
  
## <a name="creating-xml"></a>Создание XML  
 Существует два способа создания деревьев XML в Visual Basic. Вы можете объявить буквальный XML прямо в коде, или вы можете использовать AIS LIN'а для создания дерева. Оба процесса позволяют коду отражать окончательную структуру дерева XML. Например, следующий пример кода создает элемент XML:  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Для получения дополнительной информации [см.](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
  
## <a name="accessing-and-navigating-xml"></a>Доступ и навигация XML  
 Visual Basic предоставляет свойства оси XML для доступа к структурам XML и навигации. Эти свойства позволяют получить доступ к элементам и атрибутам XML, указав имена элементов элемента XML. Кроме того, можно явно вызвать методы LIN'а для навигации и определения местонахождения элементов и атрибутов. Например, в следующем примере кода используются свойства оси XML для обозначения атрибутов и элементов детской части элемента XML. В примере кода используется запрос LIN'а для извлечения элементов ребенка и вывода их в качестве элементов XML, эффективно выполняя преобразование.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Для получения дополнительной информации смотрите [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 Visual Basic позволяет указать псевдоним в глобальном пространстве имен `Imports` XML с помощью оператора. В следующем примере показано, как использовать выписку `Imports` для импорта пространства имен XML:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 Вы можете использовать псевдоним XML namespace при доступе к свойствам оси XML и декларировать буквы XML для документов и элементов XML.  
  
 Вы можете получить <xref:System.Xml.Linq.XNamespace> объект для конкретного префикса пространства имен с помощью [оператора GetXmlNamespace.](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)  
  
 Для получения дополнительной информации [см.](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Использование именных пространств XML в буквах XML  
 Ниже приводится следующий <xref:System.Xml.Linq.XElement> пример, как создать `ns`объект, который использует глобальное пространство имен:  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 Компилятор Visual Basic переводит буквальные буквы XML, содержащие псевдонимы XML namespace, в эквивалентный код, `xmlns` использующий обозначение XML для использования пространства имен XML с атрибутом. При компилировании код в примере предыдущего раздела создает по существу тот же исполняемый код, что и следующий пример:  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Использование именных пространств XML в свойствах XML Axis  
 XML пространства имен, заявленные в буквальных данных XML, недоступны для использования в свойствах оси XML. Однако глобальные пространства имен могут использоваться с свойствами оси XML. Используйте толстую кишку, чтобы отделить префикс пространства имен XML от локального имени элемента. Ниже приведен пример:  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>См. также раздел

- [Xml](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
