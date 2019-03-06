---
title: Пошаговое руководство. Размещение элемента управления Windows Forms в WPF с помощью XAML
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 1566f27703e2603a5d70cf8cfc7a01a08c407f6a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379540"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>Пошаговое руководство. Размещение элемента управления Windows Forms в WPF с помощью XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет множество элементов управления с богатым набором функций. Тем не менее, иногда можно использовать [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страниц. Например, может получить значительные преимущества в существующих [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления, или имеете [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления, предоставляющий уникальную функциональность.  
  
 В этом пошаговом руководстве показано, как разместить форм Windows <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Полный пример кода для задач, демонстрируемых в этом пошаговом руководстве, см. в разделе [размещение элемента управления Windows Forms в WPF с помощью XAML примером](https://go.microsoft.com/fwlink/?LinkID=160000).  
  
## <a name="prerequisites"></a>Предварительные требования  

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.  
  
## <a name="hosting-the-windows-forms-control"></a>Размещение элемента управления Windows Forms  
  
#### <a name="to-host-the-maskedtextbox-control"></a>Чтобы разместить элемент управления MaskedTextBox, выполните следующие действия.  
  
1.  Создание проекта приложения WPF с именем `HostingWfInWpfWithXaml`.  
  
2.  Добавьте ссылки на следующие сборки.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms.  
  
3.  Откройте файл MainWindow.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  В <xref:System.Windows.Window> элемента, добавьте следующее сопоставление пространства имен. `wf` Сопоставление пространства имен устанавливает ссылку на сборку, содержащую элемент управления Windows Forms.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  В <xref:System.Windows.Controls.Grid> элемент добавьте следующий XAML.  
  
     <xref:System.Windows.Forms.MaskedTextBox> Элемент управления создается в качестве дочернего элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента управления.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Пошаговое руководство: Размещение элемента управления Windows Forms в WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Пошаговое руководство: Размещение Windows Forms составного элемента управления в WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Элементы управления Windows Forms и эквивалентные элементы управления WPF](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Размещение элемента управления Windows Forms в WPF с помощью примера XAML](https://go.microsoft.com/fwlink/?LinkID=160000)
