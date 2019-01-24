---
title: Как выполнить Изменение цвета элемента с помощью событий фокуса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: ad5ba8490f4b98512d539f5ae9c72b03333aca69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547018"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>Как выполнить Изменение цвета элемента с помощью событий фокуса
В этом примере показано, как изменение цвета элемента, когда он получает и теряет фокус с помощью <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus> события.  
  
 В этом примере состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл и файл с выделенным кодом.  
  
## <a name="example"></a>Пример  
 Следующие [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создает пользовательский интерфейс, который состоит из двух <xref:System.Windows.Controls.Button> объектов, а также присоединяет обработчики событий для <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus> событий <xref:System.Windows.Controls.Button> объектов.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 Следующий код создает <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus> обработчики событий.  Когда <xref:System.Windows.Controls.Button> прирост фокус <xref:System.Windows.Controls.Control.Background%2A> из <xref:System.Windows.Controls.Button> изменяется на красный.  Когда <xref:System.Windows.Controls.Button> теряет фокус клавиатуры, <xref:System.Windows.Controls.Control.Background%2A> из <xref:System.Windows.Controls.Button> изменяется обратно на белое.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)
