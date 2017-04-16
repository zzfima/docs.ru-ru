---
title: "Практическое руководство. Привязка к данным xml с помощью XMLDataProvider и запросов XPath | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "привязка, к XML-данным с помощью запросов XmlDataProvider"
  - "привязка данных, привязка к XML-данным с помощью запросов XmlDataProvider"
  - "XmlDataProvider, привязка к XML-данным"
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Практическое руководство. Привязка к данным xml с помощью XMLDataProvider и запросов XPath
В этом примере показана привязка к данным [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] с помощью <xref:System.Windows.Data.XmlDataProvider>.  
  
 С помощью <xref:System.Windows.Data.XmlDataProvider> к базовым данным можно обращаться через привязку данных в приложении и они могут являться любым деревом узлов [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  Другими словами, <xref:System.Windows.Data.XmlDataProvider> обеспечивает удобный способ использования любого дерева узлов [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] в качестве [источника привязки](GTMT).  
  
## Пример  
 В следующем примере данные внедряются непосредственно как [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] *остров данных* внутри блока <xref:System.Windows.FrameworkElement.Resources%2A>.  Остров данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] должен быть заключен в теги `<x:XData>` и всегда иметь один корневой узел, которым в этом примере является узел *Данные инвентаризации*.  
  
> [!NOTE]
>  Корневой узел данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] имеет атрибут **xmlns**, который устанавливает пространство имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] в значение пустой строки.  Это требование необходимо для выполнения запросов XPath к островам данных, встроенным в страницу [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  В данном случае [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(и, соответственно, остров данных\) наследует пространство имен <xref:System.Windows>.  Поэтому необходимо задать пространство имен пустым, чтобы запретить определение имен в запросах XPath пространством имен <xref:System.Windows>, что могло бы привести к неправильному направлению запросов.  
  
 [!code-xml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Как показано в этом примере, для создания такого же объявления привязки в синтаксисе атрибутов необходимо с осторожностью использовать специальные символы.  Дополнительные сведения см. в разделе [Сущности знаков XML и XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 При выполнении этого примера в <xref:System.Windows.Controls.ListBox> будут показаны следующие элементы.  Таким элементом является *Заголовок* каждого элемента в *Книгах* либо со значением *Запас* — "*out*", либо со значением *Номер* — 3 или больше либо равно 8.  Обратите внимание, что ни один из элементов *Компакт\-диск* не возвращается, так как значение <xref:System.Windows.Data.XmlDataProvider.XPath%2A>, заданное для <xref:System.Windows.Data.XmlDataProvider>, указывает, что следует предоставлять только элементы *Книги* \(то же самое, что и установка фильтра\).  
  
 ![Пример XPath](../../../../docs/framework/wpf/data/media/xpathexample.png "XPathExample")  
  
 В этом примере названия книг отображаются, поскольку <xref:System.Windows.Data.Binding.XPath%2A> у <xref:System.Windows.Controls.TextBlock> выполняющий привязку в <xref:System.Windows.DataTemplate> установлен в значение "*Заголовки*".  Если необходимо вывести значение атрибута, например *ISBN*, следует установить для <xref:System.Windows.Data.Binding.XPath%2A> значение "`@ISBN`".  
  
 Свойства **XPath** в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обрабатываются методом XmlNode.SelectNodes.  Для получения различных результатов можно изменять запросы **XPath**.  Ниже приводятся некоторые примеры для запроса <xref:System.Windows.Data.Binding.XPath%2A> к привязанному <xref:System.Windows.Controls.ListBox> из предыдущего примера:  
  
-   `XPath="Book[1]"` вернет первый элемент "Книги" \("XML в действии"\).  Обратите внимание, что индексы **XPath** начинаются с 1, а не 0.  
  
-   `XPath="Book[@*]"` вернет все элементы "Книги" с любыми атрибутами.  
  
-   `XPath="Book[last()-1]"` вернет второй с конца элемент "Книги" \("используется Microsoft .NET"\).  
  
-   `XPath="*[position()>3]"` вернет все элементы "Книги", за исключением первых трех.  
  
 При выполнении запроса **XPath** возвращается объект <xref:System.Xml.XmlNode> или список элементов XmlNode.  <xref:System.Xml.XmlNode> является объектом [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], что позволяет выполнять привязку к свойствам [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] с использованием свойства <xref:System.Windows.Data.Binding.Path%2A>.  Рассмотрим предыдущий пример еще раз.  Если остальную часть примера оставить без изменения, а изменить привязку <xref:System.Windows.Controls.TextBlock> на приведенную ниже, то то будут отображаться имена возвращенных XmlNodes в <xref:System.Windows.Controls.ListBox>.  В этом случае именем для всех возвращаемых всех узлов будет являться "*Книга*".  
  
 [!code-xml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 В некоторых приложениях внедрение [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] в качестве острова данных в источник страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] может вызвать неудобство, поскольку точное содержимое данных должно быть известно во время компиляции.  Поэтому получение данных из внешнего файла [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] также поддерживается, как в следующем примере.  
  
 [!code-xml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Если данные [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] находятся в удаленном файле [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], то можно определить доступ к данным путем назначения соответствующего [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] для атрибута <xref:System.Windows.Data.XmlDataProvider.Source%2A> следующим образом:  
  
```  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## См. также  
 <xref:System.Windows.Data.ObjectDataProvider>   
 [Привязка к XDocument, XElement или LINQ для результатов запросов XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)   
 [Использование шаблона "главный\-подчиненный" с иерархическими XML\-данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)   
 [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)