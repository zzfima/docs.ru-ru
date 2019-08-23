---
title: Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: 4833e024fcd352094a2163f11df8572aa4c241f8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944646"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath
В этом примере показано, как выполнить [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] привязку к <xref:System.Windows.Data.XmlDataProvider>данным с помощью.  
  
 В службах базовые данные, к которым можно получить доступ через привязку данных в приложении [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ,могутбытьлюбымдеревомузлов.<xref:System.Windows.Data.XmlDataProvider> Иными словами, <xref:System.Windows.Data.XmlDataProvider> предоставляет удобный способ использовать любое [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] дерево узлов в качестве источника привязки.  
  
## <a name="example"></a>Пример  
 В следующем примере данные внедряются непосредственно как [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] <xref:System.Windows.FrameworkElement.Resources%2A> *остров данных* в разделе. Остров данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] должен быть заключен в теги `<x:XData>` и всегда иметь один корневой узел, который в этом примере является *Инвентаризацией*.  
  
> [!NOTE]
> Корневой узел данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] имеет атрибут **xmlns**, который задает для пространства имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] пустую строку. Это обязательное требование для выполнения запросов XPath к островам данных, встроенным в страницу [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. В этом случае [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], и, поэтому остров данных наследует <xref:System.Windows> пространство имен. Поэтому необходимо задать пустое пространство имен, чтобы запросы <xref:System.Windows> XPath не задаются пространством имен, что приведет к невозможности направить запросы.  
  
 [!code-xaml[XMLDataSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Как показано в следующем примере, для создания такого же объявления привязки в синтаксисе атрибутов необходимо экранировать специальные символы правильно. Дополнительные сведения см. в разделе [Сущности знаков XML и XAML](../../xaml-services/xml-character-entities-and-xaml.md).  
  
 При выполнении этого примера будутпоказаныследующиеэлементы.<xref:System.Windows.Controls.ListBox> Это *заголовки* всех элементов в группе *Книги* со значением *Stock*, равным *out*, или значением *Number*, равным 3 или больше или равным 8. Обратите внимание, что элементы *компакт-диска* не возвращаются, <xref:System.Windows.Data.XmlDataProvider.XPath%2A> поскольку <xref:System.Windows.Data.XmlDataProvider> значение, установленное на, указывает, что должны быть предоставлены только элементы *Books* (по сути, установка фильтра).  
  
 ![Снимок экрана примера XPath, показывающий название четырех книг.](./media/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries/xpath-example-listbox-details.png)  
  
 В этом примере отображаются названия книг, <xref:System.Windows.Data.Binding.XPath%2A> так как <xref:System.Windows.Controls.TextBlock> для привязки в <xref:System.Windows.DataTemplate> задано значение*Title*. Если требуется отобразить значение атрибута, например *ISBN*, это <xref:System.Windows.Data.Binding.XPath%2A> значение можно задать равным "`@ISBN`".  
  
 Свойства **XPath** в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обрабатываются методом XmlNode.SelectNodes. Можно изменить запросы **XPath** для получения других результатов. Ниже приведены некоторые примеры для <xref:System.Windows.Data.Binding.XPath%2A> запроса, привязанного <xref:System.Windows.Controls.ListBox> к предыдущему примеру.  
  
- `XPath="Book[1]"` возвращает первый элемент книги (XML в действии). Обратите внимание, что индексы **XPath** основаны на 1, а не на 0.  
  
- `XPath="Book[@*]"` возвращает все элементы книги с любыми атрибутами.  
  
- `XPath="Book[last()-1]"` возвращает второй элемент последней книги ("Знакомство с Microsoft .NET").  
  
- `XPath="*[position()>3]"` возвращает все элементы книги, за исключением первых трех.  
  
 При выполнении запроса **XPath** он возвращает <xref:System.Xml.XmlNode> или список XMLNodes. <xref:System.Xml.XmlNode>— Это объект среды CLR, который означает, что можно использовать <xref:System.Windows.Data.Binding.Path%2A> свойство для привязки к свойствам среды CLR. Вернемся к нашему предыдущему примеру еще раз. Если остальная часть примера остается неизменной и вы изменяете <xref:System.Windows.Controls.TextBlock> привязку на следующую, вы увидите имена возвращенных XMLNodes <xref:System.Windows.Controls.ListBox>в. В этом случае все возвращаемые узлы называются "*книги*".  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 В некоторых приложениях внедрение [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] в качестве острова данных в источник [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы может быть нецелесообразным, поскольку точное содержимое данных должно быть известно во время компиляции. Поэтому также поддерживается получение данных из внешнего [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] файла, как показано в следующем примере:  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Если данные находятся в удаленном [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] файле, необходимо определить доступ к данным, <xref:System.Windows.Data.XmlDataProvider.Source%2A> назначив соответствующий [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] атрибуту следующие значения: [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.ObjectDataProvider>
- [Привязка к XDocument, XElement или LINQ для результатов запросов XML](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)
- [Использование шаблона "Основной/подробности" с иерархическими XML-данными](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Общие сведения об источниках привязки](binding-sources-overview.md)
- [Общие сведения о привязке данных](data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
