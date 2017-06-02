---
title: "Практическое руководство. Размещение дочерних элементов Grid | Microsoft Docs"
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
  - "Grid - элемент управления, размещение дочерних элементов"
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Размещение дочерних элементов Grid
В этом примере демонстрируется, как использовать методы получения и установки, определенные в <xref:System.Windows.Controls.Grid> для размещения дочерних элементов.  
  
## Пример  
 В следующем примере определяется родительский элемент <xref:System.Windows.Controls.Grid> \(`grid1`\), который имеет три столбца и три строки.  Дочерний элемент <xref:System.Windows.Shapes.Rectangle> \(`rect1`\) добавляется в <xref:System.Windows.Controls.Grid> в столбец номер 0, строку номер 0.  Элементы <xref:System.Windows.Controls.Button> представляют методы, которые вызываются для изменения положения элемента <xref:System.Windows.Shapes.Rectangle> в <xref:System.Windows.Controls.Grid>.  Когда пользователь нажимает кнопку, активируется связанный метод.  
  
 [!code-xml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 Следующий пример кода обрабатывает методы, вызываемые событиями кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  Пример записывает эти вызовы методов в элементы <xref:System.Windows.Controls.TextBlock>, которые используют связанные полученные методы для вывода новых значений свойств в виде строк.  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## См. также  
 <xref:System.Windows.Controls.Grid>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)