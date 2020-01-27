---
title: Архитектура ввода Windows Forms и WPF Interop
titleSuffix: ''
ms.date: 03/30/2017
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
ms.openlocfilehash: f79971ba13691ccc36420e39696b7b8a46e5ce0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745047"
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Windows Forms и архитектура ввода взаимодействия WPF
Для взаимодействия между [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] требуется, чтобы обе технологии имели соответствующую клавиатурную обработку ввода. В этом разделе описывается, как эти технологии реализуют обработку клавиатуры и сообщений для обеспечения беспрепятственного взаимодействия в гибридных приложениях.  
  
 В этом разделе содержатся следующие подразделы:  
  
- Немодальные формы и диалоговые окна  
  
- WindowsFormsHost клавиатуры и обработки сообщений  
  
- Обработка клавиатуры и сообщений ElementHost  
  
## <a name="modeless-forms-and-dialog-boxes"></a>Немодальные формы и диалоговые окна  
 Вызовите метод <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> для элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>, чтобы открыть немодальную форму или диалоговое окно из приложения на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Вызовите метод <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> для элемента управления <xref:System.Windows.Forms.Integration.ElementHost>, чтобы открыть немодальную страницу [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложении на основе [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>WindowsFormsHost клавиатуры и обработки сообщений  
 При размещении приложения на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] обработка клавиатуры и сообщений состоит из следующих компонентов:  
  
- Класс <xref:System.Windows.Forms.Integration.WindowsFormsHost> получает сообщения из цикла сообщений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], который реализуется классом <xref:System.Windows.Interop.ComponentDispatcher>.  
  
- Класс <xref:System.Windows.Forms.Integration.WindowsFormsHost> создает суррогатный [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] цикл обработки сообщений, чтобы обеспечить нормальную [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]ную обработку клавиатуры.  
  
- Класс <xref:System.Windows.Forms.Integration.WindowsFormsHost> реализует интерфейс <xref:System.Windows.Interop.IKeyboardInputSink> для координации управления фокусом с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Элементы управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> регистрируются самостоятельно и начинают циклы сообщений.  
  
 В следующих разделах эти части процесса описаны более подробно.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>Получение сообщений из цикла обработки сообщений WPF  
 Класс <xref:System.Windows.Interop.ComponentDispatcher> реализует диспетчер циклов обработки сообщений для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Класс <xref:System.Windows.Interop.ComponentDispatcher> предоставляет обработчики, позволяющие внешним клиентам фильтровать сообщения перед тем, как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обрабатывает их.  
  
 Реализация взаимодействия обрабатывает событие <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>, которое позволяет элементам управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] обрабатывать сообщения до [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления.  
  
### <a name="surrogate-windows-forms-message-loop"></a>Цикл обработки сообщений суррогатного Windows Forms  
 По умолчанию класс <xref:System.Windows.Forms.Application?displayProperty=nameWithType> содержит основной цикл обработки сообщений для [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] приложений. Во время взаимодействия цикл обработки сообщений [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не обрабатывает сообщения. Таким образом, эта логика должна быть воспроизведена. Обработчик события <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> выполняет следующие действия:  
  
1. Фильтрует сообщение с помощью интерфейса <xref:System.Windows.Forms.IMessageFilter>.  
  
2. Вызывает метод <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType>.  
  
3. Переводит и отправляет сообщение, если оно требуется.  
  
4. Передает сообщение в элемент управления размещения, если другие элементы управления не обрабатывают сообщение.  
  
### <a name="ikeyboardinputsink-implementation"></a>Реализация IKeyboardInputSink  
 Суррогатный цикл обработки сообщений обрабатывает управление с помощью клавиатуры. Таким образом, метод <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> является единственным элементом <xref:System.Windows.Interop.IKeyboardInputSink>, для которого требуется реализация в классе <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
 По умолчанию класс <xref:System.Windows.Interop.HwndHost> возвращает `false` для своей реализации <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A>. Это не позволяет переходить от элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] к элементу управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>ная реализация метода <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> выполняет следующие действия.  
  
1. Находит первый или последний элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], который содержится в элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> и может получать фокус. Выбор элемента управления зависит от сведений об обходах.  
  
2. Устанавливает фокус на элемент управления и возвращает `true`.  
  
3. Если элемент управления не может получить фокус, функция возвращает `false`.  
  
### <a name="windowsformshost-registration"></a>Регистрация WindowsFormsHost  
 При создании обработчика окна <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> вызывает внутренний статический метод, регистрирующий его присутствие в цикле обработки сообщений.  
  
 Во время регистрации элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> проверяет цикл обработки сообщений. Если цикл обработки сообщений не запущен, создается обработчик событий <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>. Цикл обработки сообщений считается выполняющимся при присоединении обработчика событий <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>.  
  
 При уничтожении маркера окна элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> удаляет себя из регистрации.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>Обработка клавиатуры и сообщений ElementHost  
 При размещении в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обработка клавиатуры и сообщений состоит из следующих компонентов:  
  
- реализации интерфейса <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>и <xref:System.Windows.Interop.IKeyboardInputSite>.  
  
- Переходы и клавиши со стрелками.  
  
- Ключи команд и диалоговые окна.  
  
- [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]ная обработка ускорителя.  
  
 В следующих разделах эти компоненты описаны более подробно.  
  
### <a name="interface-implementations"></a>Реализации интерфейса  
 В [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]сообщения клавиатуры направляются в маркер окна элемента управления, который находится в фокусе. В элементе управления <xref:System.Windows.Forms.Integration.ElementHost> эти сообщения направляются в размещенный элемент. Для этого элемент управления <xref:System.Windows.Forms.Integration.ElementHost> предоставляет экземпляр <xref:System.Windows.Interop.HwndSource>. Если элемент управления <xref:System.Windows.Forms.Integration.ElementHost> имеет фокус, то экземпляр <xref:System.Windows.Interop.HwndSource> направляет большинство вводимых с клавиатуры данных, чтобы их можно было обработать с помощью класса [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager>.  
  
 Класс <xref:System.Windows.Interop.HwndSource> реализует интерфейсы <xref:System.Windows.Interop.IKeyboardInputSink> и <xref:System.Windows.Interop.IKeyboardInputSite>.  
  
 Взаимодействие с клавиатурой зависит от реализации метода <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> для управления вводом клавиши TAB и клавиши со стрелкой, которая перемещает фокус из размещенных элементов.  
  
### <a name="tabbing-and-arrow-keys"></a>Переходы и клавиши со стрелками  
 Логика выбора [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставлена с методами <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> и <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> для реализации навигации клавишей TAB и клавиши со стрелкой. Это сопоставление достигается при переопределении метода <xref:System.Windows.Forms.Integration.ElementHost.Select%2A>.  
  
### <a name="command-keys-and-dialog-box-keys"></a>Ключи команд и диалоговые окна  
 Чтобы придать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] первой возможности обрабатывать ключи команд и диалоговые ключи, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Предварительная обработка команд подключается к методу <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>. Переопределение метода <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> соединяет две технологии.  
  
 При использовании метода <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> размещенные элементы могут выполнять любые ключевые сообщения, такие как WM_KEYDOWN, WM_KEYUP, WM_SYSKEYDOWN или WM_SYSKEYUP, включая клавиши команд, такие как TAB, ENTER, ESC и клавиши со стрелками. Если сообщение ключа не обрабатывается, оно отправляется вверх по иерархии [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-предка для обработки.  
  
### <a name="accelerator-processing"></a>Обработка ускорителя  
 Чтобы правильно обработать ускорители, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]ная обработка ускорителя должна быть подключена к классу [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager>. Кроме того, все сообщения WM_CHAR должны быть правильно направлены в размещенные элементы.  
  
 Поскольку реализация <xref:System.Windows.Interop.HwndSource> по умолчанию метода <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> возвращает `false`, WM_CHAR сообщения обрабатываются с помощью следующей логики:  
  
- Метод <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> переопределяется, чтобы обеспечить перенаправление всех сообщений WM_CHAR в размещенные элементы.  
  
- Если нажата клавиша ALT, сообщение будет WM_SYSCHAR. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не выполняет предварительную обработку этого сообщения с помощью метода <xref:System.Windows.Forms.Control.IsInputChar%2A>. Таким образом, метод <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> переопределяется для запроса <xref:System.Windows.Input.AccessKeyManager> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для зарегистрированного ускорителя. Если зарегистрированное сочетание клавиш найдено, <xref:System.Windows.Input.AccessKeyManager> обрабатывает его.  
  
- Если клавиша ALT не нажата, класс [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> обрабатывает необработанные входные данные. Если входные данные являются ускорителем, <xref:System.Windows.Input.AccessKeyManager> обрабатывает его. Событие <xref:System.Windows.Input.InputManager.PostProcessInput> обрабатывается для WM_CHAR сообщений, которые не были обработаны.  
  
 Когда пользователь нажимает клавишу ALT, визуальные подсказки ускорителя отображаются на всей форме. Для поддержки такого поведения все элементы управления <xref:System.Windows.Forms.Integration.ElementHost> в активной форме получают WM_SYSKEYDOWN сообщения, независимо от того, какой элемент управления имеет фокус.  
  
 Сообщения отправляются только <xref:System.Windows.Forms.Integration.ElementHost> элементам управления в активной форме.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
