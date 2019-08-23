---
title: Учебник. Размещение визуальных объектов в приложении Win32
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual objects in Win32 code [WPF]
- Win32 code [WPF], visual objects in
- hosting [WPF], visual objects in Win32 code
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
ms.openlocfilehash: c8baefbf01467a65626a77f300f34a145d5c7281
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962875"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Учебник. Размещение визуальных объектов в приложении Win32
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако при наличии значительных инвестиций в [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] код может оказаться более эффективным добавление [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] функциональных возможностей в приложение, а не переписывание кода. Для обеспечения поддержки [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] графических подсистем, используемых в приложении параллельно, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] предоставляет механизм для размещения объектов в окне.  
  
 В этом учебнике описывается Написание примера приложения, [Проверка попадания с помощью примера взаимодействия Win32](https://go.microsoft.com/fwlink/?LinkID=159995), в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] котором [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] визуальные объекты размещаются в окне.  

<a name="requirements"></a>   
## <a name="requirements"></a>Требования  
 В этом учебнике предполагается, что вы знакомы с основами программирования в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Базовые сведения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] о программировании см. в [разделе Пошаговое руководство. Мое первое приложение](../getting-started/walkthrough-my-first-wpf-desktop-application.md)WPF для настольных систем. Общие сведения [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] о программировании см. в любом из многочисленных книг по теме в определенных окнах *программирования* с помощью Чарльз Петцольд.  
  
> [!NOTE]
> Этот учебник включает ряд примеров кода из связанного образца приложения. Однако для удобства чтения он не содержит полный пример кода. Полный пример кода см. в разделе [Проверка попадания с помощью примера взаимодействия Win32](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Создание окна размещения Win32  
 Ключом к размещению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объектов [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в окне является <xref:System.Windows.Interop.HwndSource> класс. Этот класс создает оболочку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] для объектов [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в окне, позволяя включать их в качестве дочернего окна.  
  
 В следующем примере показан код для создания <xref:System.Windows.Interop.HwndSource> объекта в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] качестве окна контейнера для визуальных объектов. Чтобы задать стиль окна, расположение и другие параметры для [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна, <xref:System.Windows.Interop.HwndSourceParameters> используйте объект.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> Значение <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> свойства не может быть задано равным WS_EX_TRANSPARENT. Это означает, что окно [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] главного приложения не может быть прозрачным. По этой причине цвет фона главного [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна устанавливается на тот же цвет фона, что и его родительское окно.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Добавление визуальных объектов в окно размещения Win32  
 После создания [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна контейнера для визуальных объектов можно добавить в него визуальные объекты. Необходимо убедиться, что все преобразования визуальных объектов, такие как анимация, не выходят за границы ограничивающего прямоугольника главного [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна.  
  
 В следующем примере показан код для создания <xref:System.Windows.Interop.HwndSource> объекта и добавления в него визуальных объектов.  
  
> [!NOTE]
> Свойству <xref:System.Windows.Interop.HwndSource> объекта присваивается первый визуальный объект, добавленный в главное [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окно. <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Корневой визуальный объект определяет верхний узел дерева визуальных объектов. Все последующие визуальные объекты, добавленные [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в главное окно, добавляются как дочерние объекты.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Реализация фильтра сообщений Win32  
 Ведущему [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окну для визуальных объектов требуется процедура фильтрации сообщений окна для обработки сообщений, отправляемых в окно из очереди приложения. Оконная процедура получает сообщения от [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] системы. Это могут быть входные сообщения или сообщения управления окнами. Сообщение можно обработать в процедуре окна или передать системе для обработки по умолчанию.  
  
 <xref:System.Windows.Interop.HwndSource> Объект, определенный как родительский для визуальных объектов, должен ссылаться на процедуру фильтрации сообщений окна, которую вы задаете. При создании <xref:System.Windows.Interop.HwndSource> объекта <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> задайте для свойства значение, ссылающееся на процедуру окна.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 В следующем примере показан код для обработки сообщений при отпускании левой и правой кнопок мыши. Значение координаты в положении нажатия мыши содержится в значении `lParam` параметра.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Обработка сообщений Win32  
 Код в следующем примере показывает, как выполняется проверка попадания для иерархии визуальных объектов, содержащихся в главном [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окне. Можно определить, находится ли точка в пределах геометрии визуального объекта, используя <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метод для указания корневого визуального объекта и значения координаты для проверки попадания. В этом случае корневой визуальный объект является значением <xref:System.Windows.Interop.HwndSource.RootVisual%2A> свойства <xref:System.Windows.Interop.HwndSource> объекта.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Дополнительные сведения о проверке нажатия для визуальных объектов см. [в разделе Проверка попадания на визуальном уровне](hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Interop.HwndSource>
- [Проверка нажатия с помощью примера взаимодействия Win32](https://go.microsoft.com/fwlink/?LinkID=159995)
- [Проверка нажатия на визуальном уровне](hit-testing-in-the-visual-layer.md)
