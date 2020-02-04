---
title: Совместное использование циклов обработки сообщений между Win32 и WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
ms.openlocfilehash: e1b96284d69645876d3e383beb03a2cc540d8b7b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731718"
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Совместное использование циклов обработки сообщений между Win32 и WPF
В этом разделе описано, как реализовать цикл обработки сообщений для взаимодействия с [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]с помощью существующего риска цикла обработки сообщений в <xref:System.Windows.Threading.Dispatcher> или путем создания отдельного цикла обработки сообщений на стороне Win32 кода взаимодействия.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>Компонентдиспатчер и цикл обработки сообщений  
 Обычным сценарием поддержки взаимодействия и событий клавиатуры является реализация <xref:System.Windows.Interop.IKeyboardInputSink>или подкласс классов, которые уже реализуют <xref:System.Windows.Interop.IKeyboardInputSink>, например <xref:System.Windows.Interop.HwndSource> или <xref:System.Windows.Interop.HwndHost>. Однако поддержка приемника клавиатуры не поддерживает все возможные потребности в цикле обработки сообщений, которые могут возникнуть при отправке и получении сообщений через границы взаимодействия. Чтобы помочь в формализации архитектуры циклов обработки сообщений приложений, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет класс <xref:System.Windows.Interop.ComponentDispatcher>, который определяет простой протокол для выполнения цикла обработки сообщений.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> является статическим классом, предоставляющим несколько членов. Область каждого метода неявно привязана к вызывающему потоку. Цикл обработки сообщений должен вызывать некоторые из этих API в критические моменты времени (как определено в следующем разделе).  
  
 <xref:System.Windows.Interop.ComponentDispatcher> предоставляет события, которые могут прослушивать другие компоненты (например, приемник клавиатуры). Класс <xref:System.Windows.Threading.Dispatcher> вызывает все соответствующие методы <xref:System.Windows.Interop.ComponentDispatcher> в соответствующей последовательности. Если вы реализуете собственный цикл обработки сообщений, код отвечает за вызов методов <xref:System.Windows.Interop.ComponentDispatcher> аналогичным образом.  
  
 Вызов методов <xref:System.Windows.Interop.ComponentDispatcher> в потоке приведет к вызову только тех обработчиков событий, которые были зарегистрированы в этом потоке.  
  
## <a name="writing-message-loops"></a>Написание циклов сообщений  
 Ниже приведен контрольный список элементов <xref:System.Windows.Interop.ComponentDispatcher>, которые будут использоваться при написании собственного цикла обработки сообщений:  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: цикл сообщений должен вызывать его, чтобы указать, что поток является модальным.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: цикл обработки сообщений должен вызвать его, чтобы указать, что поток вернулся в немодальный.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: цикл обработки сообщений должен вызывать этот метод, чтобы указать, что <xref:System.Windows.Interop.ComponentDispatcher> должен вызвать событие <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>. <xref:System.Windows.Interop.ComponentDispatcher> не будет вызывать <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>, если <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> `true`, но циклы сообщений могут вызывать <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>, даже если <xref:System.Windows.Interop.ComponentDispatcher> не может ответить на него в модальном состоянии.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: цикл сообщений должен вызвать этот метод, чтобы указать, что доступно новое сообщение. Возвращаемое значение показывает, обрабатывалось ли сообщение прослушивателем <xref:System.Windows.Interop.ComponentDispatcher> события. Если <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> возвращает `true` (обрабатывается), диспетчер не должен ничего делать дальше с сообщением. Если возвращаемое значение равно `false`, диспетчер должен вызвать функцию Win32 `TranslateMessage`, а затем вызвать `DispatchMessage`.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>Использование Компонентдиспатчер и существующей обработки сообщений  
 Ниже приведен контрольный список элементов <xref:System.Windows.Interop.ComponentDispatcher>, которые будут использоваться, если вы полагаетесь на внутреннюю [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ный цикл обработки сообщений.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: Возвращает значение, указывающее, было ли приложение удалено (например, был отправлен модальный цикл обработки сообщений). <xref:System.Windows.Interop.ComponentDispatcher> может контролировать это состояние, так как класс поддерживает количество <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> и <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> вызовов из цикла обработки сообщений.  
  
- события <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> и <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> соответствуют стандартным правилам для вызовов делегатов. Делегаты вызываются в неопределенном порядке, и все делегаты вызываются, даже если первый из них помечает сообщение как обработанное.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: указывает правильное и эффективное время для обработки бездействия (для потока нет других ожидающих сообщений). <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> не будет вызываться, если поток является модальным.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: вызывается для всех сообщений, обрабатываемых конвейером сообщений.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: вызывается для всех сообщений, которые не были обработаны во время <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Сообщение считается обработанным, если после события <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> или события <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> `handled` параметр, передаваемый по ссылке в данных события, `true`. Обработчики событий должны игнорировать сообщение, если `handled` `true`, так как это означает, что другой обработчик обработал сообщение первым. Обработчики событий для обоих событий могут изменять сообщение. Диспетчер должен отправлять измененное сообщение, а не исходное сообщение без изменений. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> доставляется во все прослушиватели, но архитектурная цель состоит в том, что только окно верхнего уровня, содержащее HWND, в течение которого целевые сообщения должны вызывать код в ответ на сообщение.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>Как HwndSource обрабатывает события Компонентдиспатчер  
 Если <xref:System.Windows.Interop.HwndSource> является окном верхнего уровня (без родительского HWND), оно будет зарегистрировано в <xref:System.Windows.Interop.ComponentDispatcher>. Если возникает <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>, и если сообщение предназначено для <xref:System.Windows.Interop.HwndSource> или дочерних окон, <xref:System.Windows.Interop.HwndSource> вызывает последовательность приемников клавиатуры <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A><xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A>.  
  
 Если <xref:System.Windows.Interop.HwndSource> не является окном верхнего уровня (имеет родительский HWND), обработка не выполняется. Для обработки требуется только окно верхнего уровня, а ожидается окно верхнего уровня с поддержкой приемника клавиатуры в рамках любого сценария взаимодействия.  
  
 Если <xref:System.Windows.Interop.HwndHost.WndProc%2A> в <xref:System.Windows.Interop.HwndSource> вызывается без вызова соответствующего метода приемника клавиатуры, приложение получит события клавиатуры более высокого уровня, такие как <xref:System.Windows.UIElement.KeyDown>. Однако методы приемника клавиатуры не вызываются, что позволяет обойти такие функции модели ввода с клавиатуры, как поддержка ключа доступа. Это может произойти из-за того, что цикл обработки сообщений неправильно уведомил соответствующий поток на <xref:System.Windows.Interop.ComponentDispatcher>или потому, что родительский HWND не вызывал правильные ответы на приемники клавиатуры.  
  
 Сообщение, которое передается в приемник клавиатуры, может не отправляться в HWND, если вы добавили обработчики для этого сообщения с помощью метода <xref:System.Windows.Interop.HwndSource.AddHook%2A>. Сообщение может быть обработано на уровне приема сообщений напрямую и не отправлено в функцию `DispatchMessage`.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Interop.ComponentDispatcher>
- <xref:System.Windows.Interop.IKeyboardInputSink>
- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
- [Потоковая модель](threading-model.md)
- [Общие сведения о входных данных](input-overview.md)
