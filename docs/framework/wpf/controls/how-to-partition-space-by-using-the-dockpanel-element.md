---
title: "Практическое руководство. Разделение пространства с помощью элемента DockPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 056aeaf1dfb7db420ce5359849a9a409dcd3fe13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>Практическое руководство. Разделение пространства с помощью элемента DockPanel
В следующем примере создается простой [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework с помощью <xref:System.Windows.Controls.DockPanel> элемента. <xref:System.Windows.Controls.DockPanel> Разделяет доступное пространство его дочерним элементам.  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Windows.Controls.DockPanel.Dock%2A> свойство, которое является присоединенным свойством, чтобы прикрепить два идентичных <xref:System.Windows.Controls.Border> элементы <xref:System.Windows.Controls.Dock.Top> разделенного пространства. В третьем <xref:System.Windows.Controls.Border> элемент прикрепляется к <xref:System.Windows.Controls.Dock.Left>, с шириной 200 пикселей. Четвертый <xref:System.Windows.Controls.Border> прикрепляется к <xref:System.Windows.Controls.Dock.Bottom> экрана. Последний <xref:System.Windows.Controls.Border> элемент автоматически заполняет оставшееся пространство.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  По умолчанию, последний дочерний <xref:System.Windows.Controls.DockPanel> элемент заполняет оставшееся незанятое пространство. Если в этом нет необходимости, следует задать `LastChildFill="False"`.  
  
 Скомпилированное приложение возвращает новый пользовательский интерфейс, выглядящий следующим образом.  
  
 ![Обычный сценарий DockPanel.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.DockPanel>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
