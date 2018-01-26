---
title: "Добавление сведений о строках в элемент управления DataGrid"
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
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f65eb9e916fad83deb1476c1d8f0def4981d08d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Добавление сведений о строках в элемент управления DataGrid
При использовании <xref:System.Windows.Controls.DataGrid> элемента управления, можно настраивать представление данных путем добавления раздела сведений о строке. Добавление раздела сведений о строке позволяет группировать некоторые данные в шаблоне, который при необходимости видима или свернута. Например, можно добавить сведения о строке в <xref:System.Windows.Controls.DataGrid> , представляющие только сводку данных для каждой строки в <xref:System.Windows.Controls.DataGrid>, но предоставляет дополнительные поля данных, когда пользователь выбирает строку. Определить шаблон для раздела сведений о строке в <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> свойство. Ниже показан пример раздела сведений о строке.  
  
 ![Сетка DataGrid, показанная со сведениями в строке](../../../../docs/framework/wpf/controls/media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Определение шаблона сведений о строке, либо как встроенный XAML или как ресурс. Оба варианта показаны в следующих процедурах. Шаблон данных, который добавляется в качестве ресурса можно использовать в проекте без повторного создания шаблона. Шаблон данных, который добавляется как встроенный код XAML доступен только из элемента управления, где он определен.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Отображение сведений о строке с помощью встроенного XAML  
  
1.  Создание <xref:System.Windows.Controls.DataGrid> , отображающий данные из источника данных.  
  
2.  В элементе <xref:System.Windows.Controls.DataGrid> добавьте элемент <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3.  Создание <xref:System.Windows.DataTemplate> , определяет внешний вид раздела сведений о строке.  
  
     В следующем XAML показан <xref:System.Windows.Controls.DataGrid> и определения <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> встроенной. <xref:System.Windows.Controls.DataGrid> Отображает три значения в каждой строке и три дополнительные значения при выборе строки.  
  
     [!code-xaml[DataGrid_RowDetails#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     В следующем коде показано запрос, который используется для выбора данных, отображаемых в <xref:System.Windows.Controls.DataGrid>. В этом примере запрос выбирает данные из сущности, содержащей сведения о клиенте.  
  
     [!code-csharp[DataGrid_RowDetails#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Отображение сведений о строке с помощью ресурса  
  
1.  Создание <xref:System.Windows.Controls.DataGrid> , отображающий данные из источника данных.  
  
2.  Добавить <xref:System.Windows.FrameworkElement.Resources%2A> элемента корневого элемента, например <xref:System.Windows.Window> управления или <xref:System.Windows.Controls.Page> , или же добавьте <xref:System.Windows.Application.Resources%2A> элемент <xref:System.Windows.Application> класс в файле App.xaml (или Application.xaml).  
  
3.  В элементе ресурсов создайте <xref:System.Windows.DataTemplate> , определяет внешний вид раздела сведений о строке.  
  
     В следующем XAML показан <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> определенные в <xref:System.Windows.Application> класса.  
  
     [!code-xaml[DataGrid_RowDetails#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4.  На <xref:System.Windows.DataTemplate>, задайте [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md) значение, уникально идентифицирующее шаблон данных.  
  
5.  В <xref:System.Windows.Controls.DataGrid> , задайте <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> свойство для ресурса, определенного в предыдущих шагах. Назначьте универсальный код ресурса, как статический ресурс.  
  
     В следующем XAML показан <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> свойства ресурса из предыдущего примера.  
  
     [!code-xaml[DataGrid_RowDetails#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Установка видимости и предотвращение горизонтальной прокрутки сведений о строке  
  
1.  При необходимости задайте <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> свойства <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> значение.  
  
     По умолчанию присвоено значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. Вы можете задать <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> чтобы показать сведения для всех строк или <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> Чтобы скрыть сведения для всех строк.  
  
2.  При необходимости задайте <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> свойства `true` для предотвращения строки раздела горизонтальная прокрутка сведений о.
