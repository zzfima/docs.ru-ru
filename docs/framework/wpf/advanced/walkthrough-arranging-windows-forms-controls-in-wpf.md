---
title: "Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF"
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
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 480d61f6ca2aa67e0de48030655a6368c70554f4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF
В этом пошаговом руководстве показано, как использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] возможностей компоновки для размещения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления в гибридных приложениях.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание проекта.  
  
-   Использование параметров макета по умолчанию.  
  
-   Изменение размеров в зависимости от содержимого.  
  
-   Использование абсолютного позиционирования.  
  
-   Задание размера явным образом.  
  
-   Установка свойств макета.  
  
-   Описание ограничений z-порядка.  
  
-   Закрепление.  
  
-   Задание видимости.  
  
-   Размещение нерастягиваемых элементов управления.  
  
-   Масштабирование.  
  
-   Поворот.  
  
-   Задание полей и внутренних полей.  
  
-   Использование динамических контейнеров макета.  
  
 Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [упорядочение элементов управления Windows Forms в образце WPF](http://go.microsoft.com/fwlink/?LinkID=159971).  
  
 По завершении вы получите представление о [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] возможности разметки в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложений на основе.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="creating-the-project"></a>Создание проекта  
  
#### <a name="to-create-and-set-up-the-project"></a>Создание и настройка проекта  
  
1.  Создание проекта приложения WPF с именем `WpfLayoutHostingWf`.  
  
2.  В обозревателе решений добавьте ссылки на следующие сборки.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms.  
  
    -   System.Drawing;  
  
3.  Дважды щелкните файл MainWindow.xaml, чтобы открыть его в представлении XAML.  
  
4.  В <xref:System.Windows.Window> элемента, добавьте следующий [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставление пространства имен.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  В <xref:System.Windows.Controls.Grid> элемент набора <xref:System.Windows.Controls.Grid.ShowGridLines%2A> свойства `true` и определите пять строк и три столбца.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a>Использование параметров макета по умолчанию  
 По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент обрабатывает макет для размещаемого [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.  
  
#### <a name="to-use-default-layout-settings"></a>Использование параметров макета по умолчанию  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> Элемент управления отображается в <xref:System.Windows.Controls.Canvas>. Размещенного элемента управления изменяется в зависимости от содержимого и <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента изменяются, чтобы вместить размещенного элемента управления.  
  
## <a name="sizing-to-content"></a>Изменение размеров в зависимости от содержимого  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент гарантирует, что размещенного элемента управления имеет размер для правильного отображения ее содержимого.  
  
#### <a name="to-size-to-content"></a>Изменение размеров в соответствии с содержимым  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Два новых элемента управления button изменяется для отображения длинных строк текста и размера шрифта правильно и <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементов изменяется, чтобы вместить размещаемые элементы управления.  
  
## <a name="using-absolute-positioning"></a>Использование абсолютного позиционирования  
 Абсолютное позиционирование используется для размещения <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент в любом месте в пользовательском интерфейсе (UI).  
  
#### <a name="to-use-absolute-positioning"></a>Использование абсолютного позиционирования  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент помещается 20 пикселей от верхнего края ячейки сетки и 20 пикселей от левого края.  
  
## <a name="specifying-size-explicitly"></a>Задание размера явным образом  
 Можно указать размер <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента с помощью <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства.  
  
#### <a name="to-specify-size-explicitly"></a>Задание размера явным образом  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент имеет значение 50 пикселей в ширину 70 пикселей в высоту, размер которой меньше, чем параметры макета по умолчанию. Содержимое [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления упорядочивается соответствующим образом.  
  
## <a name="setting-layout-properties"></a>Установка свойств макета  
 Всегда задавать свойства, связанные с макетом размещенного элемента управления, с помощью свойств <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента. При установке свойств макета непосредственно для размещаемого элемента управления результат не будет соответствовать ожидаемому.  
  
 Установка свойства, связанные с макетом размещенного элемента управления в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не делает ничего.  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>Чтобы увидеть влияние задания свойств размещаемого элемента управления  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  В обозревателе решений дважды щелкните файл MainWindow.xaml. vb или MainWindow.xaml.cs, чтобы открыть его в редакторе кода.  
  
3.  Скопируйте следующий код в `MainWindow` определения класса.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
5.  Нажмите кнопку **Click me** кнопки. `button1_Click` Задает обработчик событий <xref:System.Windows.Forms.Control.Top%2A> и <xref:System.Windows.Forms.Control.Left%2A> свойства размещенным элементом управления. В результате размещенного элемента управления изменять внутри <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента. Ведущий элемент занимает то же пространство на экране, но размещаемый элемент управления обрезается. Вместо этого размещаемый элемент управления должен всегда заполнять <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.  
  
## <a name="understanding-z-order-limitations"></a>Описание ограничений z-порядка  
 По умолчанию отображается <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементы всегда рисуются поверх других [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементы и они не подвержены влиянию z порядка. Чтобы включить z порядка, задайте <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost> значение true и <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> свойства <xref:System.Windows.Interop.CompositionMode.Full> или <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### <a name="to-see-the-default-z-order-behavior"></a>Просмотр ограничений z-порядка  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент рисуется через элемент label.  
  
#### <a name="to-see-the-z-order-behavior-when-isredirected-is-true"></a>Чтобы увидеть поведение z порядка, когда свойству IsRedirected присвоено значение "true"  
  
1.  Замените следующий код XAML в предыдущем примере z порядка.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#8b)]  
  
     Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Элемент label рисуется через <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.  
  
## <a name="docking"></a>Закрепление  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>поддерживает элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] закрепления. Задать <xref:System.Windows.Controls.DockPanel.Dock%2A> вложенное свойство, чтобы закрепить размещенного элемента управления в <xref:System.Windows.Controls.DockPanel> элемент.  
  
#### <a name="to-dock-a-hosted-control"></a>Закрепление размещаемого элемента управления  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент закреплен в правую часть <xref:System.Windows.Controls.DockPanel> элемента.  
  
## <a name="setting-visibility"></a>Задание видимости  
 Можно сделать ваш [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления невидимым или свернуть его, задав <xref:System.Windows.UIElement.Visibility%2A> свойства <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента. Если элемент управления невидим, он не отображается, но при этом занимает пространство разметки. Если элемент управления свернут, он не отображается и не занимает пространство разметки.  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a>Задание видимости размещаемого элемента управления  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
4.  Нажмите кнопку **щелкните, чтобы сделать невидимыми** кнопку, чтобы <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент невидимым.  
  
5.  Нажмите кнопку **щелкните, чтобы свернуть** кнопку, чтобы скрыть <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент из макета полностью. Когда [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления свернут, соседние элементы переупорядочиваются, чтобы занять его место.  
  
## <a name="hosting-a-control-that-does-not-stretch"></a>Размещение нерастягиваемых элементов управления  
 Некоторые [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления имеют фиксированный размер и не растягиваются для заполнения доступного места в макете. Например <xref:System.Windows.Forms.MonthCalendar> элемент управления отображает месяц в фиксированное пространство.  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a>Размещение нерастягиваемого элемента управления  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемента выравнивается по центру в строке сетки, но она не растягивается для заполнения всего доступного пространства. Если окно является достаточно большим, можно увидеть два или более месяцев, отображаемых размещаемым <xref:System.Windows.Forms.MonthCalendar> элемента управления, но они выравниваются по центру в строке. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Обработчик макетов Центрирование элементов, которые не меняются для заполнения всего доступного пространства.  
  
## <a name="scaling"></a>Масштабирование  
 В отличие от [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов, большинство [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления не являются непрерывно масштабируемыми. По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент масштабирует ее размещенного элемента управления, когда это возможно.  Чтобы включить полноценные масштабирование, задайте <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost> значение true и <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> свойства <xref:System.Windows.Interop.CompositionMode.Full> или <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>Масштабирование размещаемого элемента управления с помощью поведения по умолчанию  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Размещаемый элемент управления и его окружающие элементы масштабируются с коэффициентом 0,5. Но шрифт размещаемого элемента управления не масштабируется.  
  
#### <a name="to-scale-a-hosted-control-by-setting-isredirected-to-true"></a>Масштабирование размещаемого элемента управления с помощью установки для свойства IsRedirected значения "true"  
  
1.  Замените следующий код XAML в предыдущем примере масштабирования.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#12b)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Шрифт размещаемого элемента управления, его окружающих элементов и вложенных в него элементов масштабируется с коэффициентом 0,5.  
  
## <a name="rotating"></a>Поворот  
 В отличие от [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления не поддерживают поворот. По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент не поворачивается вместе с другими [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементы, когда применяется преобразование поворота. Значение поворота, отличное от 180 градусов, вызывает <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> событий.  Чтобы включить на любой угол поворота, задайте <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost> значение true и <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> свойства <xref:System.Windows.Interop.CompositionMode.Full> или <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>Чтобы увидеть эффект от поворота в гибридном приложении  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Размещаемый элемент управления не повернут, но его соседние элементы повернуты на угол в 180 градусов. Для отображения элементов может потребоваться изменить размер окна.  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application-when-isredirected-is-true"></a>Чтобы увидеть эффект от поворота в гибридном приложении, когда для свойства IsRedirected задано значение "true"  
  
1.  Замените следующий код XAML в предыдущем примере поворота.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#13b)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Размещаемый элемент повернут.  Обратите внимание, что <xref:System.Windows.Media.RotateTransform.Angle%2A> свойство может быть присвоено любое значение. Для отображения элементов может потребоваться изменить размер окна.  
  
## <a name="setting-padding-and-margins"></a>Задание отбивки и внутренних полей  
 Заполнение и поля в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макета аналогичны отступы и рамки, в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Просто установите <xref:System.Windows.Controls.Control.Padding%2A> и <xref:System.Windows.FrameworkElement.Margin%2A> свойства <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>Задание отбивки и внутренних полей размещаемого элемента управления  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Параметры поля и заполнение применяются к размещаемым [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления таким же образом, как они будут применяться в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
## <a name="using-dynamic-layout-containers"></a>Использование динамических контейнеров макета  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]предусмотрены два типа контейнеров динамического макета, <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel>. Можно также использовать эти контейнеры в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макеты.  
  
#### <a name="to-use-a-dynamic-layout-container"></a>Использование динамических контейнеров макета  
  
1.  Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  Добавьте вызов `InitializeFlowLayoutPanel` в конструкторе.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Заполняет элемент <xref:System.Windows.Controls.DockPanel>, и <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает его дочерние элементы в значение по умолчанию <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Конструктор WPF](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Вопросы, связанные с макетом элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [Элементы управления упорядочение Windows Forms в образце WPF](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
