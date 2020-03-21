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
ms.openlocfilehash: d04357e0770bbf8eebe8f40a86a19ddc9baae3ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187430"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Руководство по размещению визуальных объектов в приложении Win32
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако, если у вас есть значительные инвестиции в код [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Win32, возможно, будет более эффективным добавить функциональность в приложение, а не переписывать код. Для обеспечения поддержки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Подсистем Win32 и графики, используемых одновременно в приложении, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предусмотрен механизм размещения объектов в окне Win32.  
  
 В этом учебнике описывается, как написать образец приложения, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [Хит-тест с Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting), который размещает визуальные объекты в окне Win32.  

<a name="requirements"></a>
## <a name="requirements"></a>Требования  
 Этот учебник предполагает базовое знакомство с программированием win32 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и Win32. Для базового [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] введения в программирование, см. [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md) Для введения в Win32 программирования, см любой из многочисленных книг по этому вопросу, в *частности, программирование Windows* Чарльз Петцольд.  
  
> [!NOTE]
> Этот учебник включает ряд примеров кода из связанного образца приложения. Однако для удобства чтения он не содержит полный пример кода. Для полного кода [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)образца см.  
  
<a name="creating_the_host_win32_window"></a>
## <a name="creating-the-host-win32-window"></a>Создание окна размещения Win32  
 Ключом к [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] размещению <xref:System.Windows.Interop.HwndSource> объектов в окне Win32 является класс. Этот класс заворачивает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объекты в окно Win32, позволяя их включать в ваше [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] окно в качестве ребенка.  
  
 В следующем примере показан <xref:System.Windows.Interop.HwndSource> код для создания объекта в качестве окна контейнера Win32 для визуальных объектов. Чтобы установить стиль окна, положение и другие параметры для <xref:System.Windows.Interop.HwndSourceParameters> окна Win32, используйте объект.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> Стоимость <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> свойства не может быть установлена в WS_EX_TRANSPARENT. Это означает, что окно win32 не может быть прозрачным. По этой причине цвет фона окна узла Win32 установлен на тот же цвет фона, что и родительское окно.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Добавление визуальных объектов в окно размещения Win32  
 После создания окна контейнера Win32 для визуальных объектов можно добавить визуальные объекты. Вы хотите убедиться, что любые преобразования визуальных объектов, таких как анимация, не выходят за пределы прямоугольника окна Win32.  
  
 В следующем примере показан <xref:System.Windows.Interop.HwndSource> код для создания объекта и добавления к нему визуальных объектов.  
  
> [!NOTE]
> Свойство <xref:System.Windows.Interop.HwndSource.RootVisual%2A> <xref:System.Windows.Interop.HwndSource> объекта устанавливается на первый визуальный объект, добавленный в окно узла Win32. Корневой визуальный объект определяет верхний узел дерева визуальных объектов. Любые последующие визуальные объекты, добавленные в окно узла Win32, добавляются в качестве детских объектов.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>
## <a name="implementing-the-win32-message-filter"></a>Реализация фильтра сообщений Win32  
 Окно узла Win32 для визуальных объектов требует процедуры фильтра сообщений окон для обработки сообщений, отправляемых в окно из очереди приложения. Процедура окна получает сообщения из системы Win32. Это могут быть входные сообщения или сообщения управления окнами. Сообщение можно обработать в процедуре окна или передать системе для обработки по умолчанию.  
  
 Объект, <xref:System.Windows.Interop.HwndSource> который вы определили как родитель для визуальных объектов, должен ссылаться на процедуру фильтра оконных сообщений, которую вы предоставляете. При создании <xref:System.Windows.Interop.HwndSource> объекта установите <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> свойство для ссылки на процедуру окна.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 В следующем примере показан код для обработки сообщений при отпускании левой и правой кнопок мыши. Значение координат позиции попадания мыши содержится в значении `lParam` параметра.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>
## <a name="processing-the-win32-messages"></a>Обработка сообщений Win32  
 Код в следующем примере показывает, как выполняется хит-тест против иерархии визуальных объектов, содержащихся в окне узла Win32. Можно определить, находится ли точка в геометрии визуального <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> объекта, используя метод для определения корневого визуального объекта и значения координат, против которых можно попасть в тест. В этом случае корневым визуальным <xref:System.Windows.Interop.HwndSource.RootVisual%2A> объектом <xref:System.Windows.Interop.HwndSource> является значение свойства объекта.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Для получения дополнительной информации о тестировании хитов против визуальных объектов, [см.](hit-testing-in-the-visual-layer.md)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Interop.HwndSource>
- [Проверка нажатия с помощью примера взаимодействия Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)
- [Проверка попадания на визуальном уровне](hit-testing-in-the-visual-layer.md)
