---
title: "Совместное использование циклов обработки сообщений между Win32 и WPF | Microsoft Docs"
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
  - "взаимодействие [WPF], Win32"
  - "циклы обработки сообщений [WPF]"
  - "совместное использование циклов обработки сообщений"
  - "код Win32, совместное использование циклов обработки сообщений"
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Совместное использование циклов обработки сообщений между Win32 и WPF
В этом разделе описана реализация цикла обработки сообщений для взаимодействия с [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] при помощи существующего доступа к циклу обработки сообщений в <xref:System.Windows.Threading.Dispatcher> или при помощи создания отдельного цикла обработки сообщения на стороне [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] кода взаимодействия.  
  
## Диспетчер компонента и цикл обработки сообщений  
 Обычный скрипт для взаимодействия и поддержки события клавиатуры является реализация <xref:System.Windows.Interop.IKeyboardInputSink> или подкласса из классов, в которых уже реализован <xref:System.Windows.Interop.IKeyboardInputSink>, таких как <xref:System.Windows.Interop.HwndSource> или <xref:System.Windows.Interop.HwndHost>.  Тем не менее, поддержка приемника клавиатуры не обращается ко всем возможным циклам обработки сообщений при отправке и получении сообщений через ваши границы взаимодействия.  Чтобы помочь формализовать архитектуру цикла обработки сообщений приложения, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет класс <xref:System.Windows.Interop.ComponentDispatcher>, который определяет простой протокол для выполнения цикла обработки сообщений.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> представляет собой статический класс, предоставляющий несколько членов.  Область каждого метода неявно привязана к вызывающему потоку.  Цикл обработки сообщений должен вызывать некоторые из этих [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] в критические моменты времени \(как определенный в следующем разделе\).  
  
 <xref:System.Windows.Interop.ComponentDispatcher> предоставляет события, которые могут прослушивать другие компоненты \(такие как приемник клавиатуры\).  Класс <xref:System.Windows.Threading.Dispatcher> вызывает соответствующие методы <xref:System.Windows.Interop.ComponentDispatcher> в соответствующей последовательности.  При реализации вашего собственного цикла обработки сообщений, ваш код ответственен за вызов методов <xref:System.Windows.Interop.ComponentDispatcher> аналогичным образом.  
  
 Вызов методов <xref:System.Windows.Interop.ComponentDispatcher> в потоке только вызовет обработчики событий, которые были зарегистрированы в этом потоке.  
  
## Написание Циклов Обработки Сообщений  
 Ниже приведен список членов <xref:System.Windows.Interop.ComponentDispatcher> которые вы будете использовать при написании собственного цикла обработки сообщений:  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: ваш цикл обработки сообщений должен вызывать его для того, чтобы показать, что поток является модальным.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: ваш цикл обработки сообщений должен вызывать его для того, чтобы показать, что поток стал немодальным.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>. Цикл обработки сообщений должен вызывать этот метод для указания того, что <xref:System.Windows.Interop.ComponentDispatcher> должен вызвать событие <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>.  <xref:System.Windows.Interop.ComponentDispatcher> не вызовет событие <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>, если свойству <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> присвоено значение `true`, но циклы обработки сообщений могут вызвать метод <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>, даже если <xref:System.Windows.Interop.ComponentDispatcher> не может ответить на него, пока находится в модальном состоянии.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: ваш цикл обработки сообщений должны вызывать его для того, чтобы показать, что доступно новое сообщение.  Возвращаемое значение указывает на то, обработал ли слушатель события <xref:System.Windows.Interop.ComponentDispatcher> сообщение.  Если <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> возвращает `true`\(обработано\), то диспетчер в дальнейшем ничего не делает с сообщением.  Если возвращаемое значение равно `false`, диспетчер ожидает вызов функции `TranslateMessage` в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], а затем вызывает `DispatchMessage`.  
  
## Использование Диспетчера Компонента и Обработки Существующих Сообщений  
 Ниже приведен список членов <xref:System.Windows.Interop.ComponentDispatcher> которые вы будете использовать во встроенном [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] цикле обработки сообщений:  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>. Определяет, является ли приложение модальным \(например, был передан модальный цикл обработки сообщений\).  <xref:System.Windows.Interop.ComponentDispatcher> может отслеживать это состояние, так как класс содержит счетчик вызовов <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> и <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> из цикла обработки сообщений.  
  
-   События <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> и <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> соответствуют стандартным правилам для вызова делегата.  Делегаты вызываются в неопределенном порядке, и все делегаты вызываются, даже если первый из них помечает сообщение как обработанное.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>. Указывает подходящее и эффективное время для обработки бездействия \(когда нет других ожидающих сообщений для потока\).  Событие <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> не вызывается, если поток является модальным.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: вызывается для всех сообщений, что сообщение загружает процессы.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: вызывается для всех сообщений, которые не были обработаны во время <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Сообщение считается обработанным, если после события <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> или события <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> параметр `handled`, передаваемый по ссылке в данных события, равен `true`.  Обработчики событий должны игнорировать сообщение, если `handled` равен `true`, так как это означает, что другой обработчик обработал сообщение первым.  Обработчики событий могут изменить сообщение для обоих событий.  Диспетчер должен отправлять измененное сообщение, а не исходное.  Событие <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> доставляется всем слушателям, но архитектурно необходимо только верхнеуровневое окно, содержащее HWND, у которого нужные сообщения должны вызвать код в ответ на сообщение.  
  
## Как HwndSource Рассматривает События Диспетчера Компонента  
 Если <xref:System.Windows.Interop.HwndSource> является окном верхнего уровня \(нет родительского HWND\), оно будет зарегистрировано с <xref:System.Windows.Interop.ComponentDispatcher>.  Если вызывается <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>, и если сообщение предназначено для <xref:System.Windows.Interop.HwndSource> или дочерних окон, <xref:System.Windows.Interop.HwndSource> вызывает его последовательность приемника клавиатуры <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A>.  
  
 Если <xref:System.Windows.Interop.HwndSource> не является окном верхнего уровня \(имеет родителя HWND\), оно обработано не будет.  Только окно верхнего уровня ожидает выполнения обработки и оно должно быть окном верхнего уровня с поддержкой приемника клавиатуры в качестве части любого скрипта взаимодействия.  
  
 Если <xref:System.Windows.Interop.HwndHost.WndProc%2A> в <xref:System.Windows.Interop.HwndSource> вызывается без соответствующего вызова метода приемника клавиатуры, ваше приложение получит более высокоуровневые события клавиатуры, такие как <xref:System.Windows.UIElement.KeyDown>.  Однако не будут вызваны такие методы приемника клавиатуры, которые нарушают возможности модели ввода клавиатуры, такие как поддержка клавиш доступа.  Это может произойти, поскольку цикл обработки сообщений не уведомил соответствующий поток на <xref:System.Windows.Interop.ComponentDispatcher>, или поскольку родительское HWND не вызвало соответствующие ответы приемника клавиатуры.  
  
 Сообщение, которое переходит приемнику клавиатуры не может быть отправлено HWND, если вы добавили ловушки для этого сообщения с помощью метода <xref:System.Windows.Interop.HwndSource.AddHook%2A>.  Сообщение может быть непосредственно обработано на уровне загрузки сообщений и не отправлено функции `DispatchMessage`.  
  
## См. также  
 <xref:System.Windows.Interop.ComponentDispatcher>   
 <xref:System.Windows.Interop.IKeyboardInputSink>   
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Модель потоков](../../../../docs/framework/wpf/advanced/threading-model.md)   
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)