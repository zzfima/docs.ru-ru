---
title: Практическое руководство. Изменение цвета элемента с помощью событий фокуса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 5c59dc5f2f8f26fac69933f9ef641a3a51306619
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004834"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>Практическое руководство. Изменение цвета элемента с помощью событий фокуса
В этом примере показано, как изменить цвет элемента при получении и потере фокуса с помощью событий <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus>.  
  
 Этот пример состоит из файла [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и файла кода программной части.  
  
## <a name="example"></a>Пример  
 Следующий код XAML создает пользовательский интерфейс, состоящий из двух объектов <xref:System.Windows.Controls.Button>, и присоединяет обработчики событий <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus> к объектам <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 Следующий программный код создает обработчики событий <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus>.  Когда <xref:System.Windows.Controls.Button> получает фокус клавиатуры, <xref:System.Windows.Controls.Control.Background%2A> из <xref:System.Windows.Controls.Button> меняется на красный.  Когда <xref:System.Windows.Controls.Button> теряет фокус клавиатуры, <xref:System.Windows.Controls.Control.Background%2A> из <xref:System.Windows.Controls.Button> меняется обратно на белый.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о входных данных](input-overview.md)
