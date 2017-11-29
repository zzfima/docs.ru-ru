---
title: "Совместное использование циклов обработки сообщений между Win32 и WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dcf8baa87038bc5625d46968b39d759daae25cbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Совместное использование циклов обработки сообщений между Win32 и WPF
В этом разделе описывается реализация цикла обработки сообщений для взаимодействия с [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], при помощи существующего сообщения раскрытия цикла в <xref:System.Windows.Threading.Dispatcher> или путем создания отдельного цикла обработки сообщения на [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] параллельно кода взаимодействия.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>Диспетчер компонента и цикл обработки сообщений  
 Обычный сценарий для взаимодействия и поддержки события клавиатуры является реализация <xref:System.Windows.Interop.IKeyboardInputSink>, или подкласса из классов, которые уже реализуют <xref:System.Windows.Interop.IKeyboardInputSink>, такие как <xref:System.Windows.Interop.HwndSource> или <xref:System.Windows.Interop.HwndHost>. Поддержка приемник клавиатуры не учитывает все возможные циклам обработки сообщений при отправке и получении сообщений через ваши границы взаимодействия. Чтобы помочь формализовать архитектуру цикла обработки сообщений приложения, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет <xref:System.Windows.Interop.ComponentDispatcher> класса, который определяет простой протокол для цикла обработки сообщений.  
  
 <xref:System.Windows.Interop.ComponentDispatcher>является статическим классом, предоставляющий несколько членов. Область каждого метода неявно привязана в вызывающий поток. Цикл обработки сообщений должен вызывать некоторые из этих [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] в критические моменты времени (как определено в следующем разделе).  
  
 <xref:System.Windows.Interop.ComponentDispatcher>Предоставляет события, которые могут прослушивать другие компоненты (такие как приемник клавиатуры). <xref:System.Windows.Threading.Dispatcher> Класса вызывает соответствующие <xref:System.Windows.Interop.ComponentDispatcher> методы в соответствующей последовательности. При реализации собственного цикла обработки сообщений, код отвечает за вызов метода <xref:System.Windows.Interop.ComponentDispatcher> методы таким же образом.  
  
 Вызов <xref:System.Windows.Interop.ComponentDispatcher> методы в потоке только вызовет обработчики событий, которые были зарегистрированы в этом потоке.  
  
## <a name="writing-message-loops"></a>Написание циклов обработки сообщений  
 Ниже приведен перечень <xref:System.Windows.Interop.ComponentDispatcher> члены, которые вы будете использовать при написании собственного цикла обработки сообщений:  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: ваш цикл обработки сообщений должен вызывать его, чтобы указать, что поток является модальным.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: ваш цикл обработки сообщений должен вызывать его, чтобы указать, что поток вернулся немодальным.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: ваш цикл обработки сообщений должен вызывать его, чтобы указать, что <xref:System.Windows.Interop.ComponentDispatcher> должен вызывать <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> событий. <xref:System.Windows.Interop.ComponentDispatcher>не создает <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> Если <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> — `true`, но циклы обработки сообщений, можно вызвать <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> даже в том случае, если <xref:System.Windows.Interop.ComponentDispatcher> не может ответить на него в модальное состояние.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: ваш цикл обработки сообщений должен вызывать его, чтобы указать, что доступно новое сообщение. Возвращаемое значение указывает, является ли прослушиватель для <xref:System.Windows.Interop.ComponentDispatcher> сообщение обработано событие. Если <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> возвращает `true` (обработано), диспетчер в дальнейшем ничего с сообщением. Если возвращается значение `false`, диспетчер ожидает вызов [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] функция `TranslateMessage`, затем вызовите `DispatchMessage`.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>Использование диспетчера компонента и обработки существующих сообщений  
 Ниже приведен перечень <xref:System.Windows.Interop.ComponentDispatcher> члены, которые будет использовать, если вы полагаетесь на встроенном [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] цикл обработки сообщений.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: возвращает, стал ли приложение модальное (например, цикл модальное сообщение было помещено). <xref:System.Windows.Interop.ComponentDispatcher>может отслеживать это состояние, так как класс содержит счетчик <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> и <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> вызовы от цикла обработки сообщений.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>и <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> события соответствовать стандартным правилам для вызова делегата. Делегаты вызываются в неопределенном порядке, и вызываются все делегаты, даже если первый из них помечает сообщение как обработанное.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: указывает на соответствующий и эффективный время простоя обработки (нет других ожидающих сообщений для потока). <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>не будет вызываться, если поток является модальным.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: вызывается для всех сообщений, обрабатываемых в генераторе сообщений.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: вызывается для всех сообщений, которые не были обработаны во время <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Сообщение считается обработанным, если после <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> событий или <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> событий, `handled` параметр, передаваемый по ссылке в данных события `true`. Обработчики событий должны игнорировать сообщение, если `handled` — `true`, так как это означает, что другой обработчик обработал сообщение первым. Обработчики событий для обоих событий могут изменить сообщение. Диспетчер должен отправлять измененное сообщение, а не исходное сообщение без изменений. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>доставляется всем слушателям, но архитектурно это только окна верхнего уровня, содержащий HWND, с которой сообщения должны вызвать код в ответ на сообщение.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>Как HwndSource Рассматривает события диспетчера компонента  
 Если <xref:System.Windows.Interop.HwndSource> является окном верхнего уровня (нет родительского HWND), будет зарегистрирован <xref:System.Windows.Interop.ComponentDispatcher>. Если <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> возникает, если сообщение предназначено для <xref:System.Windows.Interop.HwndSource> или дочерних окон, <xref:System.Windows.Interop.HwndSource> вызовы его <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> последовательность приемника клавиатуры.  
  
 Если <xref:System.Windows.Interop.HwndSource> не является окном верхнего уровня (имеет родителя HWND), обработано не будет. Только окно верхнего уровня должен выполнять обработку и оно должно быть окном верхнего уровня с поддержкой приемника клавиатуры как часть любого скрипта взаимодействия.  
  
 Если <xref:System.Windows.Interop.HwndHost.WndProc%2A> на <xref:System.Windows.Interop.HwndSource> вызывается без вызова метода приемника сочетания, ваше приложение получит более высокоуровневые события клавиатуры например <xref:System.Windows.UIElement.KeyDown>. Тем не менее не методы приемника клавиатуры будет вызываться, которые нарушают возможности модели ввода клавиатуры, такие как поддержка клавиш доступа. Это может происходить, когда цикл обработки сообщений не уведомил соответствующий поток на <xref:System.Windows.Interop.ComponentDispatcher>, или поскольку родительское HWND не вызвало соответствующие ответы приемника клавиатуры.  
  
 Это сообщение в приемник клавиатуры может не должны отправляться HWND обработчики для этого сообщения, добавленные с помощью <xref:System.Windows.Interop.HwndSource.AddHook%2A> метод. Сообщение может быть обработано на уровне загрузки сообщений напрямую и не отправлено `DispatchMessage` функции.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Interop.ComponentDispatcher>  
 <xref:System.Windows.Interop.IKeyboardInputSink>  
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Потоковая модель](../../../../docs/framework/wpf/advanced/threading-model.md)  
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)
