---
title: "Практическое руководство. Сортировка столбцов GridView при нажатии на заголовок | Microsoft Docs"
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
  - "элементов управления GridView"
  - "элементы управления, ListView"
  - "Элементы управления ListView, сортировка столбцов GridView"
  - "Элементы управления GridView, элемент управления ListView"
ms.assetid: 4865d720-d147-40ed-83a7-af7587f8aad8
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Сортировка столбцов GridView при нажатии на заголовок
В этом примере показано, как создать <xref:System.Windows.Controls.ListView> управления, реализующий <xref:System.Windows.Controls.GridView> просмотреть режим и сортировка данных содержимого, когда пользователь щелкает заголовок столбца.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется <xref:System.Windows.Controls.GridView> с тремя столбцами, которые привязаны к <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, и <xref:System.DateTime.Day%2A>, свойства <xref:System.DateTime> структуры.  
  
```xaml  
<GridView>  
  <GridViewColumn DisplayMemberBinding="{Binding Path=Year}"   
                  Header="Year"  
                  Width="100"/>  
  <GridViewColumn DisplayMemberBinding="{Binding Path=Month}"   
                  Header="Month"  
                  Width="100"/>  
  <GridViewColumn DisplayMemberBinding="{Binding Path=Day}"   
                  Header="Day"  
                  Width="100"/>  
</GridView>  
```  
  
 В следующем примере показано элементов данных, которые определены как <xref:System.Collections.ArrayList> из <xref:System.DateTime> объектов. <xref:System.Collections.ArrayList> определяется как <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для <xref:System.Windows.Controls.ListView> элемента управления.  
  
```xaml  
<ListView.ItemsSource>  
  <s:ArrayList>  
    <p:DateTime>1993/1/1 12:22:02</p:DateTime>  
    <p:DateTime>1993/1/2 13:2:01</p:DateTime>  
    <p:DateTime>1997/1/3 2:1:6</p:DateTime>  
    <p:DateTime>1997/1/4 13:6:55</p:DateTime>  
    <p:DateTime>1999/2/1 12:22:02</p:DateTime>  
    <p:DateTime>1998/2/2 13:2:01</p:DateTime>  
    <p:DateTime>2000/2/3 2:1:6</p:DateTime>  
    <p:DateTime>2002/2/4 13:6:55</p:DateTime>  
    <p:DateTime>2001/3/1 12:22:02</p:DateTime>  
    <p:DateTime>2006/3/2 13:2:01</p:DateTime>  
    <p:DateTime>2004/3/3 2:1:6</p:DateTime>  
    <p:DateTime>2004/3/4 13:6:55</p:DateTime>  
  </s:ArrayList>  
</ListView.ItemsSource>  
```  
  
 `s` И `p` идентификаторы в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] тегов см. сопоставления пространства имен, которые определены в метаданных [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы. В следующем примере показано определение метаданных.  
  
```xaml  
<Window        
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    x:Class="ListViewSort.Window1"      
    xmlns:s="clr-namespace:System.Collections;assembly=mscorlib"  
    xmlns:p="clr-namespace:System;assembly=mscorlib">  
```  
  
 Чтобы отсортировать данные в соответствии с содержимым столбца, в примере определяется обработчик событий для обработки <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событие, возникающее при нажатии кнопки заголовка столбца. В следующем примере показано, как задать обработчик событий для <xref:System.Windows.Controls.GridViewColumnHeader> управления.  
  
```xaml  
<ListView x:Name='lv' Height="150" HorizontalAlignment="Center"   
  VerticalAlignment="Center"   
  GridViewColumnHeader.Click="GridViewColumnHeaderClickedHandler"  
 >  
```  
  
 В примере определяется обработчик событий, чтобы изменяет направление сортировки по возрастанию и убыванию при каждом нажатии кнопки заголовка столбца. В следующем примере показан обработчик событий.  
  
```csharp  
public partial class Window1 : Window  
{  
    public Window1()  
    {  
        InitializeComponent();  
    }  
  
    GridViewColumnHeader _lastHeaderClicked = null;  
    ListSortDirection _lastDirection = ListSortDirection.Ascending;  
  
    void GridViewColumnHeaderClickedHandler(object sender,  
                                            RoutedEventArgs e)  
    {  
        GridViewColumnHeader headerClicked =  
              e.OriginalSource as GridViewColumnHeader;  
        ListSortDirection direction;  
  
        if (headerClicked != null)  
        {  
            if (headerClicked.Role != GridViewColumnHeaderRole.Padding)  
            {  
                if (headerClicked != _lastHeaderClicked)  
                {  
                    direction = ListSortDirection.Ascending;  
                }  
                else  
                {  
                    if (_lastDirection == ListSortDirection.Ascending)  
                    {  
                        direction = ListSortDirection.Descending;  
                    }  
                    else  
                    {  
                        direction = ListSortDirection.Ascending;  
                    }  
                }  
  
                string header = headerClicked.Column.Header as string;  
                Sort(header, direction);  
  
                if (direction == ListSortDirection.Ascending)  
                {  
                    headerClicked.Column.HeaderTemplate =  
                      Resources["HeaderTemplateArrowUp"] as DataTemplate;  
                }  
                else  
                {  
                    headerClicked.Column.HeaderTemplate =  
                      Resources["HeaderTemplateArrowDown"] as DataTemplate;  
                }  
  
                // Remove arrow from previously sorted header  
                if (_lastHeaderClicked != null && _lastHeaderClicked != headerClicked)  
                {  
                    _lastHeaderClicked.Column.HeaderTemplate = null;  
                }  
  
                _lastHeaderClicked = headerClicked;  
                _lastDirection = direction;  
            }  
        }  
    }  
```  
  
```vb  
Partial Public Class Window1  
        Inherits Window  
        Public Sub New()  
            InitializeComponent()  
        End Sub  
  
        Private _lastHeaderClicked As GridViewColumnHeader = Nothing  
        Private _lastDirection As ListSortDirection = ListSortDirection.Ascending  
  
        Private Sub GridViewColumnHeaderClickedHandler(ByVal sender As Object, ByVal e As RoutedEventArgs)  
            Dim headerClicked As GridViewColumnHeader = TryCast(e.OriginalSource, GridViewColumnHeader)  
            Dim direction As ListSortDirection  
  
            If headerClicked IsNot Nothing Then  
                If headerClicked.Role <> GridViewColumnHeaderRole.Padding Then  
                    If headerClicked IsNot _lastHeaderClicked Then  
                        direction = ListSortDirection.Ascending  
                    Else  
                        If _lastDirection = ListSortDirection.Ascending Then  
                            direction = ListSortDirection.Descending  
                        Else  
                            direction = ListSortDirection.Ascending  
                        End If  
                    End If  
  
                    Dim header As String = TryCast(headerClicked.Column.Header, String)  
                    Sort(header, direction)  
  
                    If direction = ListSortDirection.Ascending Then  
                        headerClicked.Column.HeaderTemplate = TryCast(Resources("HeaderTemplateArrowUp"), DataTemplate)  
                    Else  
                        headerClicked.Column.HeaderTemplate = TryCast(Resources("HeaderTemplateArrowDown"), DataTemplate)  
                    End If  
  
                    ' Remove arrow from previously sorted header  
                    If _lastHeaderClicked IsNot Nothing AndAlso _lastHeaderClicked IsNot headerClicked Then  
                        _lastHeaderClicked.Column.HeaderTemplate = Nothing  
                    End If  
  
                    _lastHeaderClicked = headerClicked  
                    _lastDirection = direction  
                End If  
            End If  
        End Sub  
```  
  
 В следующем примере алгоритм сортировки, который вызывается обработчиком событий для сортировки данных. Сортировка выполняется путем создания нового <xref:System.ComponentModel.SortDescription> структуры.  
  
```csharp  
private void Sort(string sortBy, ListSortDirection direction)  
{  
    ICollectionView dataView =  
      CollectionViewSource.GetDefaultView(lv.ItemsSource);  
  
    dataView.SortDescriptions.Clear();  
    SortDescription sd = new SortDescription(sortBy, direction);  
    dataView.SortDescriptions.Add(sd);  
    dataView.Refresh();  
}  
  
```  
  
```vb  
Private Sub Sort(ByVal sortBy As String, ByVal direction As ListSortDirection)  
            Dim dataView As ICollectionView = CollectionViewSource.GetDefaultView(lv.ItemsSource)  
  
            dataView.SortDescriptions.Clear()  
            Dim sd As New SortDescription(sortBy, direction)  
            dataView.SortDescriptions.Add(sd)  
            dataView.Refresh()  
        End Sub  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Общие сведения о ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)