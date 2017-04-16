---
title: "Практическое руководство. Поворот рукописных данных | Microsoft Docs"
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
  - "рукописный ввод, поворот"
  - "рукописный ввод с поворотом"
ms.assetid: fac36cc9-dd01-41ca-9bde-9d33e3790bbe
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Поворот рукописных данных
## Пример  
 В следующем примере копируются рукописные данные из <xref:System.Windows.Controls.InkCanvas> в <xref:System.Windows.Controls.Canvas>, содержащий <xref:System.Windows.Controls.InkPresenter>.  Когда приложение копирует рукописные данные, оно также поворачивает рукописные данные на 90 градусов по часовой стрелке.  
  
 [!code-xml[HowToRotateInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## Пример  
 Следующий пример представляет собой пользовательский <xref:System.Windows.Documents.Adorner>, поворачивающий штрихи на <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[AdornerForStrokes#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 Следующий пример представляет собой файл [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], определяющий <xref:System.Windows.Controls.InkPresenter> и заполняющий его рукописным вводом.  Обработчик событий `Window_Loaded` добавляет пользовательский графический элемент <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-xml[AdornerForStrokes#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]