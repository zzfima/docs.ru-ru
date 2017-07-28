---
title: "Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "сопоставление свойств"
  - "сопоставление свойств с элементом WindowsFormsHost"
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost
В этом пошаговом руководстве показано, как использовать <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> свойство сопоставляется [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства соответствующим свойствам в размещенных [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание проекта.  
  
-   Определение макета приложения.  
  
-   Определение нового сопоставления свойства.  
  
-   Удаление сопоставления свойства по умолчанию.  
  
-   Замена сопоставления свойства по умолчанию.  
  
-   Расширение сопоставления свойства по умолчанию.  
  
 Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [сопоставление свойств с помощью образец элемента WindowsFormsHost](http://go.microsoft.com/fwlink/?LinkID=160019).  
  
 Когда вы закончите, можно сопоставить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства соответствующим свойствам в размещенных [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.  
  
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
  
#### <a name="to-define-the-application-layout"></a>Чтобы определить макет приложения  
  
1.  Откройте файл Window1.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
2.  Замените существующий код следующим кодом.  
  
     [!code-xml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  Откройте файл Window1.xaml.cs в редакторе кода.  
  
4.  В верхней части файла импортируйте следующие пространства имен.  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a>Определение нового сопоставления свойств  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент предоставляет несколько стандартных сопоставлений свойств. Добавить новое сопоставление свойства путем вызова <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> метод <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-define-a-new-property-mapping"></a>Чтобы определить новое сопоставление свойства  
  
-   Скопируйте следующий код в определение `Window1` класса.  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     `AddClipMapping` Метод добавляет новое сопоставление для <xref:System.Windows.UIElement.Clip%2A> свойство.  
  
     `OnClipChange` Метод преобразует <xref:System.Windows.UIElement.Clip%2A> свойства [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> свойство.  
  
     `Window1_SizeChanged` Метод обрабатывает окна <xref:System.Windows.FrameworkElement.SizeChanged> событий и изменяет размер области отсечения по размеру окна приложения.  
  
## <a name="removing-a-default-property-mapping"></a>Удаление сопоставления свойства по умолчанию  
 Удалить сопоставление свойства по умолчанию, можно вызвать <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> метод <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-remove-a-default-property-mapping"></a>Чтобы удалить сопоставление свойства по умолчанию  
  
-   Скопируйте следующий код в определение `Window1` класса.  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     `RemoveCursorMapping` Метод удаляет сопоставление по умолчанию для <xref:System.Windows.FrameworkElement.Cursor%2A> свойство.  
  
## <a name="replacing-a-default-property-mapping"></a>Замена сопоставления свойства по умолчанию  
 Замените сопоставление свойства по умолчанию, удалив сопоставление по умолчанию и вызывая метод <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> метод <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-replace-a-default-property-mapping"></a>Чтобы заменить сопоставление свойства по умолчанию  
  
-   Скопируйте следующий код в определение `Window1` класса.  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     `ReplaceFlowDirectionMapping` Метод заменяет сопоставление по умолчанию для <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойство.  
  
     `OnFlowDirectionChange` Метод преобразует <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойства [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> свойство.  
  
     `cb_CheckedChanged` Метод обрабатывает <xref:System.Windows.Forms.CheckBox.CheckedChanged> события <xref:System.Windows.Forms.CheckBox> элемента управления. Он назначает <xref:System.Windows.FrameworkElement.FlowDirection%2A> , основанного на значении <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойство  
  
## <a name="extending-a-default-property-mapping"></a>Расширение сопоставления свойства по умолчанию  
 Можно использовать сопоставление свойства по умолчанию и также расширить его с помощью собственного сопоставления.  
  
#### <a name="to-extend-a-default-property-mapping"></a>Чтобы расширить сопоставление свойства по умолчанию  
  
-   Скопируйте следующий код в определение `Window1` класса.  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     `ExtendBackgroundMapping` Метод добавляет пользовательский преобразователь свойств к существующему <xref:System.Windows.Controls.Control.Background%2A> сопоставление свойств.  
  
     `OnBackgroundChange` Метод присваивает определенное изображение размещенного элемента управления <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство. `OnBackgroundChange` Метод вызывается после применения сопоставления свойства по умолчанию.  
  
## <a name="initializing-your-property-mappings"></a>Инициализация сопоставления свойств  
 Настройка сопоставления свойств путем вызова ранее описанных методов <xref:System.Windows.FrameworkElement.Loaded> обработчика событий.  
  
#### <a name="to-initialize-your-property-mappings"></a>Чтобы инициализировать сопоставления свойств  
  
1.  Скопируйте следующий код в определение `Window1` класса.  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     `WindowLoaded` Метод обрабатывает <xref:System.Windows.FrameworkElement.Loaded> событие и выполняет следующую инициализацию.  
  
    -   Создает [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> элемента управления.  
  
    -   Вызывает методы, определенные ранее в пошаговом руководстве для настройки сопоставлений свойств.  
  
    -   Назначение начальных значений сопоставленным свойствам.  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его. Щелкните флажок, чтобы увидеть эффект <xref:System.Windows.FrameworkElement.FlowDirection%2A> сопоставления. Если щелкнуть флажок, макет отменяет его ориентации слева направо.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Сопоставление свойств WPF и Windows Forms](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Пошаговое руководство: Размещение элемента управления Windows Forms в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)