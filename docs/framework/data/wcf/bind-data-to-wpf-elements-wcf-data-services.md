---
title: "Практическое руководство. Привязка данных к элементам Windows Presentation Foundation (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ba6f46fb8c16b00f1e63be94b0a6ef300d56d6d2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-bind-data-to-windows-presentation-foundation-elements-wcf-data-services"></a>Практическое руководство. Привязка данных к элементам Windows Presentation Foundation (службы данных WCF)
С [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], позволяют привязывать элементы Windows Presentation Foundation (WPF), такие как <xref:System.Windows.Controls.ListBox>'' или <xref:System.Windows.Controls.ComboBox> к экземпляру <xref:System.Data.Services.Client.DataServiceCollection%601>, которая обрабатывает события, вызываемые элементами управления для сохранения <xref:System.Data.Services.Client.DataServiceContext> синхронизацию изменений внесены данные в элементах управления. Дополнительные сведения см. в разделе [привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются после выполнения [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующий пример взят из страницы с выделенным кодом для страницы на языке XAML, которая определяет окно `SalesOrders` в WPF. При загрузке окна создается коллекция <xref:System.Data.Services.Client.DataServiceCollection%601> на основе результатов запросов клиентов, отфильтрованных по стране. Загружаются все страницы разбитого на страницы результата вместе со связанными заказами. После этого данные привязываются к свойству <xref:System.Windows.FrameworkElement.DataContext%2A> объекта <xref:System.Windows.Controls.StackPanel>, который является корневым элементом управления макетом в окне WPF. Дополнительные сведения см. в разделе [загрузка отложенного содержимого](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## <a name="example"></a>Пример  
 Следующий код XAML определяет окно `SalesOrders` в WPF для предыдущего примера.  
  
 [!code-xaml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## <a name="example"></a>Пример  
 Следующий пример взят из страницы с выделенным кодом для страницы на языке XAML, которая определяет окно `SalesOrders` в WPF. При загрузке окна создается коллекция <xref:System.Data.Services.Client.DataServiceCollection%601> на основе результатов запросов клиентов со связанными объектами, отфильтрованными по стране. Результат привязывается к свойству <xref:System.Windows.FrameworkElement.DataContext%2A> объекта <xref:System.Windows.Controls.StackPanel>, являющегося корневым элементом управления макетом в окне WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## <a name="example"></a>Пример  
 Следующий код XAML определяет окно `SalesOrders` в WPF для предыдущего примера.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]
