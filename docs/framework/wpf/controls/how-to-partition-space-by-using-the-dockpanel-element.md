---
title: "Практическое руководство. Разделение пространства с помощью элемента DockPanel | Microsoft Docs"
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
  - "элементы управления [WPF], DockPanel"
  - "DockPanel - элемент управления, разделение пространства"
  - "разделение пространства"
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Разделение пространства с помощью элемента DockPanel
В следующем примере создается простая структура [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] с помощью элемента <xref:System.Windows.Controls.DockPanel>.  Элемент <xref:System.Windows.Controls.DockPanel> разделяет доступное пространство между его дочерними элементами.  
  
## Пример  
 В этом примере используется свойство <xref:System.Windows.Controls.DockPanel.Dock%2A>, являющееся [вложенным свойством](GTMT), чтобы прикрепить два идентичных элемента <xref:System.Windows.Controls.Border> к <xref:System.Windows.Controls.Dock> разделенного пространства.  Третий элемент <xref:System.Windows.Controls.Border> присоединяется к <xref:System.Windows.Controls.Dock> с шириной 200 пикселей.  Четвертый элемент <xref:System.Windows.Controls.Border> присоединяется к <xref:System.Windows.Controls.Dock> экрана.  Последний элемент <xref:System.Windows.Controls.Border> автоматически заполняет оставшееся пространство.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  По умолчанию последний дочерний элемент <xref:System.Windows.Controls.DockPanel> заполняет оставшееся незанятое пространство.  Если в этом нет необходимости, следует задать `LastChildFill="False"`.  
  
 Скомпилированное приложение возвращает новый пользовательский интерфейс, выглядящий следующим образом.  
  
 ![Обычный сценарий DockPanel.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.png "panel\_intro\_dockpanel")  
  
## См. также  
 <xref:System.Windows.Controls.DockPanel>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)