---
title: "Практическое руководство. Проверка нажатия в Viewport3D | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "трехмерные визуальные элементы, проверка нажатия"
  - "проверка нажатия, для трехмерных визуальных элементов"
  - "Viewport3D"
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Проверка нажатия в Viewport3D
В этом примере демонстрируется проверка нажатия для 3D Visuals в <xref:System.Windows.Controls.Viewport3D>.  
  
 Поскольку <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> возвращает 2D и 3D информацию, можно выполнить перебор результатов проверки для просмотра только 3D результатов.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 <xref:System.Windows.Media.HitTestResultBehavior> в следующем коде определяет способ обработки результатов проверки нажатия.  `UpdateResultInfo` и `UpdateMaterial` являются локально определенными методами.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## См. также  
 [3\-D Hit Testing Sample](http://go.microsoft.com/fwlink/?LinkID=159959)