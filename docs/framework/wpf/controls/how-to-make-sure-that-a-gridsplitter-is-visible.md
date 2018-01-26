---
title: "Как проверить видимость GridSplitter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b7587a093b2b43856a05693bb785a0465211782
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>Как проверить видимость GridSplitter
В этом примере показано, как убедитесь, что <xref:System.Windows.Controls.GridSplitter> управления не скрыты другими элементами управления в <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Controls.Panel.Children%2A> Из <xref:System.Windows.Controls.Grid> управления подготавливаются к просмотру в том порядке, в котором они определены в разметке или коде. <xref:System.Windows.Controls.GridSplitter>элементы управления можно скрыть, другие элементы управления, если не назначить их последними элементами в <xref:System.Windows.Controls.Panel.Children%2A> коллекции или задать для других элементов более высокое <xref:System.Windows.Controls.Panel.ZIndexProperty>.  
  
 Чтобы предотвратить скрытые <xref:System.Windows.Controls.GridSplitter> элементов управления, выполните одно из следующих действий.  
  
-   Убедитесь, что <xref:System.Windows.Controls.GridSplitter> элементы управления — это последний <xref:System.Windows.Controls.Panel.Children%2A> добавлены <xref:System.Windows.Controls.Grid>. В следующем примере показан <xref:System.Windows.Controls.GridSplitter> как последний элемент в <xref:System.Windows.Controls.Panel.Children%2A> коллекцию <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   Задать <xref:System.Windows.Controls.Panel.ZIndexProperty> на <xref:System.Windows.Controls.GridSplitter> будет больше, чем элемент управления, в противном случае будет скрыть. Следующий пример предоставляет <xref:System.Windows.Controls.GridSplitter> управления более высокий <xref:System.Windows.Controls.Panel.ZIndexProperty> чем <xref:System.Windows.Controls.Button> элемента управления.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   Установка полей элемента управления, в противном случае скроет <xref:System.Windows.Controls.GridSplitter> , чтобы <xref:System.Windows.Controls.GridSplitter> предоставляется. В следующем примере задается поля на элемент управления, в противном случае будет наложения и скрыть <xref:System.Windows.Controls.GridSplitter>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.GridSplitter>  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
