---
title: "Практическое руководство. Создание пользовательского режима представления для ListView | Microsoft Docs"
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
  - "ListView - элементы управления, создание настраиваемого режима представления"
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Создание пользовательского режима представления для ListView
В этом примере демонстрируется создание пользовательского режима <xref:System.Windows.Controls.ListView.View%2A> для элемента управления <xref:System.Windows.Controls.ListView>.  
  
## Пример  
 При создании пользовательского представления для элемента управления <xref:System.Windows.Controls.ListView> необходимо использовать класс <xref:System.Windows.Controls.ViewBase>.  В следующем примере показан режим представления с именем `PlainView`, который является производным от класса <xref:System.Windows.Controls.ViewBase>.  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Чтобы применить стиль к пользовательскому представлению, используйте класс <xref:System.Windows.Style>.  В следующем примере определяется <xref:System.Windows.Style> для режима представления `PlainView`.  В предыдущем примере этот стиль задан как значение свойства <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A>, которое определено для `PlainView`.  
  
 [!code-xml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Чтобы определить макет данных в режиме представления, определите объект <xref:System.Windows.DataTemplate>.  В следующем примере определяется <xref:System.Windows.DataTemplate>, который может использоваться для отображения данных в режиме представления `PlainView`.  
  
 [!code-xml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 В следующем примере показано определение <xref:System.Windows.ResourceKey> для режима представления `PlainView`, который использует <xref:System.Windows.DataTemplate>, определенный в предыдущем примере.  
  
 [!code-xml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Элемент управления <xref:System.Windows.Controls.ListView> может использовать пользовательское представление, если в качестве значения свойства <xref:System.Windows.Controls.ListView.View%2A> указан ключ ресурса.  В следующем примере показано, как задать `PlainView` в качестве режима представления для <xref:System.Windows.Controls.ListView>.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Полный код примера см. в разделе [Пример "ListView with Multiple Views"](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## См. также  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Практические руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)