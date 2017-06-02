---
title: "Добавление сведений о строках в элемент управления DataGrid | Microsoft Docs"
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
  - "DataGrid [WPF], сведения о строке"
  - "DataTemplate [WPF], DataGrid"
  - "сведения о строке [WPF], DataGrid"
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Добавление сведений о строках в элемент управления DataGrid
При использовании элемента управления <xref:System.Windows.Controls.DataGrid> можно настраивать представление данных путем добавления раздела сведений о строке.  Добавление раздела сведений о строке позволяет группировать некоторые данные в шаблон, который может быть видимым или свернутым.  Например, можно добавить сведения о строке в элемент управления <xref:System.Windows.Controls.DataGrid>, представляющие только сводку по данным каждой строки в элементе управления <xref:System.Windows.Controls.DataGrid>, но предоставляет дополнительные поля данных при выборе пользователем этой строки.  Шаблон для раздела сведений о строке задается в свойстве <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  На следующем рисунке показан пример раздела сведений о строке.  
  
 ![Сетка DataGrid, показанная со сведениями в строке](../../../../docs/framework/wpf/controls/media/ndp-rowdetails.png "NDP\_RowDetails")  
  
 Шаблон сведений о строке задается либо как встроенный XAML, либо как ресурс.  Оба варианта показаны в следующих процедурах.  Шаблон данных, добавляемый как ресурс, может использоваться во всем проекте без необходимости повторного создания шаблона.  Шаблон данных, добавляемый как встроенный XAML, доступен только из элемента управления, в котором он определен.  
  
### Отображение сведений о строке с помощью встроенного XAML  
  
1.  Создайте элемент управления <xref:System.Windows.Controls.DataGrid>, отображающий данные из источника данных.  
  
2.  В элементе управления <xref:System.Windows.Controls.DataGrid> добавьте элемент <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3.  Создайте шаблон <xref:System.Windows.DataTemplate>, задающий внешний вид раздела сведений о строке.  
  
     В следующем примере XAML показан элемент управления <xref:System.Windows.Controls.DataGrid> и порядок задания встроенного шаблона <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  Элемент управления <xref:System.Windows.Controls.DataGrid> отображает три значения в каждой строке и не менее трех значений при выборе этой строки.  
  
     [!code-xml[DataGrid_RowDetails#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     В следующем примере кода показан запрос, используемый для выбора данных, отображаемых в элементе управления <xref:System.Windows.Controls.DataGrid>.  В этом примере запрос выбирает данные из сущности, содержащей сведения о клиенте.  
  
     [!code-csharp[DataGrid_RowDetails#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### Отображение сведений о строке с помощью ресурса  
  
1.  Создайте элемент управления <xref:System.Windows.Controls.DataGrid>, отображающий данные из источника данных.  
  
2.  Добавьте элемент <xref:System.Windows.FrameworkElement.Resources%2A> в корневой элемент, такой как элемент управления <xref:System.Windows.Window> и <xref:System.Windows.Controls.Page>, или же добавьте элемент <xref:System.Windows.Application.Resources%2A> в класс <xref:System.Windows.Application> в файле App.xaml \(или Application.xaml\).  
  
3.  В элементе ресурсов создайте шаблон <xref:System.Windows.DataTemplate>, задающий внешний вид раздела сведений о строке.  
  
     Следующий пример XAML показывает элемент <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>, заданный в классе <xref:System.Windows.Application>.  
  
     [!code-xml[DataGrid_RowDetails#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4.  В элементе <xref:System.Windows.DataTemplate> установите атрибут [Директива x:Key](../../../../docs/framework/xaml-services/x-key-directive.md) в значение, уникально идентифицирующее шаблон данных.  
  
5.  В элементе <xref:System.Windows.Controls.DataGrid> установите в качестве значения свойства <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> ресурс, заданный в на предыдущих этапах.  Назначьте этот ресурс как статический.  
  
     В следующем примере XAML показывается установка в качестве значения свойства <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> ресурса из предыдущего примера.  
  
     [!code-xml[DataGrid_RowDetails#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### Установка видимости и предотвращение горизонтальной прокрутки сведений о строке  
  
1.  При необходимости присвойте свойству <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>.  
  
     По умолчанию это значение устанавливается в <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>.  Можно установить его в значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>, чтобы показывать сведения по всем строкам, или в значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>, чтобы скрыть сведения для всех строк.  
  
2.  При необходимости установите свойство <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> в значение `true`, предотвратить горизонтальное прокручивание раздела сведений о строке.