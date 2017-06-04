---
title: "Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "упорядочивание элементов управления"
  - "гибридные приложения [взаимодействие с WPF]"
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF
В этом пошаговом руководстве демонстрируется использование возможностей макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для упорядочения элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в гибридных приложениях.  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Создание проекта.  
  
-   Использование параметров макета по умолчанию.  
  
-   Изменение размеров в зависимости от содержимого.  
  
-   Использование абсолютного позиционирования.  
  
-   Задание размера явным образом.  
  
-   Установка свойств макета.  
  
-   Описание ограничений z\-порядка.  
  
-   Закрепление.  
  
-   Задание видимости.  
  
-   Размещение нерастягиваемых элементов управления.  
  
-   Масштабирование.  
  
-   Поворот.  
  
-   Задание полей и внутренних полей.  
  
-   Использование динамических контейнеров макета.  
  
 Полный код для задач, приведенных в этом руководстве, см. на веб\-странице [Arranging Windows Forms Controls in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).  
  
 По окончании знакомства с разделом пользователь будет иметь представление о возможностях макета [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в приложениях, основанных на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Создание проекта  
  
#### Чтобы создать и настроить проект  
  
1.  Создайте проект приложения WPF с именем `WpfLayoutHostingWf`.  
  
2.  В обозревателе решений добавьте ссылки на следующие сборки.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
    -   System.Drawing  
  
3.  Дважды щелкните файл MainWindow.xaml, чтобы открыть его в представлении XAML.  
  
4.  В элементе <xref:System.Windows.Window> добавьте следующее сопоставление пространства имен [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  В элементе <xref:System.Windows.Controls.Grid> задайте для свойства <xref:System.Windows.Controls.Grid.ShowGridLines%2A> значение `true` и определите пять строк и три столбца.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## Использование параметров макета по умолчанию  
 По умолчанию элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> обрабатывает макет для размещаемого элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
#### Для использования параметров макета по умолчанию  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=fullName> находится внутри элемента управления <xref:System.Windows.Controls.Canvas>.  Размер размещаемого элемента управления основан на его содержимом, а размеры элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> изменяются, чтобы вместить размещаемый элемент управления.  
  
## Изменение размеров в зависимости от содержимого  
 Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> обеспечивает то, что размер размещаемого элемента управления изменяется для правильного отображения его содержимого.  
  
#### Для изменения размера в зависимости от содержимого  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Размер двух новых кнопок корректно изменяется для отображения длинных строк текста и большого шрифта, а размер элементов <xref:System.Windows.Forms.Integration.WindowsFormsHost> изменяется, чтобы вместить размещаемые элементы управления.  
  
## Использование абсолютного позиционирования  
 Абсолютное позиционирование можно использовать для размещения элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> в любом месте в пользовательском интерфейсе.  
  
#### Чтобы использовать абсолютное позиционирование  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> размещается в 20 пикселях от верхнего края ячейки сетки и в 20 пикселях от левого края.  
  
## Задание размера явным образом  
 Можно указать размер элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> с помощью <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>.  
  
#### Чтобы явно указать размер  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Размер элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> устанавливается в 50 пикселей в ширину и в 70 пикселей в высоту — это меньше, чем параметры макета по умолчанию.  Содержимое элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] упорядочивается соответствующим образом.  
  
## Установка свойств макета  
 Всегда следует задавать связанные с макетом свойства для размещаемого элемента управления с помощью свойств элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  При установке свойств макета непосредственно для размещаемого элемента управления результат не будет соответствовать ожидаемому.  
  
 Установка связанных с макетом свойств размещаемого элемента управления в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не оказывает никакого действия.  
  
#### Чтобы увидеть влияние задания свойств размещаемого элемента управления  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  В обозревателе решений дважды щелкните файл MainWindow.xaml.  vb или MainWindow.xaml.cs, чтобы открыть его в редакторе кода.  
  
3.  Скопируйте следующий код в определение класса `MainWindow`.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
5.  Нажмите кнопку **Click Me**.  Обработчик событий `button1_Click` задает свойства <xref:System.Windows.Forms.Control.Top%2A> и <xref:System.Windows.Forms.Control.Left%2A> размещаемого элемента управления.  Это приводит к изменению положения размещаемого элемента управления в элементе <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Ведущий элемент занимает то же пространство на экране, но размещаемый элемент управления обрезается.  Вместо этого размещаемый элемент управления должен всегда заполнять элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
## Описание ограничений z\-порядка  
 По умолчанию visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементы всегда рисуется поверх другого  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементы, и они не затрагиваются z\-порядка.  Чтобы включить Z\-приказывать, установите <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> свойство   <xref:System.Windows.Forms.Integration.WindowsFormsHost> true и  <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> свойство  <xref:System.Windows.Interop.CompositionMode.Full> OR  <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### Доступны по умолчанию расширения функциональности z\-порядок  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> рисуется через элемент метки.  
  
#### Увидеть расширение функциональности z\-порядка, когда IsRedirected true  
  
1.  Заменить предыдущий пример z\-порядок следующим кодом XAML.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#8b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#8b)]  
  
     Нажмите клавишу F5 для построения и выполнения приложения.  Элемент метки окрашен над <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент.  
  
## Закрепление  
 Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> поддерживает закрепление [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Задайте вложенное свойство <xref:System.Windows.Controls.DockPanel.Dock%2A>, чтобы закрепить размещаемый элемент управления в элементе <xref:System.Windows.Controls.DockPanel>.  
  
#### Чтобы закрепить размещаемый элемент управления  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> закрепляется по правой стороне элемента <xref:System.Windows.Controls.DockPanel>.  
  
## Задание видимости  
 Элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] можно сделать невидимым или свернуть его, задав свойству <xref:System.Windows.UIElement.Visibility%2A> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Если элемент управления невидим, он не отображается, но при этом занимает пространство разметки.  Если элемент управления свернут, он не отображается и не занимает пространство разметки.  
  
#### Чтобы задать видимость размещаемого элемента управления  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
4.  Нажмите на кнопку **Click to make invisible** чтобы сделать элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> невидимым.  
  
5.  Нажмите на кнопку **Click to collapse** кнопку, чтобы полностью скрыть элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> в макете.  Когда элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] свернут, соседние элементы переупорядочиваются, чтобы занять его место.  
  
## Размещение нерастягиваемых элементов управления  
 Некоторые элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] имеют фиксированный размер и не растягиваются для заполнения доступного места в макете.  Например, элемент управления <xref:System.Windows.Forms.MonthCalendar> отображает месяц в фиксированном пространстве.  
  
#### Чтобы разместить нерастягиваемый элемент управления  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> выравнивается по центру в строке сетки, но он не растягивается, чтобы заполнить доступное пространство.  Если окно достаточно большое, можно увидеть два или более месяцев, отображаемых размещаемым элементом управления <xref:System.Windows.Forms.MonthCalendar>, но они выравниваются по центру строки.  Обработчик макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выравнивает по центру элементы, размеры которых не меняются для заполнения доступного пространства.  
  
## Масштабирование  
 В отличие от элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], большинство элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не являются непрерывно масштабируемыми.  По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент масштабирует размещаемый элемент управления его, если это возможно.  Чтобы включить полноценное масштабирование, установите <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> свойство   <xref:System.Windows.Forms.Integration.WindowsFormsHost> true и  <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> свойство  <xref:System.Windows.Interop.CompositionMode.Full> OR  <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### Масштабирование размещаемый элемент управления по умолчанию с помощью расширения функциональности  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Размещаемый элемент управления и его окружающие элементы масштабируется с коэффициентом 0,5.  Однако шрифт размещаемого элемента управления не масштабируется.  
  
#### Масштабирование размещаемый элемент управления установкой IsRedirected true  
  
1.  Заменить предыдущий пример масштабирования следующим кодом XAML.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#12b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#12b)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Размещаемый элемент управления, его окружающие элементы и шрифт размещаемого элемента управления \- на 0,5.  
  
## Поворот  
 В отличие от элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не поддерживают поворот.  По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент не вращает с другим  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементы, когда применяется преобразование поворота.  Любой угол поворота, отличный от 180 градусов, вызывает событие <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>.  Чтобы включить выполнять циклический сдвиг к любому углу, установите <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> свойство   <xref:System.Windows.Forms.Integration.WindowsFormsHost> true и  <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> свойство  <xref:System.Windows.Interop.CompositionMode.Full> OR  <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### Чтобы увидеть эффект от поворота в гибридном приложении  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Размещаемый элемент управления не повернут, но его соседние элементы повернуты на угол в 180 градусов.  Для отображения элементов может потребоваться изменить размер окна.  
  
#### Увидеть эффект поворота в гибридном приложении при IsRedirected true  
  
1.  Заменить предыдущий пример поворота следующим кодом XAML.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#13b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#13b)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Размещаемый элемент управления вращано.  Обратите внимание, что <xref:System.Windows.Media.RotateTransform.Angle%2A> свойству может быть присвоено любое значение.  Для отображения элементов может потребоваться изменить размер окна.  
  
## Задание полей и внутренних полей  
 Поля и внутренние поля в макете [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] похожи на свои аналоги в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Просто задайте свойства <xref:System.Windows.Controls.Control.Padding%2A> и <xref:System.Windows.FrameworkElement.Margin%2A> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
#### Чтобы задать поля и внутренние поля размещаемого элемента управления  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  Параметры полей и внутренних полей будут применены к размещаемым элементам управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] так же, как и в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
## Использование динамических контейнеров макета  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] предоставляет два динамических контейнера макета, <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel>.  Можно также использовать эти контейнеры в макетах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
#### Чтобы использовать динамический контейнер макета  
  
1.  Скопируйте следующую разметку XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  Добавьте вызов метода `InitializeFlowLayoutPanel` в конструктор.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  Нажмите клавишу F5 для построения и выполнения приложения.  Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> заполняет <xref:System.Windows.Controls.DockPanel>, а <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает его дочерние элементы в направлении <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> по умолчанию.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Вопросы, связанные с макетом элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)   
 [Arranging Windows Forms Controls in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971)   
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)