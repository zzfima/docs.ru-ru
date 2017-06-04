---
title: "Практическое руководство. Изменение цвета элемента с помощью событий фокуса | Microsoft Docs"
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
  - "цвета элементов, изменение"
  - "элементы, изменение цвета"
  - "события фокуса, изменение цвета элемента после"
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Изменение цвета элемента с помощью событий фокуса
В этом примере демонстрируется изменение цвета элемента при получении и потере фокуса с помощью событий <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus>.  
  
 Этот пример состоит из файла [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и файла кода программной части.  
  
## Пример  
 Следующий [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создает интерфейс пользователя, состоящий из двух объектов <xref:System.Windows.Controls.Button>, и связывает обработчики событий <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus> с объектами <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 Следующий код программной части создает обработчики событий <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus>.  Когда <xref:System.Windows.Controls.Button> получает фокус ввода с клавиатуры, <xref:System.Windows.Controls.Control.Background%2A> элемента <xref:System.Windows.Controls.Button> изменяется на красный.  Когда <xref:System.Windows.Controls.Button> теряет фокус ввода с клавиатуры, <xref:System.Windows.Controls.Control.Background%2A> элемента <xref:System.Windows.Controls.Button> изменяется обратно на белый.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## См. также  
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)