---
title: "Практическое руководство. Указание пользовательского расположения контекстного меню | Microsoft Docs"
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
  - "Popup - элемент управления, задание настраиваемой позиции"
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Указание пользовательского расположения контекстного меню
В этом примере демонстрируется указание пользовательского расположения для элемента управления <xref:System.Windows.Controls.Primitives.Popup> при установке свойства <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> в <xref:System.Windows.Controls.Primitives.PlacementMode>.  
  
## Пример  
 Когда свойство <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> устанавливается в <xref:System.Windows.Controls.Primitives.PlacementMode>, <xref:System.Windows.Controls.Primitives.Popup> вызывает определенный экземпляр делегата <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.  Этот делегат возвращает набор возможных точек относительно верхнего левого угла нужной области и верхнего левого угла <xref:System.Windows.Controls.Primitives.Popup>.  Размещение <xref:System.Windows.Controls.Primitives.Popup> происходит в точке, обеспечивающей наилучшую видимость.  
  
 В следующем примере показано, как определить положение <xref:System.Windows.Controls.Primitives.Popup> путем установки свойства <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> в <xref:System.Windows.Controls.Primitives.PlacementMode>.  В нем также показывается, как создать и назначить делегат <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>, чтобы расположить <xref:System.Windows.Controls.Primitives.Popup>.  Делегат обратного вызова возвращает два объекта <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>.  Если <xref:System.Windows.Controls.Primitives.Popup> скрыт краем экрана в первом положении, <xref:System.Windows.Controls.Primitives.Popup> помещается во второе положение.  
  
 [!code-xml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Полный пример см. на веб\-странице [Пример Popup Placement](http://go.microsoft.com/fwlink/?LinkID=160032).  
  
## См. также  
 <xref:System.Windows.Controls.Primitives.Popup>   
 [Общие сведения о контекстном меню](../../../../docs/framework/wpf/controls/popup-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)