---
title: "Поиск элемента, созданного шаблоном ControlTemplate | Microsoft Docs"
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
  - "шаблоны элементов управления ControlTemplate [WPF], поиск элементов"
  - "поиск элементов ControlTemplate"
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Поиск элемента, созданного шаблоном ControlTemplate
В этом примере демонстрируется порядок поиска элементов, которые создаются с использованием шаблона <xref:System.Windows.Controls.ControlTemplate>.  
  
## Пример  
 В следующем примере показан стиль, который создает простой шаблон <xref:System.Windows.Controls.ControlTemplate> для класса <xref:System.Windows.Controls.Button>:  
  
 [!code-xml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Чтобы найти элемент в шаблоне после применения шаблона, следует вызвать метод <xref:System.Windows.FrameworkTemplate.FindName%2A> класса <xref:System.Windows.Controls.Control.Template%2A>.  В следующем примере создается окно сообщения, которое показывает фактическое значение ширины сетки <xref:System.Windows.Controls.Grid> в шаблоне элемента управления:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## См. также  
 [Поиск элементов, созданных с использованием шаблона DataTemplate](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Области видимости имен XAML в WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)   
 [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)