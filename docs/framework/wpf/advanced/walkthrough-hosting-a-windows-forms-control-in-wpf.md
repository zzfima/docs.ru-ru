---
title: Пошаговое руководство. Размещение элементов управления Windows Forms в WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: af5a0d58e789e609a25aa828493a3b0722cc83e1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605472"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a>Пошаговое руководство. Размещение элементов управления Windows Forms в WPF

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет множество элементов управления с богатым набором функций. Тем не менее, иногда можно использовать [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страниц. Например, может получить значительные преимущества в существующих [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления, или имеете [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления, предоставляющий уникальную функциональность.

В этом пошаговом руководстве показано, как разместить [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы с помощью кода.

Полный пример кода для задач, демонстрируемых в этом пошаговом руководстве, см. в разделе [размещение элемента управления Windows Forms в WPF](https://go.microsoft.com/fwlink/?LinkID=160057).

## <a name="prerequisites"></a>Предварительные требования

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.

## <a name="hosting-the-windows-forms-control"></a>Размещение элемента управления Windows Forms

### <a name="to-host-the-maskedtextbox-control"></a>Чтобы разместить элемент управления MaskedTextBox, выполните следующие действия.

1. Создание проекта приложения WPF с именем `HostingWfInWpf`.

2. Добавьте ссылки на следующие сборки.

    - WindowsFormsIntegration

    - System.Windows.Forms.

3. Откройте файл MainWindow.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

4. Имя <xref:System.Windows.Controls.Grid> элемент `grid1`.

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. В представлении конструирования или XAML, выберите <xref:System.Windows.Window> элемент.

6. В окне «Свойства» щелкните **события** вкладки.

7. Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событий.

8. Вставьте следующий код для обработки <xref:System.Windows.FrameworkElement.Loaded> событий.

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. В верхней части файла, добавьте следующий код `Imports` или `using` инструкции.

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Пошаговое руководство: Размещение элемента управления Windows Forms в WPF с помощью XAML](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [Пошаговое руководство: Размещение Windows Forms составного элемента управления в WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Элементы управления Windows Forms и эквивалентные элементы управления WPF](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Пример размещения элемента управления Windows Forms в приложении WPF](https://go.microsoft.com/fwlink/?LinkID=160057)
