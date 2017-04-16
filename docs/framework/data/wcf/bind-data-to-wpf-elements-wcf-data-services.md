---
title: "Как привязать данные к элементам Windows Presentation Foundation (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "привязка данных, Службы WCF Data Services"
  - "Службы WCF Data Services, привязка данных"
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как привязать данные к элементам Windows Presentation Foundation (службы WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют привязывать элементы Windows Presentation Foundation \(WPF\), например <xref:System.Windows.Controls.ListBox>``или <xref:System.Windows.Controls.ComboBox>, к экземпляру коллекции <xref:System.Data.Services.Client.DataServiceCollection%601>, которая обрабатывает события, вызываемые элементами управления <xref:System.Data.Services.Client.DataServiceContext>, и поддерживает синхронизацию изменений, произведенных над данными в элементах управления.  Для получения дополнительной информации см. [Привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных.  Эта служба и клиентские классы данных создаются после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Пример  
 Следующий пример взят из страницы с выделенным кодом для страницы на языке XAML, которая определяет окно `SalesOrders` в WPF.  При загрузке окна создается коллекция <xref:System.Data.Services.Client.DataServiceCollection%601> на основе результатов запросов клиентов, отфильтрованных по стране.  Загружаются все страницы разбитого на страницы результата вместе со связанными заказами. После этого данные привязываются к свойству <xref:System.Windows.FrameworkElement.DataContext%2A> объекта <xref:System.Windows.Controls.StackPanel>, который является корневым элементом управления макетом в окне WPF.  Для получения дополнительной информации см. [Загрузка отложенного содержимого](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## Пример  
 Следующий код XAML определяет окно `SalesOrders` в WPF для предыдущего примера.  
  
 [!code-xml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## Пример  
 Следующий пример взят из страницы с выделенным кодом для страницы на языке XAML, которая определяет окно `SalesOrders` в WPF.  При загрузке окна создается коллекция <xref:System.Data.Services.Client.DataServiceCollection%601> на основе результатов запросов клиентов со связанными объектами, отфильтрованными по стране.  Результат привязывается к свойству <xref:System.Windows.FrameworkElement.DataContext%2A> объекта <xref:System.Windows.Controls.StackPanel>, являющегося корневым элементом управления макетом в окне WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## Пример  
 Следующий код XAML определяет окно `SalesOrders` в WPF для предыдущего примера.  
  
 [!code-xml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]