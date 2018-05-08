---
title: 'Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: 771c0d972420b929ac757ced684de70d2dc7a58d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a>Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost
В этом пошаговом руководстве показано, как использовать <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> свойство для сопоставления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства соответствующим свойствам размещенных [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание проекта.  
  
-   Определение макета приложения.  
  
-   Определение нового сопоставления свойства.  
  
-   Удаление сопоставления свойства по умолчанию.  
  
-   Замена сопоставления свойства по умолчанию.  
  
-   Расширение сопоставления свойства по умолчанию.  
  
 Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [сопоставление свойств с помощью образец элемента WindowsFormsHost](http://go.microsoft.com/fwlink/?LinkID=160019).  
  
 Когда вы закончите, можно для сопоставления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства соответствующим свойствам размещенных [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>Создание проекта  
  
#### <a name="to-create-and-set-up-the-project"></a>Создание и настройка проекта  
  
1.  Создание проекта приложения WPF с именем `PropertyMappingWithWfhSample`.  
  
2.  В обозревателе решений добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration.dll.  
  
3.  В обозревателе решений добавьте ссылки на сборки System.Drawing и System.Windows.Forms.  
  
## <a name="defining-the-application-layout"></a>Определение макета приложения  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-На основе приложения использует <xref:System.Windows.Forms.Integration.WindowsFormsHost> для размещения элемента [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.  
  
#### <a name="to-define-the-application-layout"></a>Определение макета приложения  
  
1.  Откройте файл Window1.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
2.  Замените существующий код следующим кодом:  
  
     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  Откройте файл Window1.xaml.cs в редакторе кода.  
  
4.  В верхней части файла импортируйте указанные ниже пространства имен.  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a>Определение нового сопоставления свойства  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент предоставляет несколько по умолчанию сопоставления свойств. Добавить новое сопоставление свойства путем вызова <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> метод <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-define-a-new-property-mapping"></a>Определение нового сопоставления свойства  
  
-   Скопируйте следующий код в определение `Window1` класса.  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     `AddClipMapping` Метод добавляет новое сопоставление для <xref:System.Windows.UIElement.Clip%2A> свойства.  
  
     `OnClipChange` Метод переводит <xref:System.Windows.UIElement.Clip%2A> свойства [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> свойство.  
  
     `Window1_SizeChanged` Метод обрабатывает окна <xref:System.Windows.FrameworkElement.SizeChanged> событий и размеров области отсечения по размеру окна приложения.  
  
## <a name="removing-a-default-property-mapping"></a>Удаление сопоставления свойства по умолчанию  
 Удалить сопоставление свойства по умолчанию путем вызова <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> метод <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-remove-a-default-property-mapping"></a>Удаление сопоставления свойства по умолчанию  
  
-   Скопируйте следующий код в определение `Window1` класса.  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     `RemoveCursorMapping` Метод удаляет сопоставление по умолчанию для <xref:System.Windows.FrameworkElement.Cursor%2A> свойства.  
  
## <a name="replacing-a-default-property-mapping"></a>Замена сопоставления свойства по умолчанию  
 Замените сопоставление свойства по умолчанию, удалив сопоставление по умолчанию и вызывая метод <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> метод <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-replace-a-default-property-mapping"></a>Замена сопоставления свойства по умолчанию  
  
-   Скопируйте следующий код в определение `Window1` класса.  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     `ReplaceFlowDirectionMapping` Метод заменяет сопоставление по умолчанию для <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойства.  
  
     `OnFlowDirectionChange` Метод переводит <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойства [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> свойство.  
  
     `cb_CheckedChanged` Метод обрабатывает <xref:System.Windows.Forms.CheckBox.CheckedChanged> события <xref:System.Windows.Forms.CheckBox> элемента управления. Он назначает <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойства на основе значения <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойство  
  
## <a name="extending-a-default-property-mapping"></a>Расширение сопоставления свойства по умолчанию  
 Вы можете использовать сопоставление свойства по умолчанию, а также расширить его с помощью собственного сопоставления.  
  
#### <a name="to-extend-a-default-property-mapping"></a>Расширение сопоставления свойства по умолчанию  
  
-   Скопируйте следующий код в определение `Window1` класса.  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     `ExtendBackgroundMapping` Метод добавляет пользовательский преобразователь свойств для существующего <xref:System.Windows.Controls.Control.Background%2A> сопоставление свойств.  
  
     `OnBackgroundChange` Метод назначает конкретный образ размещенного элемента управления <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство. `OnBackgroundChange` Метод вызывается после применения сопоставления свойства по умолчанию.  
  
## <a name="initializing-your-property-mappings"></a>Инициализация сопоставлений свойств  
 Настройка сопоставления свойств путем вызова описанных ранее методов <xref:System.Windows.FrameworkElement.Loaded> обработчика событий.  
  
#### <a name="to-initialize-your-property-mappings"></a>Инициализация сопоставлений свойств  
  
1.  Скопируйте следующий код в определение `Window1` класса.  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     `WindowLoaded` Метод обрабатывает <xref:System.Windows.FrameworkElement.Loaded> событие и выполняет следующую инициализацию.  
  
    -   Создает [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> управления.  
  
    -   Вызывает методы, ранее определенные в руководстве, для настройки сопоставлений свойств.  
  
    -   Присваивает начальные значения сопоставленным свойствам.  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Щелкните флажок, чтобы увидеть эффект <xref:System.Windows.FrameworkElement.FlowDirection%2A> сопоставления. При установке флажка меняется ориентация макета по горизонтали.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [Конструктор WPF](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
