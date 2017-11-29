---
title: "Windows Forms и архитектура ввода взаимодействия WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- input architecture [WPF interoperability]
- messages [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- modeless forms [WPF]
- ElementHost keyboard and messages [WPF]
- keyboard interoperation [WPF]
- WindowsFormsHost keyboard and messages [WPF]
- modeless dialog boxes [WPF]
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b48b5d78ce3136146f7ad17f859a489b5556a000
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Windows Forms и архитектура ввода взаимодействия WPF
Взаимодействие между [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] требует, чтобы обе технологии обработки входных данных соответствующие клавиатуры. Описывается, как реализовать эти технологии и чтобы обеспечить корректное взаимодействие в гибридных приложениях обработки сообщений клавиатуры.  
  
 В этом разделе содержатся следующие подразделы:  
  
-   Немодальные формы и диалоговые окна  
  
-   WindowsFormsHost клавиатуры и обработки сообщений  
  
-   ElementHost клавиатуры и обработки сообщений  
  
## <a name="modeless-forms-and-dialog-boxes"></a>Немодальные формы и диалоговые окна  
 Вызовите <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> метод <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента для размыкания Безрежимные формы или диалогового окна поле из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложения.  
  
 Вызовите <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> метод <xref:System.Windows.Forms.Integration.ElementHost> управления, чтобы открыть немодальный [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-приложение на основе.  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>WindowsFormsHost клавиатуры и обработки сообщений  
 Если они размещаются в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложение, на основе [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] клавиатуры и обработка состоит из следующих сообщений:  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> Класс получает сообщения из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] цикл обработки сообщений, который реализован <xref:System.Windows.Interop.ComponentDispatcher> класса.  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> Класс создает суррогат [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] цикл обработки сообщений, чтобы убедиться, что обычные [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] происходит обработка клавиатуры.  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> Класс реализует <xref:System.Windows.Interop.IKeyboardInputSink> интерфейс для координации управления фокусом с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элементы управления регистрируют себя и запускают их циклы обработки сообщений.  
  
 В следующих разделах описаны эти части процесса более подробно.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>Получение сообщений из цикла обработки сообщений WPF  
 <xref:System.Windows.Interop.ComponentDispatcher> Класс реализует диспетчер цикла обработки сообщений для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Interop.ComponentDispatcher> Класс предоставляет ловушки, позволяющие внешними клиентами для фильтрации сообщений до [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обрабатывает их.  
  
 Дескрипторы взаимодействия реализацию <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> событие, которое позволяет [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления для обработки сообщений перед [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления.  
  
### <a name="surrogate-windows-forms-message-loop"></a>Цикл обработки сообщений символов-заместителей Windows Forms  
 По умолчанию <xref:System.Windows.Forms.Application?displayProperty=nameWithType> класс содержит цикл обработки сообщений основной для [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] приложений. Во время взаимодействия [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сообщение цикла не обрабатывает сообщения. Поэтому эту логику необходимо воспроизвести. Обработчик <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> событий выполняет следующие действия:  
  
1.  Фильтры сообщений с помощью <xref:System.Windows.Forms.IMessageFilter> интерфейса.  
  
2.  Вызовы <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> метод.  
  
3.  Преобразует и отправляет сообщение, если это необходимо.  
  
4.  Передает сообщение для размещения элемента управления, если другие элементы управления не обрабатывает сообщение.  
  
### <a name="ikeyboardinputsink-implementation"></a>Реализация IKeyboardInputSink  
 Суррогатный цикл обработки сообщений обрабатывает управление клавиатуры. Таким образом <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> — единственный <xref:System.Windows.Interop.IKeyboardInputSink> член, который требует реализации в <xref:System.Windows.Forms.Integration.WindowsFormsHost> класса.  
  
 По умолчанию <xref:System.Windows.Interop.HwndHost> возвращает `false` для его <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> реализации. Это предотвращает переход из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> Реализация <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> метод выполняет следующие действия:  
  
1.  Находит первый или последний [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления, содержащийся в <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента управления, которые могут получать фокус. Выбор элемента управления зависит от обхода сведений.  
  
2.  Устанавливает фокус на элементе управления и возвращает `true`.  
  
3.  Если элемент управления не может получить фокус, возвращает `false`.  
  
### <a name="windowsformshost-registration"></a>WindowsFormsHost регистрации  
 Если дескриптор окна <xref:System.Windows.Forms.Integration.WindowsFormsHost> создается элемент управления, <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент управления вызывает внутренний статический метод, который регистрирует его присутствие для цикла обработки сообщений.  
  
 Во время регистрации <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления проверяет цикл обработки сообщений. Если цикл обработки сообщений не был запущен, <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> будет создан обработчик событий. Цикл обработки сообщений считается запущенным при <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> присоединен обработчик событий.  
  
 При уничтожении дескриптора окна <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления удаляет себя из регистрации.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>ElementHost клавиатуры и обработки сообщений  
 Если они размещаются в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] приложения, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] клавиатуры и обработка состоит из следующих сообщений:  
  
-   <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>, и <xref:System.Windows.Interop.IKeyboardInputSite> реализации интерфейсов.  
  
-   Переход между элементами и клавишами со стрелками.  
  
-   Клавиши команд и диалоговых окон.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]Обработка сочетаний клавиш.  
  
 В следующих разделах описаны более подробно эти части.  
  
### <a name="interface-implementations"></a>Реализации интерфейсов  
 В [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], сообщения клавиатуры маршрутизируются в дескриптор окна элемента управления, который имеет фокус. В <xref:System.Windows.Forms.Integration.ElementHost> управления, эти сообщения маршрутизируются в размещенный элемент. Чтобы выполнить это, <xref:System.Windows.Forms.Integration.ElementHost> управления предоставляет <xref:System.Windows.Interop.HwndSource> экземпляра. Если <xref:System.Windows.Forms.Integration.ElementHost> элемент управления имеет фокус, <xref:System.Windows.Interop.HwndSource> экземпляр направляет большинство клавиатуры, чтобы можно было обработать по [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> класса.  
  
 <xref:System.Windows.Interop.HwndSource> Класс реализует <xref:System.Windows.Interop.IKeyboardInputSink> и <xref:System.Windows.Interop.IKeyboardInputSite> интерфейсов.  
  
 Взаимодействие клавиатуры основывается на реализации <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> метод для обработки клавиши TAB и клавишами со ключа ввода, который перемещает фокус элементов.  
  
### <a name="tabbing-and-arrow-keys"></a>Между приложениями и клавиш со стрелками  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Логику выбора сопоставляется <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> и <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> методы для реализации ВКЛАДКУ и стрелкой ключа навигации. Переопределение <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> метод выполняет это сопоставление.  
  
### <a name="command-keys-and-dialog-box-keys"></a>Сочетания клавиш и диалоговых окон  
 Чтобы предоставить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] первому возможность обрабатывать клавиши команд и диалоговых окон, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] команды предварительной обработки подключен к <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> метод. Переопределение <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> метод объединяет две технологии.  
  
 С <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> метод, размещенные элементы можно обрабатывать все сообщение о нажатии клавиши, например WM_KEYUP WM_KEYDOWN, WM_SYSKEYDOWN или WM_SYSKEYUP, включая команды клавиши, такие как TAB, ввод, ESC и стрелка. Если сообщение о нажатии клавиши не обрабатывается, оно отправляется вверх [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] иерархии для обработки.  
  
### <a name="accelerator-processing"></a>Обработка сочетаний клавиш  
 Для правильной обработки [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сочетаний клавиш обработки должен быть подключен к [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> класса. Кроме того все сообщения WM_CHAR должны быть правильно маршрутизированы в размещенные элементы.  
  
 Так как значение по умолчанию <xref:System.Windows.Interop.HwndSource> реализация <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> возвращает `false`, сообщений WM_CHAR обрабатываются с использованием следующую логику:  
  
-   <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> Метод переопределяется, чтобы убедиться, что все сообщения WM_CHAR перенаправляются в размещенные элементы.  
  
-   Если нажата клавиша ALT, сообщение — WM_SYSCHAR. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]не обрабатывает это сообщение с помощью <xref:System.Windows.Forms.Control.IsInputChar%2A> метод. Таким образом <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> метод переопределяется для запроса [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> на зарегистрированное сочетание клавиш. Если зарегистрированный ускоритель найден, <xref:System.Windows.Input.AccessKeyManager> обрабатывает его.  
  
-   Если не нажата клавиша ALT, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> класс обрабатывает необработанные входные данные. Если входное значение ускоритель <xref:System.Windows.Input.AccessKeyManager> обрабатывает его. <xref:System.Windows.Input.InputManager.PostProcessInput> Событие обрабатывается для сообщений WM_CHAR, которые не были обработаны.  
  
 Когда пользователь нажимает клавишу ALT, визуальные подсказки сочетаний клавиш отображаются на всей форме. Для поддержки данной возможности всех <xref:System.Windows.Forms.Integration.ElementHost> элементов управления в форме active получают сообщения WM_SYSKEYDOWN, независимо от того, что элемент управления имеет фокус.  
  
 Сообщения отправляются только в <xref:System.Windows.Forms.Integration.ElementHost> элементов управления в активной формы.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
