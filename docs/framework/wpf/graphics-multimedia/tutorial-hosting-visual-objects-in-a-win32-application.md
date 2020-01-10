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
ms.openlocfilehash: 621684e14f9d1b599c4ef60e3731f0f58f31aacd
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740160"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Руководство по размещению визуальных объектов в приложении Win32
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако при наличии значительных инвестиций в код Win32 может оказаться более эффективным Добавление [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] функций в приложение, а не переписывание кода. Чтобы обеспечить поддержку Win32 и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] графических подсистем, используемых в приложении параллельно, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет механизм для размещения объектов в окне Win32.  
  
 В этом учебнике описывается Написание примера приложения, [Проверка попадания с помощью примера взаимодействия Win32](https://go.microsoft.com/fwlink/?LinkID=159995), в котором размещаются [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] визуальных объектов в окне Win32.  

<a name="requirements"></a>   
## <a name="requirements"></a>Требования  
 В этом учебнике предполагается базовый знакомство с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и программированием Win32. Основные сведения о [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] программировании см. в разделе [Пошаговое руководство. мое первое приложение WPF для настольных систем](../getting-started/walkthrough-my-first-wpf-desktop-application.md). Общие сведения о программировании Win32 см. в любом из многочисленных книг по теме, в определенных *окнах программирования* с помощью Чарльз Петцольд.  
  
> [!NOTE]
> Этот учебник включает ряд примеров кода из связанного образца приложения. Однако для удобства чтения он не содержит полный пример кода. Полный пример кода см. в разделе [Проверка попадания с помощью примера взаимодействия Win32](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Создание окна размещения Win32  
 Ключом к размещению объектов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окне Win32 является класс <xref:System.Windows.Interop.HwndSource>. Этот класс служит оболочкой для объектов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окне Win32, что позволяет включать их в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] в качестве дочернего окна.  
  
 В следующем примере показан код для создания объекта <xref:System.Windows.Interop.HwndSource> в виде окна контейнера Win32 для визуальных объектов. Чтобы задать стиль окна, расположение и другие параметры для окна Win32, используйте объект <xref:System.Windows.Interop.HwndSourceParameters>.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> Свойству <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> не может быть присвоено значение WS_EX_TRANSPARENT. Это означает, что окно Win32 узла не может быть прозрачным. По этой причине цвет фона главного окна Win32 устанавливается на тот же цвет фона, что и его родительское окно.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Добавление визуальных объектов в окно размещения Win32  
 После создания окна контейнера Win32 для визуальных объектов можно добавить в него визуальные объекты. Необходимо убедиться, что любые преобразования визуальных объектов, такие как анимация, не выходят за границы ограничивающего прямоугольника хост-окна Win32.  
  
 В следующем примере показан код для создания объекта <xref:System.Windows.Interop.HwndSource> и добавления в него визуальных объектов.  
  
> [!NOTE]
> Свойству <xref:System.Windows.Interop.HwndSource.RootVisual%2A> объекта <xref:System.Windows.Interop.HwndSource> присваивается первый визуальный объект, добавленный в главное окно Win32. Корневой визуальный объект определяет верхний узел дерева визуальных объектов. Все последующие визуальные объекты, добавленные в главное окно Win32, добавляются как дочерние объекты.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Реализация фильтра сообщений Win32  
 Хост-окну Win32 для визуальных объектов требуется процедура фильтрации сообщений окна для обработки сообщений, отправляемых в окно из очереди приложения. Оконная процедура получает сообщения из системы Win32. Это могут быть входные сообщения или сообщения управления окнами. Сообщение можно обработать в процедуре окна или передать системе для обработки по умолчанию.  
  
 Объект <xref:System.Windows.Interop.HwndSource>, определенный как родительский для визуальных объектов, должен ссылаться на процедуру фильтрации сообщений окна, которую вы задаете. При создании объекта <xref:System.Windows.Interop.HwndSource> установите свойство <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A>, чтобы оно ссылалось на процедуру окна.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 В следующем примере показан код для обработки сообщений при отпускании левой и правой кнопок мыши. Значение координаты в положении нажатия мыши содержится в значении параметра `lParam`.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Обработка сообщений Win32  
 Код в следующем примере показывает, как выполняется проверка попадания для иерархии визуальных объектов, содержащихся в окне Win32 узла. Можно определить, находится ли точка в пределах геометрии визуального объекта, используя метод <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>, чтобы указать корневой визуальный объект и значение координаты для проверки попадания. В этом случае корневой визуальный объект является значением свойства <xref:System.Windows.Interop.HwndSource.RootVisual%2A> объекта <xref:System.Windows.Interop.HwndSource>.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Дополнительные сведения о проверке нажатия для визуальных объектов см. [в разделе Проверка попадания на визуальном уровне](hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Interop.HwndSource>
- [Проверка нажатия с помощью примера взаимодействия Win32](https://go.microsoft.com/fwlink/?LinkID=159995)
- [Проверка нажатия на визуальном уровне](hit-testing-in-the-visual-layer.md)
