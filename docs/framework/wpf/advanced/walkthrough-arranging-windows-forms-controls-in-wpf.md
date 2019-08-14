---
title: Пошаговое руководство. Упорядочение элементов управления Windows Forms в WPF
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: fa0181e95a03324c4cfa9395ae57439c260d1c23
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972309"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Пошаговое руководство. Упорядочение элементов управления Windows Forms в WPF

В этом пошаговом руководстве показано [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , как использовать функции [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] макета для упорядочения элементов управления в гибридном приложении.

В данном пошаговом руководстве представлены следующие задачи.

- Создание проекта.

- Использование параметров макета по умолчанию.

- Изменение размеров в зависимости от содержимого.

- Использование абсолютного позиционирования.

- Задание размера явным образом.

- Установка свойств макета.

- Описание ограничений z-порядка.

- Закрепление.

- Задание видимости.

- Размещение нерастягиваемых элементов управления.

- Масштабирование.

- Поворот.

- Задание полей и внутренних полей.

- Использование динамических контейнеров макета.

Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [Размещение элементов управления Windows Forms в WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).

По завершении вы получите представление о [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] функциях макета в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]приложениях на основе.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.

## <a name="creating-the-project"></a>Создание проекта

### <a name="to-create-and-set-up-the-project"></a>Создание и настройка проекта

1. Создайте проект приложения WPF с именем `WpfLayoutHostingWf`.

2. В обозревателе решений добавьте ссылки на следующие сборки.

    - WindowsFormsIntegration

    - System.Windows.Forms.

    - System.Drawing;

3. Дважды щелкните файл MainWindow.xaml, чтобы открыть его в представлении XAML.

4. В элементе добавьте следующее [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставление пространства имен. <xref:System.Windows.Window>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. В элементе задайте для`true` свойства значение и определите пять строк и три столбца. <xref:System.Windows.Controls.Grid.ShowGridLines%2A> <xref:System.Windows.Controls.Grid>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a>Использование параметров макета по умолчанию

По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент обрабатывает макет для размещенного [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.

### <a name="to-use-default-layout-settings"></a>Использование параметров макета по умолчанию

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Элемент управления появится в<xref:System.Windows.Controls.Canvas>. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> Размер размещаемого элемента управления зависит от его содержимого, и <xref:System.Windows.Forms.Integration.WindowsFormsHost> размер элемента изменяется в соответствии с размещаемым элементом управления.

## <a name="sizing-to-content"></a>Изменение размеров в зависимости от содержимого

<xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент гарантирует, что размещаемый элемент управления будет иметь размер для правильного вывода его содержимого.

### <a name="to-size-to-content"></a>Изменение размеров в соответствии с содержимым

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Два новых элемента управления "Кнопка" имеют размеры, чтобы правильно отображать более длинную текстовую строку и больший <xref:System.Windows.Forms.Integration.WindowsFormsHost> размер шрифта, а размеры элементов изменялись в соответствии с размещаемыми элементами управления.

## <a name="using-absolute-positioning"></a>Использование абсолютного позиционирования

Можно использовать абсолютное позиционирование для размещения <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента в любом месте пользовательского интерфейса.

### <a name="to-use-absolute-positioning"></a>Использование абсолютного позиционирования

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент размещается на 20 пикселях с верхней стороны ячейки сетки и на 20 пикселях слева.

## <a name="specifying-size-explicitly"></a>Задание размера явным образом

Размер <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента можно указать <xref:System.Windows.FrameworkElement.Width%2A> с помощью свойств и <xref:System.Windows.FrameworkElement.Height%2A> .

### <a name="to-specify-size-explicitly"></a>Задание размера явным образом

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Для <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента задается размер в 50 пикселей в ширину на 70 пикселей высотой, что меньше, чем параметры макета по умолчанию. Содержимое [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления упорядочивается соответствующим образом.

## <a name="setting-layout-properties"></a>Установка свойств макета

Всегда устанавливайте связанные с макетом свойства размещаемого элемента управления с помощью свойств <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента. При установке свойств макета непосредственно для размещаемого элемента управления результат не будет соответствовать ожидаемому.

 Установка свойств, связанных с макетом, для размещенного элемента управления в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не оказывает никакого влияния.

### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>Чтобы увидеть влияние задания свойств размещаемого элемента управления

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. В обозревателе решений дважды щелкните файл MainWindow.xaml. vb или MainWindow.xaml.cs, чтобы открыть его в редакторе кода.

3. Скопируйте следующий код в `MainWindow` определение класса.

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.

5. Нажмите кнопку " **щелкните мне** ". Обработчик событий задает свойства <xref:System.Windows.Forms.Control.Left%2A>идля размещаемого элемента управления. <xref:System.Windows.Forms.Control.Top%2A> `button1_Click` В результате размещаемый элемент управления будет перемещен в пределах <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента. Ведущий элемент занимает то же пространство на экране, но размещаемый элемент управления обрезается. Вместо этого размещаемый элемент управления всегда должен заполнять <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент.

## <a name="understanding-z-order-limitations"></a>Описание ограничений z-порядка

Видимые <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементы всегда рисуются поверх других элементов WPF и не зависят от z-порядка. Чтобы увидеть это поведение z-порядка, выполните следующие действия.

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент зарисовывается поверх элемента Label.

## <a name="docking"></a>Закрепление

<xref:System.Windows.Forms.Integration.WindowsFormsHost>элемент поддерживает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] закрепление. Задайте присоединенное свойство, чтобы закрепить размещенный <xref:System.Windows.Controls.DockPanel> элемент управления в элементе. <xref:System.Windows.Controls.DockPanel.Dock%2A>

### <a name="to-dock-a-hosted-control"></a>Закрепление размещаемого элемента управления

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Элемент закреплен с правой стороны <xref:System.Windows.Controls.DockPanel> элемента. <xref:System.Windows.Forms.Integration.WindowsFormsHost>

## <a name="setting-visibility"></a>Задание видимости

Можно сделать [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемент управления невидимым или свернуть его, <xref:System.Windows.UIElement.Visibility%2A> задав свойство для <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента. Если элемент управления невидим, он не отображается, но при этом занимает пространство разметки. Если элемент управления свернут, он не отображается и не занимает пространство разметки.

### <a name="to-set-the-visibility-of-a-hosted-control"></a>Задание видимости размещаемого элемента управления

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.

4. Нажмите кнопку " **щелкните, чтобы сделать** невидимой <xref:System.Windows.Forms.Integration.WindowsFormsHost> кнопку", чтобы сделать элемент невидимым.

5. Нажмите кнопку " **щелкните, чтобы свернуть** ", <xref:System.Windows.Forms.Integration.WindowsFormsHost> чтобы полностью скрыть элемент в макете. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Когда элемент управления сворачивается, окружающие его элементы переупорядочиваются, чтобы занять свое пространство.

## <a name="hosting-a-control-that-does-not-stretch"></a>Размещение нерастягиваемых элементов управления

Некоторые [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления имеют фиксированный размер и не растягиваются для заполнения доступного пространства в макете. Например, <xref:System.Windows.Forms.MonthCalendar> элемент управления отображает месяц в фиксированном пространстве.

### <a name="to-host-a-control-that-does-not-stretch"></a>Размещение нерастягиваемого элемента управления

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент выравнивается по центру в строке сетки, но не растягивается для заполнения доступного пространства. Если окно достаточно велико, можно увидеть два или больше месяцев, отображаемых размещаемым <xref:System.Windows.Forms.MonthCalendar> элементом управления, но они центрируются по строке. Обработчик [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макетов выравнивает элементы, размер которых не может быть заполнять доступное пространство.

## <a name="scaling"></a>Масштабирование

В отличие от элементов WPF, большинство элементов управления Windows Forms не постоянно масштабируемыми. Чтобы обеспечить настраиваемое масштабирование, необходимо <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> переопределить метод.

### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>Масштабирование размещаемого элемента управления с помощью поведения по умолчанию

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Размещаемый элемент управления и его окружающие элементы масштабируются с коэффициентом 0,5. Но шрифт размещаемого элемента управления не масштабируется.

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>Поворот

В отличие от элементов WPF, Windows Forms элементы управления не поддерживают вращение. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент не поворачивается с другими элементами WPF при применении преобразования поворота. Любое значение вращения, отличное от 180 градусов, <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> вызывает событие.

### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>Чтобы увидеть эффект от поворота в гибридном приложении

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Размещаемый элемент управления не повернут, но его соседние элементы повернуты на угол в 180 градусов. Для отображения элементов может потребоваться изменить размер окна.

## <a name="setting-padding-and-margins"></a>Задание отбивки и внутренних полей

Заполнение и поля в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макете похожи на заполнение и поля в. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Просто задайте <xref:System.Windows.Controls.Control.Padding%2A> свойства и <xref:System.Windows.FrameworkElement.Margin%2A> для <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.

### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>Задание отбивки и внутренних полей размещаемого элемента управления

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Параметры заполнения и поля применяются к размещаемым [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементам управления так же, как и в. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]

## <a name="using-dynamic-layout-containers"></a>Использование динамических контейнеров макета

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]предоставляет два динамических контейнера макета: <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel>. Эти контейнеры также можно использовать в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макетах.

### <a name="to-use-a-dynamic-layout-container"></a>Использование динамических контейнеров макета

1. Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. Добавьте вызов метода `InitializeFlowLayoutPanel` в конструкторе.

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Элемент заполняет объект <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>и <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает его дочерние элементы управления по умолчанию. <xref:System.Windows.Forms.Integration.WindowsFormsHost>

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Вопросы, связанные с макетом элемента WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md)
- [Пример упорядочивания элементов управления Windows Forms в WPF](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Пошаговое руководство: Размещение составного элемента управления Windows Forms в WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
