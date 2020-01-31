---
title: Практическое руководство. Включение визуальных стилей в гибридном приложении
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: dd52313e9100f9c6a1141b53ccc5a23a4b54410a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789921"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>Практическое руководство. Включение визуальных стилей в гибридном приложении
В этом разделе показано, как включить визуальные стили для элемента управления Windows Forms, размещенного в приложении на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Если приложение вызывает метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>, большинство элементов управления Windows Forms будет автоматически использовать стили оформления. Дополнительные сведения см. в статье [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md) (Отрисовка элементов управления со стилями оформления).  
  
 Полный листинг кода задач, показанных в этом разделе, см. в разделе [Включение визуальных стилей в примере гибридного приложения](https://go.microsoft.com/fwlink/?LinkID=159986).  
  
## <a name="enabling-windows-forms-visual-styles"></a>Включение визуальных стилей Windows Forms  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>Чтобы включить визуальные стили Windows Forms, выполните следующие действия.  
  
1. Создайте проект приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с именем `HostingWfWithVisualStyles`.  
  
2. В обозревателе решений добавьте ссылки на следующие сборки.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms.  
  
3. На панели элементов дважды щелкните значок <xref:System.Windows.Controls.Grid>, чтобы поместить элемент <xref:System.Windows.Controls.Grid> в область конструктора.  
  
4. В окно свойств задайте для свойств <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> значение **Авто**.  
  
5. В представление конструирования или представлении XAML выберите <xref:System.Windows.Window>.  
  
6. В окно свойств перейдите на вкладку **события** .  
  
7. Дважды щелкните событие <xref:System.Windows.FrameworkElement.Loaded>.
  
8. В файле MainWindow. XAML. vb или MainWindow.xaml.cs вставьте следующий код, обрабатывающий событие <xref:System.Windows.FrameworkElement.Loaded>.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Нажмите клавишу F5 для построения и запуска приложения.  
  
     Элемент управления Windows Forms окрашен в стили оформления.  
  
## <a name="disabling-windows-forms-visual-styles"></a>Отключение визуальных стилей Windows Forms  
 Чтобы отключить стили оформления, просто удалите вызов метода <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>Чтобы отключить визуальные стили Windows Forms, выполните следующие действия.  
  
1. Откройте файл MainWindow.xaml.vb или MainWindow.xaml.cs в редакторе кода.  
  
2. Закомментируйте вызов метода <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.  
  
3. Нажмите клавишу F5 для построения и запуска приложения.  
  
     Элемент управления Windows Forms закрашивается стандартным стилем системы.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Отрисовка элементов управления с применением визуальных стилей](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
