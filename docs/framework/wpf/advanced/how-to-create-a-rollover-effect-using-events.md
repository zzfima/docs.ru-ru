---
title: "Инструкция по Созданию Эффекта Выделения с Помощью Событий | Microsoft Docs"
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
  - "цвета элементов, изменение"
  - "эффект выделения"
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Инструкция по Созданию Эффекта Выделения с Помощью Событий
В этом примере демонстрируется изменение цвета элемента, как только указатель мыши входит и покидает область, занимаемую элементом.  
  
 Этот пример состоит из файла [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и файла кода программной части.  
  
> [!NOTE]
>  Этот пример демонстрирует, как использовать события, но рекомендуемым способом добиться этого же эффекта является использование <xref:System.Windows.Trigger> в стиле.  Дополнительные сведения см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## Пример  
 Следующий [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создает интерфейс пользователя, который состоит из <xref:System.Windows.Controls.Border> окружающего <xref:System.Windows.Controls.TextBlock>, и присоединяет обработчики событий <xref:System.Windows.Input.Mouse.MouseEnter> и <xref:System.Windows.UIElement.MouseLeave> к <xref:System.Windows.Controls.Border>.  
  
 [!code-xml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Следующий код создает обработчики событий <xref:System.Windows.UIElement.MouseEnter> и <xref:System.Windows.UIElement.MouseLeave>.  Когда указатель мыши входит в <xref:System.Windows.Controls.Border>, фон <xref:System.Windows.Controls.Border> изменяется на красный.  Когда указатель мыши покидает <xref:System.Windows.Controls.Border>, фон <xref:System.Windows.Controls.Border> изменяется обратно на белый.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]