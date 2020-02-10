---
title: Размещение элемента управления Windows Forms в WPF с помощью XAML
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 99c077801a26043e17e0d51ecc0a97b9608784c0
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095064"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF с помощью XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет множество элементов управления с богатым набором функций. Однако иногда может потребоваться использовать Windows Forms элементы управления на страницах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Например, у вас может быть существенный вклад в существующие элементы управления Windows Forms или имеется элемент управления Windows Forms, обеспечивающий уникальную функциональность.  
  
 В этом пошаговом руководстве показано, как разместить элемент управления Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> на странице [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Полный листинг кода задач, приведенных в этом пошаговом руководстве, см. в разделе [Размещение элемента управления Windows Forms в WPF с помощью примера XAML](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).
  
## <a name="prerequisites"></a>предварительные требования  

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.  
  
## <a name="hosting-the-windows-forms-control"></a>Размещение элемента управления Windows Forms  
  
#### <a name="to-host-the-maskedtextbox-control"></a>Чтобы разместить элемент управления MaskedTextBox, выполните следующие действия.  
  
1. Создайте проект приложения WPF с именем `HostingWfInWpfWithXaml`.  
  
2. Добавьте ссылки на следующие сборки.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. Откройте файл MainWindow. XAML в конструкторе WPF.  
  
4. В элементе <xref:System.Windows.Window> добавьте следующее сопоставление пространства имен. Сопоставление пространства имен `wf` устанавливает ссылку на сборку, содержащую элемент управления Windows Forms.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. В элемент <xref:System.Windows.Controls.Grid> добавьте следующий код XAML.  
  
     Элемент управления <xref:System.Windows.Forms.MaskedTextBox> создается как дочерний элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. Нажмите клавишу F5, чтобы создать и запустить приложение.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Элементы управления Windows Forms и эквивалентные элементы управления WPF](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Размещение элемента управления Windows Forms в WPF с помощью примера XAML](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)
