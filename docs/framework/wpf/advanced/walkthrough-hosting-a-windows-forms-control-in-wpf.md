---
title: "Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF | Microsoft Docs"
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
  - "размещение элементов управления Windows Forms в WPF"
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
caps.latest.revision: 36
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержит множество элементов управления с богатым набором функций.  Однако иногда может возникнуть потребность в использовании элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] на страницах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Например, можно получить значительные преимущества от использования существующих элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] или можно использовать элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] с уникальными функциональными возможностями.  
  
 В данном пошаговом руководстве показано, как разместить элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=fullName> на странице [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью кода.  
  
 Полный пример кода для задач, приведенных в этом руководстве, см. в разделе [Пример размещения элемента управления Windows Forms в приложении WPF](http://go.microsoft.com/fwlink/?LinkID=160057).  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Размещение элемента управления Windows Forms  
  
#### Чтобы разместить элемент управления MaskedTextBox  
  
1.  Создайте проект приложения WPF с именем `HostingWfInWpf`.  
  
2.  Добавьте ссылки на следующие сборки:  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Откройте файл MainWindow.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  Присвойте элементу <xref:System.Windows.Controls.Grid> имя `grid1`.  
  
     [!code-xml[HostingWfInWPF#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]  
  
5.  В представлении конструирования или представлении XAML выберите элемент <xref:System.Windows.Window>.  
  
6.  В окне свойств перейдите на вкладку **События**.  
  
7.  Дважды щелкните событие <xref:System.Windows.FrameworkElement.Loaded>.  
  
8.  Вставьте следующий код для обработки события <xref:System.Windows.FrameworkElement.Loaded>.  
  
     [!code-csharp[HostingWfInWPF#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]  
  
9. В начало файла добавьте следующий оператор `Imports` или `using`.  
  
     [!code-csharp[HostingWfInWPF#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]  
  
10. Нажмите клавишу F5 для построения и выполнения приложения.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF с помощью XAML](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)   
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Элементы управления Windows Forms и эквивалентные элементы управления WPF](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)   
 [Hosting a Windows Forms Control in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=160057)