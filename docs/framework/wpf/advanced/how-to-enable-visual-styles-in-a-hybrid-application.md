---
title: "Практическое руководство. Включение визуальных стилей в гибридном приложении"
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
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73f611eab7f75d1578652a8a9f5bb05d9720e851
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>Практическое руководство. Включение визуальных стилей в гибридном приложении
В этом разделе показано, как включить [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] визуальные стили на [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] размещение элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложения.  
  
 Если приложение вызывает <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод большую часть вашей [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления будут автоматически использовать визуальные стили при запуске приложения на [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]. Дополнительные сведения см. в разделе [визуализации элементов управления с применением визуальных стилей](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).  
  
 Полный пример кода для задач, приведенных в этом разделе, в разделе [Включение визуальных стилей в гибридное приложение-пример](http://go.microsoft.com/fwlink/?LinkID=159986).  
  
## <a name="enabling-windows-forms-visual-styles"></a>Включение визуальных стилей Windows Forms  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>Чтобы включить визуальные стили Windows Forms, выполните следующие действия.  
  
1.  Создание [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] проект приложения с именем `HostingWfWithVisualStyles`.  
  
2.  В обозревателе решений добавьте ссылки на следующие сборки.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms.  
  
3.  В области элементов дважды щелкните <xref:System.Windows.Controls.Grid> значок, чтобы разместить <xref:System.Windows.Controls.Grid> элемент в области конструктора.  
  
4.  В окне свойств задайте значения <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> свойства **автоматически**.  
  
5.  В режиме конструктора или в представлении XAML выберите <xref:System.Windows.Window>.  
  
6.  В окне «Свойства» щелкните **события** вкладки.  
  
7.  Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событий.
  
8.  В файле MainWindow.xaml.cs или вставьте следующий код для обработки <xref:System.Windows.FrameworkElement.Loaded> событий.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
     [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Элемент управления отрисовывается с помощью визуальных стилей.  
  
## <a name="disabling-windows-forms-visual-styles"></a>Отключение визуальных стилей Windows Forms  
 Чтобы отключить визуальные стили, просто удалите вызов <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод.  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>Чтобы отключить визуальные стили Windows Forms, выполните следующие действия.  
  
1.  Откройте файл MainWindow.xaml.vb или MainWindow.xaml.cs в редакторе кода.  
  
2.  Закомментируйте вызов <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод.  
  
3.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
     [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Элемент управления отрисовывается с помощью стиля системы по умолчанию.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>  
 <xref:System.Windows.Forms.VisualStyles>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Отрисовка элементов управления с применением визуальных стилей](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
