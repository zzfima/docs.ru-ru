---
title: "Практическое руководство. Привязка к источнику данных ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0eb555bb9f21385d2d0b66fe0dd39112c8350dec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="fcfcb-102">Практическое руководство. Привязка к источнику данных ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fcfcb-102">How to: Bind to an ADO.NET Data Source</span></span>
<span data-ttu-id="fcfcb-103">В этом примере показано, как привязать [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> управления [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="fcfcb-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcfcb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="fcfcb-104">Example</span></span>  
 <span data-ttu-id="fcfcb-105">В этом примере объект `OleDbConnection` используется для подключения к источнику данных, который представляет собой файл `Access MDB`, указанный в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="fcfcb-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="fcfcb-106">После установления соединения создается объект `OleDbDataAdpater`.</span><span class="sxs-lookup"><span data-stu-id="fcfcb-106">After the connection is established, an `OleDbDataAdpater` object is created.</span></span> <span data-ttu-id="fcfcb-107">Объект `OleDbDataAdpater` выполняет запрос select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] для извлечения набора записей из базы данных.</span><span class="sxs-lookup"><span data-stu-id="fcfcb-107">The `OleDbDataAdpater` object executes a select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="fcfcb-108">Результаты выполнения команды [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] хранятся в `DataTable` элементе `DataSet` путем вызова метода `Fill` класса `OleDbDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="fcfcb-108">The results from the [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="fcfcb-109">`DataTable` в этом примере назван `BookTable`.</span><span class="sxs-lookup"><span data-stu-id="fcfcb-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="fcfcb-110">Затем в примере задаются <xref:System.Windows.FrameworkElement.DataContext%2A> свойство <xref:System.Windows.Controls.ListBox> для `DataSet` объекта.</span><span class="sxs-lookup"><span data-stu-id="fcfcb-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="fcfcb-111">Затем можно привязать <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство <xref:System.Windows.Controls.ListBox> для `BookTable` из `DataSet`:</span><span class="sxs-lookup"><span data-stu-id="fcfcb-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>  
  
 [!code-xaml[ADODataSet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="fcfcb-112">`BookItemTemplate`— <xref:System.Windows.DataTemplate> , определяющий способ отображения данных:</span><span class="sxs-lookup"><span data-stu-id="fcfcb-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>  
  
 [!code-xaml[ADODataSet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]  
  
 <span data-ttu-id="fcfcb-113">`IntColorConverter` преобразует `int` в цвет.</span><span class="sxs-lookup"><span data-stu-id="fcfcb-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="fcfcb-114">С помощью этого преобразователя <xref:System.Windows.Controls.TextBlock.Background%2A> цвет третьего <xref:System.Windows.Controls.TextBlock> появляется зеленая Если значение `NumPages` является менее 350 и красное — в противном случае.</span><span class="sxs-lookup"><span data-stu-id="fcfcb-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="fcfcb-115">Здесь не приведена реализация преобразователя.</span><span class="sxs-lookup"><span data-stu-id="fcfcb-115">The implementation of the converter is not shown here.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcfcb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="fcfcb-116">See Also</span></span>  
 <xref:System.Windows.Data.BindingListCollectionView>  
 [<span data-ttu-id="fcfcb-117">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="fcfcb-117">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="fcfcb-118">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="fcfcb-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
