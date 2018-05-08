---
title: Руководство по размещению визуальных объектов в приложении Win32
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual objects in Win32 code [WPF]
- Win32 code [WPF], visual objects in
- hosting [WPF], visual objects in Win32 code
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
ms.openlocfilehash: cc78dfd22b0ad2726ce8870a4e03f539ec691d85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Руководство по размещению визуальных объектов в приложении Win32
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако, если имеются существенные преимущества [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] код, он может быть более эффективным будет добавление [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] функциональные возможности приложения, а не перезаписывают код. Чтобы обеспечить поддержку [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] графических подсистем, одновременно используемых в приложении, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет механизм для размещения объектов в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна.  
  
 Этот учебник описывает, как написать пример приложения, [с взаимодействие примере приложения Win32](http://go.microsoft.com/fwlink/?LinkID=159995), что узлы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] визуальные объекты в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна.  
  

  
<a name="requirements"></a>   
## <a name="requirements"></a>Требования  
 В этом учебнике предполагается, что вы знакомы с основами программирования в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Основные сведения о [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] программирования, в разделе [Пошаговое руководство: My первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md). Основные сведения о [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] программирование, смотрите в любом из множества книг на темы, в частности *программирования Windows* , Чарльз Петцольд.  
  
> [!NOTE]
>  Этот учебник включает ряд примеров кода из связанного образца приложения. Однако для удобства чтения он не содержит полный пример кода. Полный образец кода в разделе [с образец взаимодействие Win32](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Создание окна размещения Win32  
 Ключом к размещению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объекты в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окно <xref:System.Windows.Interop.HwndSource> класса. Этот класс переносит [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объекты в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окно, в котором их присоединиться к вашей [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] как дочернего окна.  
  
 В примере показан код для создания <xref:System.Windows.Interop.HwndSource> объекта в виде [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна контейнера для визуальных объектов. Чтобы задать стиль окна, положение и другие параметры для [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна, используйте <xref:System.Windows.Interop.HwndSourceParameters> объекта.  
  
 [!code-csharp[VisualsHitTesting#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
>  Значение <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> свойства не может быть присвоено WS_EX_TRANSPARENT. Это означает, что узел [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окно не может быть прозрачным. По этой причине цвет фона узла [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] устанавливается окна тот же цвет фона, что и у родительского окна.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Добавление визуальных объектов в окно размещения Win32  
 После создания узла [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна контейнера для визуальных объектов визуальных объектов можно добавить к нему. Необходимо убедиться, что любые преобразования визуальных объектов, такие как анимация, не выходят за пределы узла [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна, ограничивающего прямоугольника.  
  
 В примере показан код для создания <xref:System.Windows.Interop.HwndSource> объекта и добавления визуальных объектов.  
  
> [!NOTE]
>  <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Свойство <xref:System.Windows.Interop.HwndSource> присваивается первый визуальный объект, добавленные к узлу [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна. Корневой визуальный объект определяет верхний узел дерева визуальных объектов. Все последующие визуальные объекты, добавленные к узлу [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна добавляются как дочерние объекты.  
  
 [!code-csharp[VisualsHitTesting#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Реализация фильтра сообщений Win32  
 Узел [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна для визуальных объектов требуется процедура фильтрации сообщений окна для обработки сообщений, отправляемых в окно из очереди приложения. Процедура окна получает сообщения от [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] системы. Это могут быть входные сообщения или сообщения управления окнами. Сообщение можно обработать в процедуре окна или передать системе для обработки по умолчанию.  
  
 <xref:System.Windows.Interop.HwndSource> Объект, который определен как родительский для визуальных объектов необходимо ссылаться предоставленная вами процедура фильтрации сообщений окна. При создании <xref:System.Windows.Interop.HwndSource> , задайте <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> свойство для ссылки на процедуру окна.  
  
 [!code-csharp[VisualsHitTesting#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 В следующем примере показан код для обработки сообщений при отпускании левой и правой кнопок мыши. Недопустимое значение координаты указателя мыши попаданий позиции содержится в значении `lParam` параметра.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Обработка сообщений Win32  
 В следующем примере кода показано, как выполняется нажатия иерархии визуальных объектов, содержащихся в узле [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна. Можно определить, расположена ли точка внутри визуального объекта с помощью <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метод, чтобы задать корневой визуальный объект и значение координаты, которую производится проверка нажатия. В этом случае корневой визуальный объект является значением <xref:System.Windows.Interop.HwndSource.RootVisual%2A> свойство <xref:System.Windows.Interop.HwndSource> объекта.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Дополнительные сведения о тестировании на посещение визуальных объектов см. в разделе [нажатия на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Interop.HwndSource>  
 [Попадания с примером взаимодействия Win32](http://go.microsoft.com/fwlink/?LinkID=159995)  
 [Проверка нажатия на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
