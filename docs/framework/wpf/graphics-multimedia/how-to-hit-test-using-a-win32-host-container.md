---
title: "Практическое руководство. Проверка попадания курсора с помощью вложенного контейнера Win32 | Microsoft Docs"
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
  - "проверка нажатия, использование контейнеров размещения Win32"
  - "визуальные объекты, проверка нажатия"
  - "контейнеры размещения Win32, проверка нажатия"
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Проверка попадания курсора с помощью вложенного контейнера Win32
Если визуальные объекты создаются в окне [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], то для таких визуальных объектов можно использовать вложенный контейнер окна.  Чтобы обрабатывать события для содержащихся визуальных объектов, необходимо выполнять обработку сообщений, которые передаются в фильтрующий цикл обработки сообщений вложенного контейнера окна.  Дополнительные сведения о способах размещения визуальных объектов в окне [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] см. в разделе [Руководство по размещению визуальных объектов в приложении Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md).  
  
## Пример  
 В следующем коде показана настройка обработчиков событий мыши для окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], используемого в качестве вложенного контейнера для визуальных объектов.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 Следующий пример показывает, как установить [проверку попадания курсора](GTMT) в ответ на перехват конкретных событий мыши.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Объект <xref:System.Windows.Interop.HwndSource> представляет содержимое [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] в окне [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]. Значение свойства <xref:System.Windows.Interop.HwndSource.RootVisual%2A> объекта <xref:System.Windows.Interop.HwndSource> представляет самый верхний узел в иерархии [визуального дерева](GTMT).  
  
 Полный пример объектов проверки нажатия с помощью вложенного контейнера Win32 см. в разделе [Пример проверки нажатия с помощью взаимодействия Win32](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
## См. также  
 <xref:System.Windows.Interop.HwndSource>   
 [Проверка попадания на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [Руководство по размещению визуальных объектов в приложении Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)