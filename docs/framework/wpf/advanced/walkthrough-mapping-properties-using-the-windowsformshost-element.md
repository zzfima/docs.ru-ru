---
title: 'Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: c076937d6431adf1750793d47ece88dc82edf95c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794104"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a>Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost

В этом пошаговом руководстве показано, как использовать свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>, чтобы сопоставлять свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с соответствующими свойствами размещенного элемента управления Windows Forms.

В данном пошаговом руководстве представлены следующие задачи.

- Создание проекта.

- Определение макета приложения.

- Определение нового сопоставления свойства.

- Удаление сопоставления свойства по умолчанию.

- Замена сопоставления свойства по умолчанию.

- Расширение сопоставления свойства по умолчанию.

Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [сопоставление свойств с помощью примера элемента WindowsFormsHost](https://go.microsoft.com/fwlink/?LinkID=160019).

По завершении вы сможете сопоставлять [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства с соответствующими свойствами размещенного элемента управления Windows Forms.

## <a name="prerequisites"></a>Prerequisites

Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.

- Visual Studio 2017

## <a name="create-and-set-up-the-project"></a>Создание и Настройка проекта

1. Создайте проект **приложения WPF** с именем `PropertyMappingWithWfhSample`.

2. В **Обозреватель решений**добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration. dll.

3. В **Обозреватель решений**добавьте ссылки на сборки System. Drawing и System. Windows. Forms.

## <a name="defining-the-application-layout"></a>Определение макета приложения

Приложение на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]использует элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> для размещения элемента управления Windows Forms.

### <a name="to-define-the-application-layout"></a>Определение макета приложения

1. Откройте Window1. XAML в конструкторе WPF.

2. Замените существующий код следующим кодом:

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. Откройте файл Window1.xaml.cs в редакторе кода.

4. В верхней части файла импортируйте указанные ниже пространства имен.

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a>Определение нового сопоставления свойства

Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> предоставляет несколько сопоставлений свойств по умолчанию. Новое сопоставление свойств добавляется путем вызова метода <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> для <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

### <a name="to-define-a-new-property-mapping"></a>Определение нового сопоставления свойства

- Скопируйте следующий код в определение класса `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     Метод `AddClipMapping` добавляет новое сопоставление для свойства <xref:System.Windows.UIElement.Clip%2A>.

     Метод `OnClipChange` преобразует свойство <xref:System.Windows.UIElement.Clip%2A> в свойство Windows Forms<xref:System.Windows.Forms.Control.Region%2A>.

     Метод `Window1_SizeChanged` обрабатывает событие <xref:System.Windows.FrameworkElement.SizeChanged> окна и изменяет размер вырезанной области в соответствии с окном приложения.

## <a name="removing-a-default-property-mapping"></a>Удаление сопоставления свойства по умолчанию

Удалите сопоставление свойств по умолчанию, вызвав метод <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> для <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

### <a name="to-remove-a-default-property-mapping"></a>Удаление сопоставления свойства по умолчанию

- Скопируйте следующий код в определение класса `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     Метод `RemoveCursorMapping` удаляет сопоставление по умолчанию для свойства <xref:System.Windows.FrameworkElement.Cursor%2A>.

## <a name="replacing-a-default-property-mapping"></a>Замена сопоставления свойства по умолчанию

Замените сопоставление свойства по умолчанию, удалив сопоставление по умолчанию и вызвав метод <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> для <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

### <a name="to-replace-a-default-property-mapping"></a>Замена сопоставления свойства по умолчанию

- Скопируйте следующий код в определение класса `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     Метод `ReplaceFlowDirectionMapping` заменяет сопоставление по умолчанию для свойства <xref:System.Windows.FrameworkElement.FlowDirection%2A>.

     Метод `OnFlowDirectionChange` преобразует свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> в свойство Windows Forms<xref:System.Windows.Forms.Control.RightToLeft%2A>.

     Метод `cb_CheckedChanged` обрабатывает событие <xref:System.Windows.Forms.CheckBox.CheckedChanged> в элементе управления <xref:System.Windows.Forms.CheckBox>. Он назначает свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> на основе значения свойства <xref:System.Windows.Forms.CheckBox.CheckState%2A>

## <a name="extending-a-default-property-mapping"></a>Расширение сопоставления свойства по умолчанию

Вы можете использовать сопоставление свойства по умолчанию, а также расширить его с помощью собственного сопоставления.

### <a name="to-extend-a-default-property-mapping"></a>Расширение сопоставления свойства по умолчанию

- Скопируйте следующий код в определение класса `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     Метод `ExtendBackgroundMapping` добавляет настраиваемый транслятор свойств к существующему сопоставлению свойств <xref:System.Windows.Controls.Control.Background%2A>.

     Метод `OnBackgroundChange` присваивает конкретному изображению свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> размещаемого элемента управления. Метод `OnBackgroundChange` вызывается после применения сопоставления свойства по умолчанию.

## <a name="initializing-your-property-mappings"></a>Инициализация сопоставлений свойств

Настройте сопоставления свойств, вызвав ранее описанные методы в обработчике событий <xref:System.Windows.FrameworkElement.Loaded>.

### <a name="to-initialize-your-property-mappings"></a>Инициализация сопоставлений свойств

1. Скопируйте следующий код в определение класса `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     Метод `WindowLoaded` обрабатывает событие <xref:System.Windows.FrameworkElement.Loaded> и выполняет следующую инициализацию.

    - Создает элемент управления<xref:System.Windows.Forms.CheckBox> Windows Forms.

    - Вызывает методы, ранее определенные в руководстве, для настройки сопоставлений свойств.

    - Присваивает начальные значения сопоставленным свойствам.

2. Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его. Установите флажок, чтобы увидеть результат сопоставления <xref:System.Windows.FrameworkElement.FlowDirection%2A>. При установке флажка меняется ориентация макета по горизонтали.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md)
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
