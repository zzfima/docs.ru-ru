---
title: "Практическое руководство. Привязка к источнику данных ADO.NET | Microsoft Docs"
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
  - "источники данных ADO.NET, привязка к"
  - "привязка, к источникам данных ADO.NET"
  - "привязка данных, привязка к источникам данных ADO.NET"
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Привязка к источнику данных ADO.NET
В этом примере показана привязка элемента управления [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> к источнику данных [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`.  
  
## Пример  
 В этом примере объект `OleDbConnection` используется для подключения к источнику данных, который является файлом `Access MDB`, указанным в строке подключения.  После установки подключения создается объект `OleDbDataAdpater`.  Объект `OleDbDataAdpater` выполняет инструкцию "select" [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] для извлечения набора записей из базы данных.  Результаты выполнения инструкции [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] сохраняются в таблице `DataTable` объекта `DataSet` путем вызова метода `Fill` объекта `OleDbDataAdapter`.  Таблица `DataTable` в этом примере называется `BookTable`.  После этого объекту `DataSet` задается свойство <xref:System.Windows.FrameworkElement.DataContext%2A> класса <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Затем свойство <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> элемента управления <xref:System.Windows.Controls.ListBox> связывается с таблицей `BookTable` объекта `DataSet`:  
  
 [!code-xml[ADODataSet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]  
  
 Шаблон `BookItemTemplate` — это шаблон данных <xref:System.Windows.DataTemplate>, определяющий вид данных:  
  
 [!code-xml[ADODataSet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]  
  
 Метод `IntColorConverter` преобразует целочисленное значение `int` в цвет.  С помощью этого преобразователя цвет <xref:System.Windows.Controls.TextBlock.Background%2A> третьего объекта <xref:System.Windows.Controls.TextBlock> становится зеленым, если значение `NumPages` меньше 350, и красным — в противном случае.  Реализация преобразователя здесь не показана.  
  
## См. также  
 <xref:System.Windows.Data.BindingListCollectionView>   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)