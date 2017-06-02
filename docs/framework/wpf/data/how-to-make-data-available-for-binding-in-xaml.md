---
title: "Практическое руководство. Обеспечение доступности данных для привязки в XAML | Microsoft Docs"
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
  - "привязка данных, предоставление данных для"
  - "привязка данных, предоставление данных для привязки"
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Обеспечение доступности данных для привязки в XAML
В этом разделе обсуждаются различные способы, позволяющие сделать данные доступными для привязки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], в зависимости от потребностей приложения.  
  
## Пример  
 Если требуется осуществить привязку к объекту [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], одним из способов сделать этот объект доступным для привязки является определение его в качестве ресурса и присвоения ему атрибута `x:Key`.  В следующем примере имеется объект `Person` со строковым свойством `PersonName`.  Объект `Person` определен в пространстве имен `SDKSample`.  
  
 [!code-xml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 Затем можно осуществить привязку к данному объекту в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], как показано в следующем примере.  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Также можно использовать класс <xref:System.Windows.Data.ObjectDataProvider>, как показано в следующем примере.  
  
 [!code-xml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 Привязка определяется тем же способом:  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 В этом конкретном примере получен тот же результат: <xref:System.Windows.Controls.TextBlock> с текстовым содержимым `Joe`.  Однако класс <xref:System.Windows.Data.ObjectDataProvider> предоставляет такие функциональные возможности, как возможность привязки к результату метода.  Можно выбрать использование класса <xref:System.Windows.Data.ObjectDataProvider>, если требуются предоставляемые им функциональные возможности.  
  
 Однако при осуществлении привязки к уже созданному объекту `DataContext` необходимо задать в коде, как в следующем примере.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Сведения о доступе к данным [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] для привязки с помощью класса <xref:System.Windows.Data.XmlDataProvider> см. в разделе [Привязка к XML\-данным с помощью XMLDataProvider и запросов XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  Сведения о доступе к данным [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] для привязки с помощью класса <xref:System.Windows.Data.ObjectDataProvider> см. в разделе [Привязка к XDocument, XElement или LINQ для результатов запросов XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Сведения о различных способах указания данных, к которым осуществляется привязка, см. в разделе [Указание источника привязки](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).  Сведения о том, к каким типам данных можно осуществить привязку, или как реализовать собственные объекты [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] для привязки, см. в разделе [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
## См. также  
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)