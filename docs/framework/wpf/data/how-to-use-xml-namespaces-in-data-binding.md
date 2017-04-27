---
title: "Практическое руководство. Использование пространства имен XML при связывании данных | Microsoft Docs"
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
  - "привязка данных, пространства имен XML"
  - "пространства имен, XML"
  - "XML, пространства имен"
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Использование пространства имен XML при связывании данных
## Пример  
 В этом примере демонстрируется обработка пространств имен, указанных в [источнике привязки](GTMT) [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 Если данные [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] имеют следующее определение пространства имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]:  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 Элемент <xref:System.Windows.Data.XmlNamespaceMapping> можно использовать для сопоставления пространства имен и <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, как показано в следующем примере.  Затем можно использовать <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> для ссылки на пространство имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  В этом примере элемент управления <xref:System.Windows.Controls.ListBox> отображает *title* и *dc:date* из каждого *item*.  
  
 <!-- TODO: review snippet reference [!code-xml[XmlnsBind#XmlNamespaceMapping](../../../../samples/snippets/xaml/VS_Snippets_Wpf/XmlnsBind/XAML/Window1.xaml#xmlnamespacemapping)]  -->
 <!-- TODO: review snippet reference [!code-xml[XmlnsBind#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBind/CS/Window1.xaml#xmlnamespacemapping)]  -->  
  
 Обратите внимание на то, что указанный <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> не обязан соответствовать тому, который используется в источнике [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]; если префикс изменяется в источнике [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], то сопоставление по\-прежнему работает.  
  
 В этом примере данные [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] поступают из веб\-службы, но элемент <xref:System.Windows.Data.XmlNamespaceMapping> также работает со встроенными данными [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] и [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] во внедренном файле.  
  
## См. также  
 [Привязка к XML\-данным с помощью XMLDataProvider и запросов XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)