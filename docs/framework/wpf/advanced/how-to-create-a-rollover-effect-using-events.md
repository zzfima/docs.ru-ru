---
title: Практическое руководство. Создание эффекта выделения с помощью событий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 3996a3b9bb976dd5f2e5b675de3894bbaba7d9d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960389"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Практическое руководство. Создание эффекта выделения с помощью событий
В этом примере показано, как изменить цвет элемента, когда указатель мыши попадает в область, занимаемую элементом.  
  
 Этот пример состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файла и файла кода программной части.  
  
> [!NOTE]
> В этом примере показано, как использовать события, но рекомендуемым способом добиться такого же результата является использование <xref:System.Windows.Trigger> в стиле. Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../controls/styling-and-templating.md).  
  
## <a name="example"></a>Пример  
 Следующий пример [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создает пользовательский интерфейс, состоящий из <xref:System.Windows.UIElement.MouseLeave> <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.TextBlock>, и <xref:System.Windows.Controls.Border>присоединяет <xref:System.Windows.Input.Mouse.MouseEnter> обработчики событий и к.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Следующий программный код создает <xref:System.Windows.UIElement.MouseEnter> обработчики событий и. <xref:System.Windows.UIElement.MouseLeave>  Когда указатель мыши попадает в <xref:System.Windows.Controls.Border>, фон <xref:System.Windows.Controls.Border> элемента изменяется на красный.  Когда указатель мыши покидает <xref:System.Windows.Controls.Border>, фон <xref:System.Windows.Controls.Border> изменяется обратно на белый.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
