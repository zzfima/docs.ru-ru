---
title: "Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF с помощью XAML | Microsoft Docs"
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
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF с помощью XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержит множество элементов управления с богатым набором функций.  Однако иногда может возникнуть потребность в использовании элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] на страницах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Например, можно получить значительные преимущества от использования существующих элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] или можно использовать элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] с уникальными функциональными возможностями.  
  
 В данном пошаговом руководстве показано, как разместить элемент управления <xref:System.Windows.Forms.MaskedTextBox?displayProperty=fullName> Windows Forms на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] странице с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Полный пример кода для задач, приведенных в этом руководстве, см. в разделе [Пример размещения элемента управления Windows Forms в приложении WPF с помощью XAML](http://go.microsoft.com/fwlink/?LinkID=160000).  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Размещение элемента управления Windows Forms  
  
#### Чтобы разместить элемент управления MaskedTextBox  
  
1.  Создайте проект приложения WPF с именем `HostingWfInWpfWithXaml`.  
  
2.  Добавьте ссылки на следующие сборки:  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Откройте файл MainWindow.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  В элементе <xref:System.Windows.Window> добавьте следующее сопоставление пространства имен.  Сопоставление пространства имен `wf` устанавливает ссылку на сборку, содержащую элемент управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  В элементе <xref:System.Windows.Controls.Grid> добавьте следующую разметку XAML.  
  
     Элемент управления <xref:System.Windows.Forms.MaskedTextBox> создается в качестве дочернего элемента управления для <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
     [!code-xml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Элементы управления Windows Forms и эквивалентные элементы управления WPF](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)   
 [Hosting a Windows Forms Control in WPF by Using XAML Sample](http://go.microsoft.com/fwlink/?LinkID=160000)