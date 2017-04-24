---
title: "Руководство по размещению визуальных объектов в приложении Win32 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "размещение, визуальные объекты в коде Win32"
  - "визуальные объекты в коде Win32"
  - "код Win32, визуальные объекты"
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Руководство по размещению визуальных объектов в приложении Win32
Клиент [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений.  Однако, если имеются существенные преимущества в коде [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], возможно, более эффективным будет добавление функциональности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложение вместо переписывания вашего кода.  Для обеспечения поддержки графических подсистем [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], одновременно используемых в приложении, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет механизм для размещения объектов в окне [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
 В этом руководстве описан процесс написания приложения [Пример проверки нажатий, включающий взаимодействие с Win32](http://go.microsoft.com/fwlink/?LinkID=159995), в котором визуальные объекты [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] размещены в окне [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
   
  
<a name="requirements"></a>   
## Требования  
 Это руководство предполагает начальное знакомство с программированием [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Введение в программирование [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Пошаговое руководство. Начало работы с WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  Введение в программирование [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] содержится в любой из многочисленных книг на данную тему, в частности, *Programming Windows* Charles Petzold.  
  
> [!NOTE]
>  Это руководство включает ряд примеров кода из сопровождающего его образца.  Тем не менее, для удобства чтения, он не включает в себя полный код примера.  Полный код примера см. в разделе [Пример проверки нажатий, включающий взаимодействие с Win32](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## Создание главного окна Win32  
 Ключом для размещению объектов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окне [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] является класс <xref:System.Windows.Interop.HwndSource>.  Этот класс переносит объекты [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окне [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], позволяя им присоединиться к вашему [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] в качестве дочернего окна.  
  
 В следующем примере показан код для создания объекта <xref:System.Windows.Interop.HwndSource> в качестве контейнера окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] для визуальных объектов.  Для задания стиля окна, положения и других параметров окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] используйте объект <xref:System.Windows.Interop.HwndSourceParameters>.  
  
 [!code-csharp[VisualsHitTesting#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
>  Значению свойства <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> не может быть равно WS\_EX\_TRANSPARENT.  Это означает, что главное окно [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] не может быть прозрачным.  По этой причине цвету фона главного окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] задается тот же цвет фона, что и у родительского окна.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## Добавление визуального объекта в главное окно Win32  
 После создания главного окна контейнера [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] для визуальных объектов на него можно добавить визуальные объекты.  Необходимо убедиться, что любые преобразования визуальных объектов, такие как анимация, не выходят за пределы ограничивающего прямоугольника главного окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
 В следующем примере показан код для создания объекта <xref:System.Windows.Interop.HwndSource> и добавления визуальных объектов к нему.  
  
> [!NOTE]
>  Свойство <xref:System.Windows.Interop.HwndSource.RootVisual%2A> объекта <xref:System.Windows.Interop.HwndSource> установлено в значение первого визуального объекта, добавленного в главное окно [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Корневой визуальный объект определяет самый верхний узел дерева визуальных объектов.  Все последующие визуальные объекты, добавленные в главное окно [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], добавляются как дочерние объекты.  
  
 [!code-csharp[VisualsHitTesting#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## Реализация фильтра сообщений Win32  
 Для главного окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] визуальных объектов требуется процедура фильтрации сообщений окна для обработки сообщений, отправляемых из очереди приложения окну.  Процедура окна получает сообщения из системы [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Это могут быть входные сообщения или сообщения от управления окнами.  Можно дополнительно обработать сообщение в процедуре окна или передать сообщение системе для обработки по умолчанию.  
  
 На объект <xref:System.Windows.Interop.HwndSource>, который определен вами как родительский для визуальных объектов, должна ссылаться предоставленная вами процедура фильтрации сообщении.  При создании объекта <xref:System.Windows.Interop.HwndSource>, установите свойству <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> значение ссылки на процедуру окна.  
  
 [!code-csharp[VisualsHitTesting#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 В следующем примере показан код для обработки сообщений при нажатии левой и правой кнопок мыши.  Значение координаты положения мыши содержатся в значении параметра `lParam`.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## Обработка сообщений Win32  
 В коде следующего примера показано, как выполняется проверка посещение по иерархии визуальных объектов, содержащихся в главном окне [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Можно определить, расположена ли точка внутри визуального объекта, с помощью метода <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>, указав корневой визуальный объект и значение координаты, которую следует проверить.  В этом случае корневой визуальный объект является значением свойства <xref:System.Windows.Interop.HwndSource.RootVisual%2A> объекта <xref:System.Windows.Interop.HwndSource>.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Дополнительные сведения о тестировании на посещение визуальных объектов содержатся в разделе [Проверка попадания на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
## См. также  
 <xref:System.Windows.Interop.HwndSource>   
 [Hit Test with Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995)   
 [Проверка попадания на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)