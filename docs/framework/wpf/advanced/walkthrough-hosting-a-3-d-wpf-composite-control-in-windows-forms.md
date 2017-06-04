---
title: "Пошаговое руководство. Размещение составного трехмерного элемента управления WPF в форме Windows Forms | Microsoft Docs"
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
  - "составные элементы управления, размещение WPF в"
  - "размещение содержимого WPF в Windows Forms"
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Пошаговое руководство. Размещение составного трехмерного элемента управления WPF в форме Windows Forms
Данный пример демонстрирует создание составного элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и его размещения в элементах управления и формах [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] с помощью элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.  
  
 Данное пошаговое руководство реализует [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>, который содержит два дочерних элемента управления.  <xref:System.Windows.Controls.UserControl> отображает трехмерный \(3\-D\) конус.  Отрисовывать 3\-D объекты гораздо удобнее с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], нежели с [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Поэтому для создания 3\-D графики имеет смысл размещать класс [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Создание [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.  
  
-   Создание проекта размещения Windows Forms  
  
-   Размещение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.  
  
 Полный листинг кода задач, приведенных в этом руководстве, см. в документе [Hosting a 3\-D WPF Composite Control in Windows Forms Sample](http://go.microsoft.com/fwlink/?LinkID=160001).  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
<a name="To_Create_the_UserControl"></a>   
## Создание UserControl  
  
#### Для создания UserControl  
  
1.  Создайте проект WPF User Control Library с именем `HostingWpfUserControlInWf`.  
  
2.  Откройте файл UserControl1.xaml в конструкторе [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
3.  Замените сгенерированный код следующим:  
  
     Этот код определяет <xref:System.Windows.Controls.UserControl?displayProperty=fullName>, который содержит два дочерних элемента управления.  Первый дочерний элемент управления является элементом управления <xref:System.Windows.Controls.Label?displayProperty=fullName>, а второй является элементом управления <xref:System.Windows.Controls.Viewport3D>, отображающим 3\-D конус.  
  
     [!code-xml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## Создание ведущего проекта Windows Forms  
  
#### Для создания ведущего проекта  
  
1.  Добавьте в решение проект приложения Windows с именем `WpfUserControlHost`.  Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/ru-ru/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  В обозревателе решений добавьте ссылку на сборку "WindowsFormsIntegration", которая называется WindowsFormsIntegration.dll.  
  
3.  Добавьте ссылки на следующие сборки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
4.  Добавьте ссылку на проект `HostingWpfUserControlInWf`.  
  
5.  В обозревателе решений назначьте проект `WpfUserControlHost` запускаемым проектом.  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## Размещение UserControl Windows Presentation Foundation  
  
#### Для размещения UserControl  
  
1.  В конструкторе Windows Forms откройте Form1.  
  
2.  В окне "Свойства" нажмите кнопку **События**, а затем дважды щелкните событие <xref:System.Windows.Forms.Form.Load>, чтобы создать обработчик событий.  
  
     Редактор кода откроется на новом созданном обработчике событий `Form1_Load`.  
  
3.  Замените код в файле Form1.cs следующим кодом:  
  
     Обработчик событий `Form1_Load` создает экземпляр `UserControl1` и добавляет его `` в коллекцию элемента управления <xref:System.Windows.Forms.Integration.ElementHost> дочерних элементов управления.  Элемент управления <xref:System.Windows.Forms.Integration.ElementHost> добавляется в коллекцию формы дочерних элементов управления.  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Hosting a WPF Composite Control in Windows Forms Sample](http://go.microsoft.com/fwlink/?LinkID=160001)