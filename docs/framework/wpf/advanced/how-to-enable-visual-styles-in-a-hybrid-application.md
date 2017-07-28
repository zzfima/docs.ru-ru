---
title: "Практическое руководство. Включение визуальных стилей в гибридном приложении | Microsoft Docs"
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
  - "гибридные приложения [взаимодействие с WPF]"
  - "визуальные стили [Windows Forms]"
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Включение визуальных стилей в гибридном приложении
В этом разделе показано, как включить визуальные стили [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] в элементе управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], размещенном в приложении, основанном на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Если приложение вызывает метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>, то большинство элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] будут автоматически использовать визуальные стили при запуске приложения в [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].  Дополнительные сведения см. в разделе [Отрисовка элементов управления с применением визуальных стилей](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).  
  
 Полный пример кода для задач, приведенных в этом разделе, см. в разделе [Пример включения стилей отображения в гибридных приложениях](http://go.microsoft.com/fwlink/?LinkID=159986).  
  
## Включение визуальных стилей Windows Forms  
  
#### Чтобы включить визуальные стили Windows Forms, выполните следующие действия:  
  
1.  Создайте проект приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с именем `HostingWfWithVisualStyles`.  
  
2.  В обозревателе решений добавьте ссылки на следующие сборки.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  В панели элементов дважды щелкните значок <xref:System.Windows.Controls.Grid>, чтобы поместить элемент <xref:System.Windows.Controls.Grid> в рабочую область конструирования.  
  
4.  В окне "Свойства" задайте для свойств <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> значения **Auto**.  
  
5.  В представлении конструктора или представлении XML выберите объект <xref:System.Windows.Window>.  
  
6.  В окне свойств перейдите на вкладку **События**.  
  
7.  Дважды щелкните событие <xref:System.Windows.FrameworkElement.Loaded>.  
  
8.  Вставьте следующий код в файл MainWindow.xaml.vb или MainWindow.xaml.cs для обработки события <xref:System.Windows.FrameworkElement.Loaded>.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Нажмите клавишу F5 для построения и выполнения приложения.  
  
     Элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] отрисовывается с помощью визуальных стилей.  
  
## Отключение визуальных стилей Windows Forms  
 Чтобы отключить визуальные стили, просто удалите вызов метода <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.  
  
#### Чтобы отключить визуальные стили Windows Forms, выполните следующие действия:  
  
1.  В редакторе кода откройте файл MainWindow.xaml.vb или MainWindow.xaml.cs.  
  
2.  Закомментируйте вызов метода <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.  
  
3.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
     Элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] отрисовывается с помощью стиля системы по умолчанию.  
  
## См. также  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>   
 <xref:System.Windows.Forms.VisualStyles>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Отрисовка элементов управления с применением визуальных стилей](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)   
 [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)