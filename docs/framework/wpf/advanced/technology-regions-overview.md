---
title: "Общие сведения об областях применения технологий | Microsoft Docs"
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
  - "airspace"
  - "взаимодействие [WPF], airspace"
  - "код Win32, airspace"
  - "код Win32, области окон"
  - "код Win32, взаимодействие с WPF"
  - "области окон"
ms.assetid: b7cc350f-b9e2-48b1-be14-60f3d853222e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения об областях применения технологий
Если в приложении используется несколько технологий представления, например, WPF, Win32 и DirectX, они должны совместно использовать области визуализации в общем окне верхнего уровня.  В этом разделе рассматриваются проблемы, которые могут оказывать влияние на визуализацию и выходные данные взаимодействующего приложения WPF.  
  
## Области  
 В окне верхнего уровня каждый дескриптор HWND, который обозначает одну из технологий взаимодействующего приложения, имеет собственную область \(также называемую "airspace"\).  Каждый пиксель в окне принадлежит ровно одному дескриптору HWND, который определяет область для этого HWND  \(строго говоря, при наличии нескольких дескрипторов HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] существует несколько областей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]; однако в целях данного материала предполагается, что имеется только одна область\).  Область подразумевает, что все уровни или другие окна, которые могут отображаться над этим пикселем во время существования приложения, должны быть частью одной и той же технологии уровня визуализации.  Отображение точек [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] над [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приводит к нежелательным результатам и настоятельно не рекомендуется при взаимодействии с [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].  
  
### Примеры областей  
 На следующем рисунке показано приложение, в котором одновременно используются технологии [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  В каждой технологии используется собственный отдельный, неперекрывающийся набор пикселей, поэтому проблемы областей отсутствуют.  
  
 ![Окно без ограничения пространства](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle01.png "MigrationInteropArchitectArticle01")  
  
 Предположим, что в приложении используется позиция указателя мыши для создания анимации, которая пытается выполнить визуализацию в любой из трех областей.  Независимо от того, какая технология применяется для анимации, ее использование приведет к нарушению областей двух других технологий.  На следующем рисунке показана попытка отобразить круг WPF в области Win32.  
  
 ![Схема взаимодействия](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle02.png "MigrationInteropArchitectArticle02")  
  
 Другим примером нарушения областей является применение эффектов прозрачности или альфа\-смешения между различными технологиями.  На следующем рисунке поле [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] нарушает области [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)].  Поскольку точки в этом поле [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являются полупрозрачными, они должны принадлежать [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], что невозможно.  Это приводит к нарушению областей и невозможности построения приложения.  
  
 ![Схема взаимодействия](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle03.png "MigrationInteropArchitectArticle03")  
  
 В трех предыдущих примерах используются прямоугольные области, однако форма областей может быть произвольной.  Например, в области может присутствовать отверстие.  На следующем рисунке показана область [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] с прямоугольным отверстием, в котором помещаются области [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)].  
  
 ![Схема взаимодействия](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle04.png "MigrationInteropArchitectArticle04")  
  
 Области могут быть полностью непрямоугольными или иметь произвольную форму, описываемую дескриптором региона HRGN [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
 ![Схема взаимодействия](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle05.png "MigrationInteropArchitectArticle05")  
  
## Прозрачность и окна верхнего уровня  
 Диспетчер окон Windows в действительности поддерживает обработку только дескрипторов HWND [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Поэтому каждый объект <xref:System.Windows.Window> системы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является дескриптором HWND.  Дескриптор HWND <xref:System.Windows.Window> должен соответствовать общим правилам, установленным для дескрипторов HWND.  В коде [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] этого дескриптора HWND могут выполняться любые операции, поддерживаемые в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].  Однако для взаимодействия с другими дескрипторами HWND на рабочем столе в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] должны соблюдаться правила обработки и отрисовки [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализуется поддержка непрямоугольных окон с помощью дескрипторов HRGN [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], а также поддержка многоуровневых окон для попиксельной альфа\-версии.  
  
 Постоянные ключевые альфа\-значения и значения цвета не поддерживаются.  Возможности многоуровневых окон в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] зависят от платформы.  
  
 Использование многоуровневых окон позволяет сделать все окно прозрачным \(полупрозрачным\), указав альфа\-значение, которое применяется к каждой точке окна.  \(В [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] фактически поддерживается поточечное альфа\-смешение. Однако на практике этот режим очень трудно использовать, поскольку в нем необходимо вручную рисовать дескриптор HWND каждого дочернего окна, включая диалоговые окна и раскрывающиеся меню.\)  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживаются дескрипторы HRGN, однако для них не предусмотрены управляемые интерфейсы [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].  Можно использовать вызов неуправляемого кода и класс <xref:System.Windows.Interop.HwndSource> для вызова соответствующего интерфейса [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].  Дополнительные сведения см. в разделе [Вызов неуправляемых функций из управляемого кода](../Topic/Calling%20Native%20Functions%20from%20Managed%20Code.md).  
  
 Многоуровневые окна [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживают различные возможности в разных операционных системах.  Это происходит потому, что [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] для визуализации, а многоуровневые окна в первую очередь предназначены не для визуализации [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)], а для визуализации [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)].  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает аппаратное ускорение многоуровневых окон в операционной системе [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] или более поздних версиях.  Аппаратное ускорение многоуровневых окон в [!INCLUDE[TLA2#tla_winxp](../../../../includes/tla2sharptla-winxp-md.md)] требует поддержки [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)], поэтому доступные возможности будут зависеть от версии [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)], установленной на компьютере.  
  
-   В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не поддерживаются ключевые значения прозрачности цвета, поскольку в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не обеспечивается гарантированную точечную отрисовку необходимого цвета, особенно при использовании аппаратного ускорения.  
  
-   Если приложение выполняется в операционной системе [!INCLUDE[TLA2#tla_winxp](../../../../includes/tla2sharptla-winxp-md.md)], многоуровневые окна, расположенные над поверхностями [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)], мерцают при отображении приложения [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)].  \(Используется следующая фактическая последовательность отрисовки: многоуровневое окно скрывается в [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)], после чего оно отрисовывается в [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] и повторно отображается в [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)].\)  Это ограничение также распространяется на многоуровневые окна, отличные от [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## См. также  
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Пошаговое руководство. Размещение часов WPF в Win32](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-clock-in-win32.md)   
 [Размещение содержимого Win32 в WPF](../../../../docs/framework/wpf/advanced/hosting-win32-content-in-wpf.md)