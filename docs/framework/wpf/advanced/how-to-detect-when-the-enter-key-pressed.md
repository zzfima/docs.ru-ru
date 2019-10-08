---
title: Практическое руководство. Обнаружить нажатие клавиши ВВОД
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: e2337826077c836696937f91541d6d261f1270aa
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004820"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Практическое руководство. Обнаружить нажатие клавиши ВВОД
В этом примере показано, как обнаружить нажатие клавиши <xref:System.Windows.Input.Key.Enter> на клавиатуре.  
  
 Этот пример состоит из файла [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и файла кода программной части.  
  
## <a name="example"></a>Пример  
 Когда пользователь нажимает клавишу <xref:System.Windows.Input.Key.Enter> в <xref:System.Windows.Controls.TextBox>, входные данные в текстовом поле появляется в другой области [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 Следующий код XAML создает пользовательский интерфейс, состоящий из <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Следующий программный код создает обработчик событий <xref:System.Windows.UIElement.KeyDown>.  Если нажата клавиша <xref:System.Windows.Input.Key.Enter>, в <xref:System.Windows.Controls.TextBlock> отображается сообщение.  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о входных данных](input-overview.md)
- [Общие сведения о перенаправленных событиях](routed-events-overview.md)
