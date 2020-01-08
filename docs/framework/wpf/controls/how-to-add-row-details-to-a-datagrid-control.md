---
title: Добавление сведений о строках в элемент управления DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 4db414e1907d42071f7251c390077d4020fa577c
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559681"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Добавление сведений о строках в элемент управления DataGrid
При использовании элемента управления <xref:System.Windows.Controls.DataGrid> можно настроить представление данных, добавив раздел сведения о строке. Добавление раздела сведений о строке позволяет сгруппировать некоторые данные в шаблон, который можно показать или свернуть. Например, можно добавить сведения о строках в <xref:System.Windows.Controls.DataGrid>, которая представляет только сводку по данным для каждой строки в <xref:System.Windows.Controls.DataGrid>, но при этом предоставляет больше полей данных, когда пользователь выбирает строку. Вы определяете шаблон для раздела сведения о строке в свойстве <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>. На следующем рисунке показан пример раздела сведений о строке.  
  
 ![Сетка, показанная со сведениями о строках](./media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Шаблон сведений о строках определяется как встроенный XAML или ресурс. Оба подхода показаны в следующих процедурах. Шаблон данных, добавленный в качестве ресурса, можно использовать во всем проекте без повторного создания шаблона. Шаблон данных, добавленный как встроенный код XAML, доступен только из элемента управления, в котором он определен.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Отображение сведений о строках с помощью встроенного кода XAML  
  
1. Создайте <xref:System.Windows.Controls.DataGrid>, отображающий данные из источника данных.  
  
2. В элементе <xref:System.Windows.Controls.DataGrid> добавьте элемент <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3. Создайте <xref:System.Windows.DataTemplate>, определяющую внешний вид раздела сведения о строке.  
  
     В следующем коде XAML показан <xref:System.Windows.Controls.DataGrid> и определение встроенного <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>. <xref:System.Windows.Controls.DataGrid> отображает три значения в каждой строке и три дополнительных значения при выборе строки.  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     В следующем коде показан запрос, используемый для выбора данных, отображаемых в <xref:System.Windows.Controls.DataGrid>. В этом примере запрос выбирает данные из сущности, содержащей сведения о клиенте.  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Отображение сведений о строках с помощью ресурса  
  
1. Создайте <xref:System.Windows.Controls.DataGrid>, отображающий данные из источника данных.  
  
2. Добавьте элемент <xref:System.Windows.FrameworkElement.Resources%2A> в корневой элемент, например элемент управления <xref:System.Windows.Window> или элемент управления <xref:System.Windows.Controls.Page>, или добавьте элемент <xref:System.Windows.Application.Resources%2A> в класс <xref:System.Windows.Application> в файле App. XAML (или Application. XAML).  
  
3. В элементе Resources создайте <xref:System.Windows.DataTemplate>, определяющую внешний вид раздела сведения о строке.  
  
     В следующем коде XAML показан <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>, определенный в классе <xref:System.Windows.Application>.  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. На <xref:System.Windows.DataTemplate>задайте для [директивы x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) значение, уникально идентифицирующее шаблон данных.  
  
5. В элементе <xref:System.Windows.Controls.DataGrid> задайте для свойства <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> ресурс, определенный на предыдущих шагах. Назначьте ресурс как статический ресурс.  
  
     В следующем коде XAML показано свойство <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>, заданное для ресурса из предыдущего примера.  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Установка видимости и предотвращение горизонтальной прокрутки для сведений о строках  
  
1. При необходимости задайте для свойства <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>.  
  
     По умолчанию устанавливается значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. Можно задать для него значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible>, чтобы отобразить подробные сведения для всех строк или <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed>, чтобы скрыть сведения для всех строк.  
  
2. При необходимости задайте для свойства <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> значение `true`, чтобы не допустить горизонтальной прокрутки раздела сведений о строках.
