---
title: Пошаговое руководство. Размещение элемента управления ActiveX в приложении WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: c8cbc2cb60e4afce4bcb35cf1fe645068a452b1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>Пошаговое руководство. Размещение элемента управления ActiveX в приложении WPF
Для улучшенного взаимодействия с браузерами, можно использовать [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] элементы управления в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложения. В этом пошаговом руководстве показано, как разместить [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] как элемент управления на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание проекта.  
  
-   Создание элемента управления ActiveX.  
  
-   Размещение элемента управления ActiveX на странице WPF.  
  
 По завершении данного пошагового руководства будет понять, как использовать [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] элементы управления в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложения.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] установлен на компьютере, где установлена среда Visual Studio.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="creating-the-project"></a>Создание проекта  
  
#### <a name="to-create-and-set-up-the-project"></a>Создание и настройка проекта  
  
1.  Создание проекта приложения WPF с именем `HostingAxInWpf`.  
  
2.  Добавьте в решение проект библиотеки элементов управления Windows Forms и назовите проект `WmpAxLib`.  
  
3.  В проекте WmpAxLib добавьте ссылку на сборку проигрыватель Windows Media, которая называется wmp.dll.  
  
4.  Откройте **элементов**.  
  
5.  Щелкните правой кнопкой мыши **элементов**, а затем нажмите кнопку **Выбор элементов**.  
  
6.  Нажмите кнопку **COM-компоненты** выберите **проигрыватель Windows Media** управления и нажмите кнопку **ОК**.  
  
     Добавляемый элемент управления Windows Media Player **элементов**.  
  
7.  В обозревателе решений щелкните правой кнопкой мыши **UserControl1** файла и нажмите кнопку **переименование**.  
  
8.  Измените имя на `WmpAxControl.vb` или `WmpAxControl.cs`, в зависимости от языка.  
  
9. Если вы получили запрос на переименование всех ссылок, нажмите кнопку **Да**.  
  
## <a name="creating-the-activex-control"></a>Создание элемента управления ActiveX  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] автоматически создает <xref:System.Windows.Forms.AxHost> класс-оболочку для [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] управления, когда элемент управления добавляется в рабочую область конструирования. В следующей процедуре создается управляемая сборка с именем AxInterop.WMPLib.dll.  
  
#### <a name="to-create-the-activex-control"></a>Создание элемента управления ActiveX  
  
1.  Откройте WmpAxControl.vb или WmpAxControl.cs в конструкторе Windows Forms.  
  
2.  Из **элементов**, добавьте элемент управления проигрывателя Windows Media в область конструктора.  
  
3.  В окне свойств установите для параметра управления проигрывателя Windows Media <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Fill>.  
  
4.  Постройте проект библиотеки элементов управления WmpAxLib.  
  
## <a name="hosting-the-activex-control-on-a-wpf-page"></a>Размещение элемента управления ActiveX в страницу WPF  
  
#### <a name="to-host-the-activex-control"></a>Чтобы разместить элемент управления ActiveX  
  
1.  В проекте HostingAxInWpf добавьте ссылку на созданный [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] сборки взаимодействия.  
  
     Эта сборка имеет имя AxInterop.WMPLib.dll и добавлен папка отладки проекта WmpAxLib при импорте управления проигрывателя Windows Media.  
  
2.  Добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration.dll.  
  
3.  Добавьте ссылку на [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сборку, которая называется System.Windows.Forms.dll.  
  
4.  Откройте файл MainWindow.xaml в конструкторе WPF.  
  
5.  Имя <xref:System.Windows.Controls.Grid> элемент `grid1`.  
  
     [!code-xaml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  В режиме конструктора или XAML, выберите <xref:System.Windows.Window> элемент.  
  
7.  В окне «Свойства» щелкните **события** вкладки.  
  
8.  Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событий.  
  
9. Вставьте следующий код для обработки <xref:System.Windows.FrameworkElement.Loaded> событий.  
  
     Этот код создает экземпляр <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления и добавляет экземпляр `AxWindowsMediaPlayer` элемента управления в качестве дочернего.  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Конструктор WPF](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
