---
title: "Практическое руководство. Поиск элементов, созданных с использованием шаблона DataTemplate | Microsoft Docs"
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
  - "DataTemplate"
  - "Поиск элементов DataTemplate"
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Поиск элементов, созданных с использованием шаблона DataTemplate
В этом примере демонстрируется порядок поиска элементов, которые создаются с использованием шаблона <xref:System.Windows.DataTemplate>.  
  
## Пример  
 В этом примере используется объект <xref:System.Windows.Controls.ListBox>, который связан с определенными данными [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]:  
  
 [!code-xml[FindGeneratedItems#LB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Для объекта <xref:System.Windows.Controls.ListBox> используется следующий шаблон <xref:System.Windows.DataTemplate>:  
  
 [!code-xml[FindGeneratedItems#DT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Чтобы получить элемент <xref:System.Windows.Controls.TextBlock>, созданный с использованием шаблона <xref:System.Windows.DataTemplate> конкретного объекта <xref:System.Windows.Controls.ListBoxItem>, необходимо получить объект <xref:System.Windows.Controls.ListBoxItem>, найти объект <xref:System.Windows.Controls.ContentPresenter> в полученном объекте <xref:System.Windows.Controls.ListBoxItem>, а затем вызвать метод <xref:System.Windows.FrameworkTemplate.FindName%2A> для шаблона <xref:System.Windows.DataTemplate>, который установлен для этого объекта <xref:System.Windows.Controls.ContentPresenter>.  В следующем примере описывается порядок выполнения этих шагов.  В целях демонстрации, в этом примере создается окно сообщения, в котором отображается текстовое содержимое блока, созданного с использованием шаблона <xref:System.Windows.DataTemplate>.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Ниже приведена реализация `FindVisualChild`, в которой используются методы <xref:System.Windows.Media.VisualTreeHelper>.  
  
 [!code-csharp[FindGeneratedItems#FVC](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## См. также  
 [Поиск элемента, созданного шаблоном ControlTemplate](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Области видимости имен XAML в WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)   
 [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)