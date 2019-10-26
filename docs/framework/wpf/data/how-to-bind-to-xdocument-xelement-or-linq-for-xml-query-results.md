---
title: Практическое руководство. Привязка к XDocument, XElement или LINQ для результатов запросов XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 070f67f30613d4522a48e08fd1c208fbe5887525
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920115"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a>Практическое руководство. Привязка к XDocument, XElement или LINQ для результатов запросов XML

В этом примере показано, как привязать данные XML к <xref:System.Windows.Controls.ItemsControl> с помощью <xref:System.Xml.Linq.XDocument>.

## <a name="example"></a>Пример

В следующем коде XAML определяется <xref:System.Windows.Controls.ItemsControl> и включается шаблон данных для данных типа `Planet` в `http://planetsNS` пространстве имен XML. Тип данных XML, заполняющий пространство имен, должен включать пространство имен, заключенное в фигурные скобки, или (при отображении вместе с расширением разметки XAML) предшествовать пространству имен с escape-последовательностью в фигурных скобках. Этот код привязывается к динамическим свойствам, которые соответствуют методам <xref:System.Xml.Linq.XContainer.Element%2A> и <xref:System.Xml.Linq.XElement.Attribute%2A> класса <xref:System.Xml.Linq.XElement>. Динамические свойства включают XAML для привязки к динамическим свойствам, предоставляющим доступ к именам методов. Дополнительные сведения см. в разделе [LINQ to XML динамические свойства](linq-to-xml-dynamic-properties.md). Обратите внимание на то, что объявление пространства имен по умолчанию для XML не применяется к именам атрибутов.

[!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]

Следующий C# код вызывает<xref:System.Xml.Linq.XDocument.Load%2A>и задает для контекста данных панели стека все подэлементы элемента с именем`SolarSystemPlanets`в пространстве имен XML`http://planetsNS`.

[!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
[!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]

XML-данные можно хранить в виде ресурса XAML с помощью <xref:System.Windows.Data.ObjectDataProvider>. Полный пример см. в разделе [Исходный код L2DBForm. XAML](l2dbform-xaml-source-code.md). В следующем примере показано, каким образом код может задавать контекст данных для ресурса объекта.

[!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
[!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]

Динамические свойства, которые сопоставляются с <xref:System.Xml.Linq.XContainer.Element%2A> и <xref:System.Xml.Linq.XElement.Attribute%2A> обеспечивают гибкость в XAML. Код также можно привязать к результатам запроса LINQ для XML. В этом примере он привязывается к результатам запроса, направленного значением элемента.

[!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
[!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]

## <a name="see-also"></a>См. также

- [Общие сведения об источниках привязки](binding-sources-overview.md)
- [Общие сведения о привязке данных WPF с помощью LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Привязка данных WPF с использованием примера LINQ to XML](linq-to-xml-data-binding-sample.md)
- [Динамические свойства LINQ to XML](linq-to-xml-dynamic-properties.md)
