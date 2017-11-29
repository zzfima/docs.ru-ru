---
title: "Практическое руководство. Привязка к данным xml с помощью XMLDataProvider и запросов XPath"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06a515b266b2787c24e95b461075d9059e4311dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>Практическое руководство. Привязка к данным xml с помощью XMLDataProvider и запросов XPath
В этом примере показано, как выполнить привязку к [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] данных с помощью <xref:System.Windows.Data.XmlDataProvider>.  
  
 С <xref:System.Windows.Data.XmlDataProvider>, базовым данным можно получить с помощью привязки данных в приложении может быть любым деревом [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] узлов. Другими словами <xref:System.Windows.Data.XmlDataProvider> предоставляет удобный способ использования любого дерева [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] узлов в качестве источника привязки.  
  
## <a name="example"></a>Пример  
 В следующем примере данные внедряются непосредственно как [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] *острова данных* в <xref:System.Windows.FrameworkElement.Resources%2A> раздела. Остров данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] должен быть заключен в теги `<x:XData>` и всегда иметь один корневой узел, который в этом примере является *Инвентаризацией*.  
  
> [!NOTE]
>  Корневой узел данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] имеет атрибут **xmlns**, который задает для пространства имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] пустую строку. Это обязательное требование для выполнения запросов XPath к островам данных, встроенным в страницу [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. В данном случае [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], и таким образом, остров данных наследует <xref:System.Windows> пространства имен. По этой причине необходимо задать пространство имен пустым, чтобы запретить запросы XPath с указанием <xref:System.Windows> пространства имен, которое будет, которые неправильно указывают запросы.  
  
 [!code-xaml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Как показано в следующем примере, для создания такого же объявления привязки в синтаксисе атрибутов необходимо экранировать специальные символы правильно. Дополнительные сведения см. в разделе [Сущности знаков XML и XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 <xref:System.Windows.Controls.ListBox> Будут показаны следующие элементы, при запуске этого примера. Это *заголовки* всех элементов в группе *Книги* со значением *Stock*, равным *out*, или значением *Number*, равным 3 или больше или равным 8. Обратите внимание, что не *CD* возвращаются элементы, так как <xref:System.Windows.Data.XmlDataProvider.XPath%2A> заданное <xref:System.Windows.Data.XmlDataProvider> указывает, что только *электронной* элементы должны быть представлены (фактически Установка фильтра).  
  
 ![XPath Example](../../../../docs/framework/wpf/data/media/xpathexample.PNG "XPathExample")  
  
 В этом примере названия книг отображаются, поскольку <xref:System.Windows.Data.Binding.XPath%2A> из <xref:System.Windows.Controls.TextBlock> привязки в <xref:System.Windows.DataTemplate> имеет значение «*заголовок*». Следует ли отображать значение атрибута, например *ISBN*, следует установить для <xref:System.Windows.Data.Binding.XPath%2A> значение «`@ISBN`».  
  
 Свойства **XPath** в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обрабатываются методом XmlNode.SelectNodes. Можно изменить запросы **XPath** для получения других результатов. Вот несколько примеров для <xref:System.Windows.Data.Binding.XPath%2A> запрос на ее границы <xref:System.Windows.Controls.ListBox> из предыдущего примера:  
  
-   `XPath="Book[1]"` возвращает первый элемент книги (XML в действии). Обратите внимание, что индексы **XPath** основаны на 1, а не на 0.  
  
-   `XPath="Book[@*]"` возвращает все элементы книги с любыми атрибутами.  
  
-   `XPath="Book[last()-1]"` возвращает второй элемент последней книги ("Знакомство с Microsoft .NET").  
  
-   `XPath="*[position()>3]"` возвращает все элементы книги, за исключением первых трех.  
  
 При запуске **XPath** запрос, он возвращает <xref:System.Xml.XmlNode> или список XmlNodes. <xref:System.Xml.XmlNode>— [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] объекта, то есть, можно использовать <xref:System.Windows.Data.Binding.Path%2A> свойство для привязки [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] свойства. Вернемся к нашему предыдущему примеру еще раз. Если остальную часть примера остается неизменным, и изменить <xref:System.Windows.Controls.TextBlock> привязки приведенному ниже, будут отображаться имена возвращенных XMLNodes в <xref:System.Windows.Controls.ListBox>. В этом случае все возвращаемые узлы называются "*книги*".  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 В некоторых приложениях внедрение [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] в качестве острова данных в источник [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы может быть нецелесообразным, поскольку точное содержимое данных должно быть известно во время компиляции. Поэтому также поддерживается получение данных из внешнего [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] файла, как показано в следующем примере:  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Если [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данные находятся в удаленном [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] файл, вы бы определяют права доступа к данных путем назначения соответствующей [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] для <xref:System.Windows.Data.XmlDataProvider.Source%2A> атрибута следующим образом:  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Data.ObjectDataProvider>  
 [Привязка к XDocument, XElement или LINQ для результатов запросов XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)  
 [Использование шаблона "Основной/подробности" с иерархическими XML-данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
