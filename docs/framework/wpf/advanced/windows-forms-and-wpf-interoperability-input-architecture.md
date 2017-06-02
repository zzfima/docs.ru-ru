---
title: "Windows Forms и архитектура ввода взаимодействия WPF | Microsoft Docs"
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
  - "ElementHost - клавиатура и сообщения"
  - "архитектура ввода [взаимодействие с WPF]"
  - "взаимодействие [WPF], Windows Forms"
  - "взаимодействие с клавиатурой [WPF]"
  - "WPF - сообщения"
  - "[WPF] - безрежимные диалоговые окна"
  - "безрежимные формы"
  - "Windows Forms [WPF], взаимодействие с"
  - "Windows Forms, взаимодействие с WPF"
  - "WindowsFormsHost - клавиатура и сообщения"
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Windows Forms и архитектура ввода взаимодействия WPF
Взаимодействие между [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] требует, чтобы обе технологии имели соответствующую обработку ввода с клавиатуры.  В этом подразделе описывается, как эти технологии реализуют обработку клавиатуры и сообщений, чтобы обеспечить корректное взаимодействие в гибридных приложениях.  
  
 В этом разделе содержатся следующие подразделы:  
  
-   Немодальные формы и диалоговые окна  
  
-   Обработка клавиатуры и сообщений WindowsFormsHost  
  
-   Обработка клавиатуры и сообщений ElementHost  
  
## Немодальные формы и диалоговые окна  
 Вызовите метод <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> для элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>, чтобы открыть немодальную форму или диалоговое окно из приложения на базе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Вызовите метод <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> для элемента управления <xref:System.Windows.Forms.Integration.ElementHost>, чтобы открыть немодальную страницу [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложении на базе [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
## Обработка клавиатуры и сообщений WindowsFormsHost  
 При размещении приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обработка клавиатуры и сообщений [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] состоит из следующего:  
  
-   Класс <xref:System.Windows.Forms.Integration.WindowsFormsHost> получает сообщения из цикла сообщений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], который реализован классом <xref:System.Windows.Interop.ComponentDispatcher>.  
  
-   Класс <xref:System.Windows.Forms.Integration.WindowsFormsHost> создает суррогатный цикл обработки сообщений [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], чтобы убедиться в том, что выполняется обычная обработка клавиатуры [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   Класс <xref:System.Windows.Forms.Integration.WindowsFormsHost> реализует интерфейс <xref:System.Windows.Interop.IKeyboardInputSink> для координации управления фокусом с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Элементы управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> регистрируют себя и запускают их циклы обработки сообщений.  
  
 В следующих разделах эти части процесса описаны более подробно.  
  
### Получение сообщений из цикла обработки сообщений WPF  
 Класс <xref:System.Windows.Interop.ComponentDispatcher> реализует диспетчер цикла обработки сообщений для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Класс <xref:System.Windows.Interop.ComponentDispatcher> предоставляет ловушки, позволяющие внешним клиентам фильтровать сообщения до того, как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обработает их.  
  
 Межоперационная реализация обрабатывает событие <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName>, что позволяет элементам управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] обрабатывать сообщения до элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Суррогатный цикл обработки сообщений Windows Forms  
 По умолчанию класс <xref:System.Windows.Forms.Application?displayProperty=fullName> содержит основной цикл обработки сообщений для приложений [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Во время взаимодействия цикла обработки сообщений [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не обрабатывает сообщения.  Таким образом, эта логика должна быть воспроизведена.  Обработчик события <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName> выполняет следующие шаги:  
  
1.  Фильтрует сообщение с помощью интерфейса <xref:System.Windows.Forms.IMessageFilter>.  
  
2.  Вызывает метод <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=fullName>.  
  
3.  Переводит и отправляет сообщение, если это необходимо.  
  
4.  Передает сообщение размещающему элементу управления, если другие элементы управления не обрабатывают сообщение.  
  
### Реализация IKeyboardInputSink  
 Суррогатный цикл обработки сообщений обрабатывает управление клавиатурой.  Таким образом, метод <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=fullName> является единственным членом <xref:System.Windows.Interop.IKeyboardInputSink>, который требует реализации в классе <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
 По умолчанию класс <xref:System.Windows.Interop.HwndHost> возвращает `false` для реализации его <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A>.  Это предотвращает переход из элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 Реализация <xref:System.Windows.Forms.Integration.WindowsFormsHost> для метода <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=fullName> выполняет следующие шаги:  
  
1.  Находит первый или последний элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], который содержит элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> и который может получить фокус.  Выбор элемента управления зависит от обхода сведений.  
  
2.  Устанавливает фокус элементу управления и возвращает значение `true`.  
  
3.  Если элемент управления не может получить фокус, он возвращает `false`.  
  
### Регистрация WindowsFormsHost  
 При создании дескриптора окна для элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>, элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> вызывает внутренний статический метод, который регистрирует его присутствие для цикла обработки сообщений.  
  
 Во время регистрации элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> проверяет цикл обработки сообщений.  Если цикл обработки сообщений не был запущен, создается обработчик событий <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName>.  Цикл обработки сообщений считается запущенным при присоединении обработчика событий <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName>.  
  
 При уничтожении дескриптора окна элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> удаляет себя из регистрации.  
  
## Обработка клавиатуры и сообщений ElementHost  
 При размещении приложением [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] обработка клавиатуры и сообщений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] состоит из следующего:  
  
-   Реализация интерфейсов <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink> и <xref:System.Windows.Interop.IKeyboardInputSite>.  
  
-   Переходы и клавиши со стрелкой.  
  
-   Клавиши команд и диалоговых окон.  
  
-   Обработка с помощью ускорителя[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 В следующих разделах это описывается более подробно.  
  
### Реализация интерфейсов  
 В приложении [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сообщения клавиатуры маршрутизируются в дескриптор окна элемента управления, на котором установлен фокус.  В элементе управления <xref:System.Windows.Forms.Integration.ElementHost> эти сообщения маршрутизируются в размещенный элемент управления.  Чтобы выполнить это, элемент управления <xref:System.Windows.Forms.Integration.ElementHost> предоставляет экземпляр <xref:System.Windows.Interop.HwndSource>.  Если элемент управления <xref:System.Windows.Forms.Integration.ElementHost> имеет фокус, экземпляр <xref:System.Windows.Interop.HwndSource> маршрутизирует почти весь клавиатурный ввод таким образом, чтобы он мог быть обработан с помощью класса [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager>.  
  
 Класс <xref:System.Windows.Interop.HwndSource> реализует интерфейсы <xref:System.Windows.Interop.IKeyboardInputSink> и <xref:System.Windows.Interop.IKeyboardInputSite>.  
  
 Взаимодействие клавиатуры основывается на реализации метода <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> для обработки клавиши TAB и клавиши со стрелкой, которые перемещают фокус элементов.  
  
### Переходы и клавиши со стрелкой  
 Логика выбора [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставляется с методами <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> и <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> для реализации переходов по TAB и клавише со стрелкой.  Переопределение метода <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> выполняет это сопоставление.  
  
### Клавиши команд и диалоговых окон  
 Чтобы предоставить приложению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] первому возможность обрабатывать клавиши команд и диалоговых окон, обработка команд [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] подключается к методу <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>.  Переопределение метода <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=fullName> объединяет две технологии.  
  
 С помощью метода <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> размещенные элементы могут обрабатывать все клавишные сообщения, такие как WM\_KEYDOWN, WM\_SYSKEYDOWN, WM\_KEYUP или WM\_SYSKEYUP, включая клавиши команд, такие как TAB, ВВОД, ESC и клавиши со стрелками.  Если сообщение о нажатии клавиши не обрабатывается, оно отправляется вверх по иерархии [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] для обработки.  
  
### Обработка с помощью ускорителя  
 Для правильной обработки сочетаний клавиш обработка с помощью сочетания клавиш [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] должна быть подключена к классу [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager>.  Кроме того все сообщения WM\_CHAR должны быть правильно маршрутизированы в размещенные элементы.  
  
 Поскольку по умолчанию реализация <xref:System.Windows.Interop.HwndSource> метода <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> возвращает значение `false`, сообщения WM\_CHAR обрабатываются с помощью следующей логики:  
  
-   Метод <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=fullName> переопределяется так, чтобы гарантировать, что все сообщения WM\_CHAR перенаправляются в размещенные элементы.  
  
-   Если нажата клавиша ALT, сообщением является WM\_SYSCHAR.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не обрабатывает это сообщение с помощью метода <xref:System.Windows.Forms.Control.IsInputChar%2A>.  Поэтому метод <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> переопределяется так, чтобы отправить объекту [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> запрос на зарегистрированное сочетание клавиш.  Если зарегистрированный ускоритель найден, <xref:System.Windows.Input.AccessKeyManager> обрабатывает его.  
  
-   Если не нажата клавиша ALT, класс [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> обрабатывает необработанные входные данные.  Если входные данные являются ускорителем, <xref:System.Windows.Input.AccessKeyManager> обрабатывает его.  Событие <xref:System.Windows.Input.InputManager.PostProcessInput> обрабатывается для сообщений WM\_CHAR, которые не были обработаны.  
  
 Когда пользователь нажимает клавишу ALT, визуальные команды вызова ускорителя отображаются на всей форме.  Чтобы поддерживать такое поведение, все элементы управления <xref:System.Windows.Forms.Integration.ElementHost> на активной форме получают сообщения WM\_SYSKEYDOWN, независимо от того, какой элемента управления имеет фокус.  
  
 Сообщения отправляются только в элементы управления <xref:System.Windows.Forms.Integration.ElementHost> в активной форме.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>   
 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>   
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)