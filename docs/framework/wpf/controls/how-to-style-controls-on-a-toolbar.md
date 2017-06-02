---
title: "Практическое руководство. Определение стиля элементов управления на панели инструментов | Microsoft Docs"
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
  - "настройка элементов управления в панели инструментов"
  - "стили элементов управления в панели инструментов"
  - "панели инструментов"
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Определение стиля элементов управления на панели инструментов
В классе <xref:System.Windows.Controls.ToolBar> определяются объекты <xref:System.Windows.ResourceKey>, задающие стиль элементов управления, представленных на объекте <xref:System.Windows.Controls.ToolBar>.  Чтобы задать стиль элемента управления на объекте <xref:System.Windows.Controls.ToolBar>, установите для атрибута стиля `x:key` значение <xref:System.Windows.ResourceKey>, определенное в классе <xref:System.Windows.Controls.ToolBar>.  
  
 В классе <xref:System.Windows.Controls.ToolBar> определяются следующие объекты <xref:System.Windows.ResourceKey>:  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## Пример  
 В следующем примере определяются стили для элементов управления на <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xml[ToolBar_snip#ToolBarAllStyles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xml[ToolBar_snip#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## См. также  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)