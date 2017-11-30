---
title: "Общие сведения о входных данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [WPF]
- input [WPF], overview
- keyboard focus [WPF]
- keyboard input [WPF]
- touch events [WPF]
- event routing [WPF]
- touch input [WPF]
- manipulation [WPF]
- logical focus [WPF]
- stylus input [WPF]
- text input [WPF]
- input events [WPF], handling
- WPF [WPF], input overview
- manipulation events [WPF]
- mouse input [WPF]
- mouse capture [WPF]
- focus [WPF]
- mouse position [WPF]
ms.assetid: ee5258b7-6567-415a-9b1c-c0cbe46e79ef
caps.latest.revision: "50"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c12d8655babeb45800f4a5c068cb2ab74faac3d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="input-overview"></a>Общие сведения о входных данных
Подсистема <a name="introduction"></a>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет мощный [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] для получения входных данных от разнообразных устройств, включая мышь, клавиатуру, сенсорный экран и перо. В этом разделе описываются службы, предоставляемые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и объясняется архитектура систем ввода.  
  
  
<a name="input_api"></a>   
## <a name="input-api"></a>API ввода  
 Основные входные [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] основано на базовых классах элемента: <xref:System.Windows.UIElement>, <xref:System.Windows.ContentElement>, <xref:System.Windows.FrameworkElement>, и <xref:System.Windows.FrameworkContentElement>.  Дополнительные сведения о базовых элементах см. в разделе [Обзор базовых элементов](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  Эти классы предоставляют функциональность для входных событий, связанных, например, с нажатием клавиш, кнопками мыши, колесиком мыши, движением мыши, управлением фокусом и захватом мыши. Благодаря помещению [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] ввода в базовые элементы, вместо того чтобы рассматривать все события ввода как службу, архитектура ввода позволяет событиям ввода поступать от конкретного объекта в пользовательском интерфейсе и поддерживать схему маршрутизации событий, при которой более чем один элемент имеет возможность обрабатывать событие ввода. Многие события ввода имеют пару связанных с ними событий.  Например, событие Нажатие клавиши связан с <xref:System.Windows.Input.Keyboard.KeyDown> и <xref:System.Windows.Input.Keyboard.PreviewKeyDown> события.  Различие этих событий заключается в способе их маршрутизации в целевой элемент.  События предварительного просмотра проходят вниз по дереву элементов от корневого элемента в целевой элемент.  События восходящей маршрутизации поднимаются от целевого элемента в корневой элемент.  Маршрутизация событий в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] рассматривается более подробно далее в этом обзоре и в разделе [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
### <a name="keyboard-and-mouse-classes"></a>Классы Keyboard и Mouse  
 Кроме ввода [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] в классах базовых элементов, <xref:System.Windows.Input.Keyboard> класса и <xref:System.Windows.Input.Mouse> классы предоставляют дополнительные [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] для работы с вводом мыши и клавиатуры.  
  
 Примерами входных [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] на <xref:System.Windows.Input.Keyboard> класса <xref:System.Windows.Input.Keyboard.Modifiers%2A> свойство, которое возвращает <xref:System.Windows.Input.ModifierKeys> в настоящее время нажаты и <xref:System.Windows.Input.Keyboard.IsKeyDown%2A> метод, который определяет, нажата ли указанный ключ.  
  
 В следующем примере используется <xref:System.Windows.Input.Keyboard.GetKeyStates%2A> метод для определения <xref:System.Windows.Input.Key> находится в отключенном состоянии.  
  
 [!code-csharp[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyArgsSnippetSample/CSharp/Window1.xaml.cs#keyeventargskeyboardgetkeystates)]
 [!code-vb[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyArgsSnippetSample/visualbasic/window1.xaml.vb#keyeventargskeyboardgetkeystates)]  
  
 Примерами входных [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] на <xref:System.Windows.Input.Mouse> класса <xref:System.Windows.Input.Mouse.MiddleButton%2A>, получающее состояние средней кнопки мыши, и <xref:System.Windows.Input.Mouse.DirectlyOver%2A>, которая получает элемента указатель мыши наведен.  
  
 В следующем примере определяется, является ли <xref:System.Windows.Input.Mouse.LeftButton%2A> мыши — в <xref:System.Windows.Input.MouseButtonState.Pressed> состояние.  
  
 [!code-csharp[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MouseRelatedSnippets/CSharp/Window1.xaml.cs#mouserelatedsnippetsgetleftbuttonmouse)]
 [!code-vb[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MouseRelatedSnippets/visualbasic/window1.xaml.vb#mouserelatedsnippetsgetleftbuttonmouse)]  
  
 <xref:System.Windows.Input.Mouse> И <xref:System.Windows.Input.Keyboard> классы рассматриваются более подробно в этом обзоре.  
  
### <a name="stylus-input"></a>Ввод с помощью пера  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]имеет встроенную поддержку <xref:System.Windows.Input.Stylus>.  <xref:System.Windows.Input.Stylus> — Популярный по рукописный ввод [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)].  Приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] могут обрабатывать перо как мышь с помощью [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] мыши, но [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также предоставляет перо как абстрактное устройство, использующее модель, аналогичную клавиатуре и мыши.  Все связанные с пером [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] содержат слово Stylus.  
  
 Поскольку перо может действовать как мышь, приложения, поддерживающие только ввод с помощью мыши, по-прежнему могут автоматически получать определенный уровень поддержки пера. При использовании пера таким образом приложение получает возможность обработать соответствующее событие пера, а затем обрабатывает соответствующее событие мыши. Кроме того, через абстрактное устройство «перо» доступны также службы более высокого уровня, например рукописный ввод.  Дополнительные сведения о рукописном вводе см. в разделе [Начало работы с рукописным вводом](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).  
  
<a name="event_routing"></a>   
## <a name="event-routing"></a>Маршрутизация событий  
 Объект <xref:System.Windows.FrameworkElement> может содержать другие элементы, как дочерние элементы в своей модели содержимого, образующие дерево элементов.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] родительский элемент может участвовать во вводе, направленном в его дочерние элементы или другие потомки, путем обработки событий. Это особенно полезно для построения элементов управления из меньших элементов управления; этот процесс называется «составление элемента управления» или «компоновка». Дополнительные сведения о деревьях элементов и их связи с маршрутами событий см. в разделе [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
 Маршрутизация событий — это процесс направления событий в несколько элементов, так что конкретный объект или элемент в маршруте может выбрать предоставление значительного отклика (посредством обработки) на событие, которое могло быть получено от другого элемента.  Перенаправленные события используют один из трех механизмов маршрутизации: прямую маршрутизацию, восходящую маршрутизацию и туннелирование.  При прямой маршрутизации уведомляется только исходный элемент и событие не перенаправляется ни в какие другие элементы. Тем не менее событие с прямой маршрутизацией предоставляет некоторые дополнительные возможности, доступные только для перенаправленных событий, в отличие от стандартных событий [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. Восходящая маршрутизация работает вверх по дереву элементов, уведомляя элемент, который является источником события, затем его родительский элемент и т. д.  Туннелирование начинается в корне дерева элементов и работает вниз, заканчивая элементом, который является источником.  Дополнительные сведения о перенаправленных событиях см. в разделе [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 События ввода [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обычно представлены парами, состоящими из событий нисходящей и восходящей маршрутизации.  События нисходящей маршрутизации отличаются от событий восходящей маршрутизации префиксом Preview.  Например <xref:System.Windows.Input.Mouse.PreviewMouseMove> является нисходящей версией события перемещения мыши и <xref:System.Windows.Input.Mouse.MouseMove> — восходящей версией этого события. Такое связывание событий представляет собой соглашение, которое реализуется на уровне элемента и не является неотъемлемой характеристикой системы событий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Дополнительные сведения см. в разделе «События ввода WPF» статьи [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
<a name="handling_input_events"></a>   
## <a name="handling-input-events"></a>Обработка событий ввода  
 Для получения входных данных в элементе обработчик событий должен быть связан с данным конкретным событием.  В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] это осуществляется напрямую: вы указываете имя события в качестве атрибута элемента, который будет перехватывать это событие.  Затем в качестве значения этого атрибута вы задаете имя обработчика событий, который можно определить на основе делегата.  Этот обработчик событий должен быть написан в коде, например на [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], и может быть включен в файл кода программной части.  
  
 События клавиатуры возникают, когда операционная система сообщает о действиях клавиш, которые происходят, когда фокус клавиатуры находится в элементе. События мыши и пера делятся на две категории: события, сообщающие об изменениях положения указателя относительно элемента, и события, сообщающие об изменениях состояния кнопок устройства.  
  
### <a name="keyboard-input-event-example"></a>Пример события ввода с клавиатуры  
 В следующем примере перехватывается событие нажатия клавиши со стрелкой влево.  Объект <xref:System.Windows.Controls.StackPanel> создается, имеет <xref:System.Windows.Controls.Button>.  Обработчик событий для ожидания нажатия клавиши со стрелкой влево присоединяется к <xref:System.Windows.Controls.Button> экземпляра.  
  
 Первый раздел примера создает <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.Button> и присоединяет обработчик событий для <xref:System.Windows.UIElement.KeyDown>.  
  
 [!code-xaml[InputOvw#Input_OvwKeyboardExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwkeyboardexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexampleuicodebehind)]  
  
 Второй раздел прописывается в коде, и в нем определяется обработчик событий.  При нажатии клавиши Стрелка влево и <xref:System.Windows.Controls.Button> фокус клавиатуры, программа запускает обработчик и <xref:System.Windows.Controls.Control.Background%2A> цвет <xref:System.Windows.Controls.Button> изменяется.  При нажатии клавиши, но не клавишу Стрелка влево <xref:System.Windows.Controls.Control.Background%2A> цвет <xref:System.Windows.Controls.Button> изменяется обратно на первоначальный.  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexamplehandlercodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexamplehandlercodebehind)]  
  
### <a name="mouse-input-event-example"></a>Пример события ввода с помощью мыши  
 В следующем примере <xref:System.Windows.Controls.Control.Background%2A> цвет <xref:System.Windows.Controls.Button> меняется, когда указатель мыши оказывается <xref:System.Windows.Controls.Button>.  <xref:System.Windows.Controls.Control.Background%2A> Цвет восстанавливается в том случае, когда указатель мыши покидает <xref:System.Windows.Controls.Button>.  
  
 Первый раздел примера создает <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.Button> управления и присоединяет обработчики событий для <xref:System.Windows.UIElement.MouseEnter> и <xref:System.Windows.UIElement.MouseLeave> событий для <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[InputOvw#Input_OvwMouseExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwmouseexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleuicodebehind)]  
  
 Второй раздел примера прописывается в коде, и в нем определяются обработчики событий.  Когда указатель мыши перемещается <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Control.Background%2A> цвет <xref:System.Windows.Controls.Button> изменяется на <xref:System.Windows.Media.Brushes.SlateGray%2A>.  Когда указатель мыши покидает <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Control.Background%2A> цвет <xref:System.Windows.Controls.Button> изменяется обратно на <xref:System.Windows.Media.Brushes.AliceBlue%2A>.  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleeneterhandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleeneterhandler)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleleavehandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleleavehandler)]  
  
<a name="text_input"></a>   
## <a name="text-input"></a>Текстовый ввод  
 <xref:System.Windows.ContentElement.TextInput> Событий позволяет ожидать ввода текста в аппаратно независимым способом. Клавиатура является основным средством ввода текста, но текст также можно вводить и с помощью речи, рукописного ввода и других устройств.  
  
 Для ввода с клавиатуры [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сначала вызывает соответствующие <xref:System.Windows.ContentElement.KeyDown> / <xref:System.Windows.ContentElement.KeyUp> события. Если эти события не обрабатываются, и клавиша является текстовой вместо (например ключа элемента управления) или сочетания клавиш, а затем <xref:System.Windows.ContentElement.TextInput> события.  Не всегда простое однозначное сопоставление между <xref:System.Windows.ContentElement.KeyDown> / <xref:System.Windows.ContentElement.KeyUp> и <xref:System.Windows.ContentElement.TextInput> событий из-за нескольких нажатий клавиш можно создавать один знак ввода текста и одного нажатия клавиш можно создать несколько символов строки.  В первую очередь это относится к таким языкам, как китайский, японский и корейский, которые используют [!INCLUDE[TLA#tla_ime#plural](../../../../includes/tlasharptla-imesharpplural-md.md)] для формирования тысяч возможных символов в соответствующем алфавите.  
  
 Когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отправляет <xref:System.Windows.ContentElement.KeyUp> / <xref:System.Windows.ContentElement.KeyDown> событий, <xref:System.Windows.Input.KeyEventArgs.Key%2A> задано значение <xref:System.Windows.Input.Key.System?displayProperty=nameWithType> Если нажатий клавиш может стать частью <xref:System.Windows.ContentElement.TextInput> события (Если сочетание клавиш ALT + S, например). Это позволяет коду в <xref:System.Windows.ContentElement.KeyDown> обработчик событий для проверки <xref:System.Windows.Input.Key.System?displayProperty=nameWithType> и, если он найден, оставьте обработки для обработчика сгенерированного впоследствии <xref:System.Windows.ContentElement.TextInput> событий. В этих случаях различные свойства <xref:System.Windows.Input.TextCompositionEventArgs> аргумент может использоваться для определения первоначальных нажатий клавиш. Аналогично Если [!INCLUDE[TLA2#tla_ime](../../../../includes/tla2sharptla-ime-md.md)] активен, <xref:System.Windows.Input.Key> имеет значение <xref:System.Windows.Input.Key.ImeProcessed?displayProperty=nameWithType>, и <xref:System.Windows.Input.KeyEventArgs.ImeProcessedKey%2A> дает первоначальное нажатие клавиши или клавиш.  
  
 В следующем примере определяется обработчик <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события и обработчик для <xref:System.Windows.UIElement.KeyDown> события.  
  
 Первый сегмент кода или разметки создает пользовательский интерфейс.  
  
 [!code-xaml[InputOvw#Input_OvwTextInputXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwtextinputxaml)]  
  
 [!code-csharp[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputuicodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputuicodebehind)]  
  
 Второй сегмент кода содержит обработчики событий.  
  
 [!code-csharp[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputhandlerscodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputhandlerscodebehind)]  
  
 Поскольку входные события восходящей по маршруту событий, <xref:System.Windows.Controls.StackPanel> получает входные данные, независимо от того, какой элемент имеет фокус клавиатуры. <xref:System.Windows.Controls.TextBox> Сначала уведомляется элемент управления и `OnTextInputKeyDown` обработчик вызывается только в том случае, если <xref:System.Windows.Controls.TextBox> не обработал входные данные. Если <xref:System.Windows.UIElement.PreviewKeyDown> событий используется вместо <xref:System.Windows.UIElement.KeyDown> событий, `OnTextInputKeyDown` сначала вызывается обработчик.  
  
 В этом примере логика обработки пишется два раза — один раз для CTRL+O и еще один раз для события нажатия кнопки. Это можно упростить, если вместо прямой обработки событий ввода использовать команды.  Команды описываются в этом обзоре и в разделе [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="touch_and_manipulation"></a>   
## <a name="touch-and-manipulation"></a>Касание и манипуляция  
 Новое оборудование и API в операционной системе Windows 7 дают приложениям возможность получать входные данные от нескольких касаний одновременно. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет приложениям обнаруживать сенсорный ввод и реагировать на него так же, как на другой ввод, например с помощью мыши или клавиатуры, путем создания событий при возникновении сенсорного ввода.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет два типа событий для сенсорного ввода: события касания и события манипуляции. События касания предоставляют необработанные данные о каждом пальце на сенсорном экране и его перемещениях. События манипуляции интерпретируют ввод как определенные действия. В этом разделе рассматриваются оба типа событий.  
  
### <a name="prerequisites"></a>Предварительные требования  
 Для разработки приложений, реагирующих на сенсорный ввод, необходимы следующие компоненты.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7.  
  
-   Устройство, которое поддерживает Windows Touch, например сенсорный экран.  
  
### <a name="terminology"></a>Терминология  
 При обсуждении сенсорного ввода используются следующие термины.  
  
-   **Касание** — это тип ввода пользователя, распознаваемый Windows 7. Обычно касание инициируется, когда пользователь прикасается пальцами к сенсорному экрану. Обратите внимание, что такие устройства, как сенсорная панель, обычно используемая в ноутбуках, не поддерживают касание, если подобное устройство просто преобразует положение и движение пальца как ввод с помощью мыши.  
  
-   **Мультикасание** — это касание, которое происходит одновременно в нескольких точках. Windows 7 и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживают мультикасание. Всякий раз, когда в документации для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] идет речь о касании, это относится и мультикасанию.  
  
-   **Манипуляция** происходит, когда касание интерпретируется как физическое действие, которое применяется к объекту. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], события манипуляции интерпретируют ввод как сдвиг, расширение или поворот.  
  
-   `touch device` — это устройство для сенсорного ввода, например одним пальцем на сенсорном экране.  
  
### <a name="controls-that-respond-to-touch"></a>Элементы управления, реагирующие на касания  
 Следующие элементы управления можно прокручивать, проводя пальцем по элементу управления, если имеется содержимое, которое находится вне области просмотра.  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.DataGrid>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.TextBox>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
 <xref:System.Windows.Controls.ScrollViewer> Определяет <xref:System.Windows.Controls.ScrollViewer.PanningMode%2A?displayProperty=nameWithType> присоединенное свойство, которое позволяет указать панорамирования сенсорный ввод включен ли горизонтальным, вертикальным, оба или ни один. <xref:System.Windows.Controls.ScrollViewer.PanningDeceleration%2A?displayProperty=nameWithType> Свойство указывает, насколько быстро замедляется прокрутка, когда пользователь отрывает палец с сенсорного экрана. <xref:System.Windows.Controls.ScrollViewer.PanningRatio%2A?displayProperty=nameWithType> Вложенное свойство задает коэффициент смещения прокрутки к смещению обработки преобразования.  
  
### <a name="touch-events"></a>События касания  
 Базовые классы <xref:System.Windows.UIElement>, <xref:System.Windows.UIElement3D>, и <xref:System.Windows.ContentElement>, определяют события, которые можно подписаться, приложение будет реагировать на touch. События касания полезны в тех случаях, когда приложение интерпретирует касание не как действие с объектом. Например, приложение, в котором пользователь может рисовать одним или несколькими пальцами, будет подписываться на события касания.  
  
 Все эти три класса определяют следующие события, которые ведут себя одинаково независимо от определяющего класса.  
  
-   <xref:System.Windows.UIElement.TouchDown>  
  
-   <xref:System.Windows.UIElement.TouchMove>  
  
-   <xref:System.Windows.UIElement.TouchUp>  
  
-   <xref:System.Windows.UIElement.TouchEnter>  
  
-   <xref:System.Windows.UIElement.TouchLeave>  
  
-   <xref:System.Windows.UIElement.PreviewTouchDown>  
  
-   <xref:System.Windows.UIElement.PreviewTouchMove>  
  
-   <xref:System.Windows.UIElement.PreviewTouchUp>  
  
-   <xref:System.Windows.UIElement.GotTouchCapture>  
  
-   <xref:System.Windows.UIElement.LostTouchCapture>  
  
 Как и события клавиатуры и мыши, события сенсорного ввода являются перенаправленными событиями. События нисходящей маршрутизации начинаются с `Preview`, а события восходящей маршрутизации — с `Touch`. Дополнительные сведения о перенаправленных событиях см. в разделе [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md). При обработке этих событий позицию ввода, относительно любого элемента, можно получить, вызвав <xref:System.Windows.Input.TouchEventArgs.GetTouchPoint%2A> или <xref:System.Windows.Input.TouchEventArgs.GetIntermediateTouchPoints%2A> метод.  
  
 Чтобы лучше объяснить взаимодействие между событиями касания, рассмотрим ситуацию, когда пользователь помещает один палец в элемент, а затем убирает палец из этого элемента. На следующем рисунке показано выполнение событий восходящей маршрутизации (для простоты события нисходящей маршрутизации не указаны).  
  
 ![Последовательность событий сенсорного экрана. ] (../../../../docs/framework/wpf/advanced/media/ndp-touchevents.png "NDP_TouchEvents")  
События касания  
  
 Последовательность событий на предыдущем рисунке приведена в следующем списке.  
  
1.  <xref:System.Windows.UIElement.TouchEnter> Событие происходит один раз, когда пользователь помещает палец на элемент.  
  
2.  <xref:System.Windows.UIElement.TouchDown> Событие происходит один раз.  
  
3.  <xref:System.Windows.UIElement.TouchMove> Событие возникает несколько раз, когда пользователь перемещает палец внутри элемента.  
  
4.  <xref:System.Windows.UIElement.TouchUp> Событие происходит один раз, когда пользователь отрывает палец из элемента.  
  
5.  <xref:System.Windows.UIElement.TouchLeave> Событие происходит один раз.  
  
 При использовании более двух пальцев, события возникают для каждого пальца.  
  
### <a name="manipulation-events"></a>События манипуляции  
 Для случаев, где приложение позволяет пользователю управлять объектом <xref:System.Windows.UIElement> класс определяет события манипуляции. В отличие от событий касания, которые сообщают только положение точки касания, события манипуляции сообщают, как можно интерпретировать ввод. Существует три типа манипуляции: сдвиг, расширение и поворот. В следующем списке показывается, как вызываются эти три типа манипуляции.  
  
-   Поместите палец на объект и переместите палец по сенсорному экрану, чтобы выполнить сдвиг. Обычно такое действие перемещает объект.  
  
-   Поместите два пальца на объект и сведите или разведите их, чтобы выполнить расширение. Обычно такое действие изменяет размеры объекта.  
  
-   Поместите два пальца на объект и поворачивайте их вокруг друг друга, чтобы выполнить действие поворота. Обычно такое действие выполняет циклический сдвиг объекта.  
  
 Можно одновременно выполнять несколько типов манипуляций.  
  
 Реализуя реагирование объектов на манипуляции, можно создать видимость инерции объекта. Тогда объекты смогут имитировать физический мир. Например, если вы достаточно сильно толкнете книгу по столу, то после того как вы ее отпустите, она продолжит движение. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет имитировать это поведение путем вызова событий манипуляции после того, как пальцы пользователя отпускают объект.  
  
 Сведения о том, как создать приложение, которое дает пользователю возможность перемещать, масштабировать и поворачивать объект, см. в статье [Пошаговое руководство. Создание первого приложения для обработки касаний](../../../../docs/framework/wpf/advanced/walkthrough-creating-your-first-touch-application.md).  
  
 <xref:System.Windows.UIElement> Определяет следующие события манипуляции.  
  
-   <xref:System.Windows.UIElement.ManipulationStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationStarted>  
  
-   <xref:System.Windows.UIElement.ManipulationDelta>  
  
-   <xref:System.Windows.UIElement.ManipulationInertiaStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationCompleted>  
  
-   <xref:System.Windows.UIElement.ManipulationBoundaryFeedback>  
  
 По умолчанию <xref:System.Windows.UIElement> не получает эти события манипуляции. Для получения событий обработки на <xref:System.Windows.UIElement>, задайте <xref:System.Windows.UIElement.IsManipulationEnabled%2A?displayProperty=nameWithType> для `true`.  
  
#### <a name="the-execution-path-of-manipulation-events"></a>Путь выполнения событий манипуляции  
 Рассмотрим сценарий, когда пользователь «бросает» объект. Пользователь ставит палец на объект, перемещает палец по сенсорному экрану на короткое расстояние, а затем поднимает палец, когда тот еще движется. В результате объект будет перемещаться под пальцем пользователя и продолжит движение после того, как пользователь поднимет палец.  
  
 На следующем рисунке показан путь выполнения событий манипуляции и важные сведения о каждом событии.  
  
 ![Последовательность событий манипуляции. ] (../../../../docs/framework/wpf/advanced/media/ndp-manipulationevents.png "NDP_ManipulationEvents")  
События манипуляции  
  
 Последовательность событий на предыдущем рисунке приведена в следующем списке.  
  
1.  <xref:System.Windows.UIElement.ManipulationStarting> Событие происходит, когда пользователь помещает палец для объекта. Помимо прочего, это событие позволяет задать <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> свойства. В последующих событиях позиции манипуляции будет относительно <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>. В событиях, отличных от <xref:System.Windows.UIElement.ManipulationStarting>, это свойство доступно только для чтения, поэтому <xref:System.Windows.UIElement.ManipulationStarting> событие — это единственный случай, когда это свойство можно задать.  
  
2.  <xref:System.Windows.UIElement.ManipulationStarted> Затем возникает событие. Это событие сообщает исходную точку манипуляции.  
  
3.  <xref:System.Windows.UIElement.ManipulationDelta> Событие возникает несколько раз как перемещения пользователя пальца на сенсорном экране. <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> Свойство <xref:System.Windows.Input.ManipulationDeltaEventArgs> класса сообщает ли манипуляции интерпретируется как движение, расширение или преобразование. Здесь вы выполняете большую часть манипуляций с объектом.  
  
4.  <xref:System.Windows.UIElement.ManipulationInertiaStarting> Событие происходит, когда пользователь перестает касаться с объектом. Это событие позволяет указать замедление манипуляции во время инерции. Так объект может имитировать разные физические расстояния или атрибуты при вашем желании. Например, предположим, что в приложении имеются два объекта, представляющие элементы в физическом мире, один из которых тяжелее другого. Можно сделать так, чтобы более тяжелый объект замедлялся быстрее, чем более легкий.  
  
5.  <xref:System.Windows.UIElement.ManipulationDelta> Событие возникает несколько раз, как происходит инерции. Обратите внимание, что это событие возникает, и когда пальцы пользователя двигаются по сенсорному экрану, и когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имитирует инерцию. Другими словами <xref:System.Windows.UIElement.ManipulationDelta> происходит до и после <xref:System.Windows.UIElement.ManipulationInertiaStarting> событий. <xref:System.Windows.Input.ManipulationDeltaEventArgs.IsInertial%2A?displayProperty=nameWithType> Отчетов о свойствах ли <xref:System.Windows.UIElement.ManipulationDelta> событие возникает во время инерции, поэтому вы можете проверять это свойство и выполнять различные действия, в зависимости от его значения.  
  
6.  <xref:System.Windows.UIElement.ManipulationCompleted> Событие возникает при завершении манипуляции и инерции любой. То есть после всех <xref:System.Windows.UIElement.ManipulationDelta> событиями, <xref:System.Windows.UIElement.ManipulationCompleted> сигнал о завершении манипуляции возникает событие.  
  
 <xref:System.Windows.UIElement> Также определяет <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> событий. Это событие возникает, когда <xref:System.Windows.Input.ManipulationDeltaEventArgs.ReportBoundaryFeedback%2A> вызове метода <xref:System.Windows.UIElement.ManipulationDelta> событий. <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> Событий позволяет приложений или компонентов, чтобы визуально достигнув границы объекта. Например <xref:System.Windows.Window> класса дескрипторы <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> событий окно немного перемещение при достижении его границы.  
  
 Манипуляцию можно отменить, вызвав <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> метод в аргументах события, за исключением того, при любой манипуляции <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> событий. При вызове <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A>, события манипуляции более не возникают, и события мыши происходят сенсорного ввода. В следующей таблице описывается связь между моментом отмены манипуляции и событиями мыши, которые происходят.  
  
|Событие, вызываемое отменой|События мыши, возникающие для ввода, который уже произошел|  
|----------------------------------------|-----------------------------------------------------------------|  
|<xref:System.Windows.UIElement.ManipulationStarting> и <xref:System.Windows.UIElement.ManipulationStarted>.|События нажатия кнопки мыши.|  
|<xref:System.Windows.UIElement.ManipulationDelta>|События нажатия кнопки мыши и перемещения мыши.|  
|<xref:System.Windows.UIElement.ManipulationInertiaStarting> и <xref:System.Windows.UIElement.ManipulationCompleted>.|События нажатия кнопки мыши, перемещения мыши и отпускания кнопки мыши.|  
  
 Обратите внимание, что при вызове метода <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> когда обработку инерции, метод возвращает `false` и входные данные не вызывает события мыши.  
  
### <a name="the-relationship-between-touch-and-manipulation-events"></a>Связь между событиями касания и событиями манипуляции  
 Объект <xref:System.Windows.UIElement> всегда может принимать события сенсорного экрана. Когда <xref:System.Windows.UIElement.IsManipulationEnabled%2A> свойству `true`, <xref:System.Windows.UIElement> могут получать события касания и манипуляции.  Если <xref:System.Windows.UIElement.TouchDown> событие не обрабатывается (то есть <xref:System.Windows.RoutedEventArgs.Handled%2A> свойство `false`), логика манипуляции перехватывает касание элемента и создает события манипуляции. Если <xref:System.Windows.RoutedEventArgs.Handled%2A> свойству `true` в <xref:System.Windows.UIElement.TouchDown> событие, логика манипуляции не создает события манипуляции. На следующем рисунке показана связь между событиями касания и событиями манипуляции.  
  
 ![Связь между событиями сенсорного экрана и манипуляции](../../../../docs/framework/wpf/advanced/media/ndp-touchmanipulateevents.png "NDP_TouchManipulateEvents")  
События касания и манипуляции  
  
 Следующий список описывает связь между событиями касания и манипуляции, показанными на предыдущем рисунке.  
  
-   Когда первое сенсорное устройство создает <xref:System.Windows.UIElement.TouchDown> события <xref:System.Windows.UIElement>, логика манипуляции вызывает <xref:System.Windows.UIElement.CaptureTouch%2A> метод, который приводит к возникновению ошибки <xref:System.Windows.UIElement.GotTouchCapture> событий.  
  
-   Когда <xref:System.Windows.UIElement.GotTouchCapture> происходит, логика манипуляции вызывает <xref:System.Windows.Input.Manipulation.AddManipulator%2A?displayProperty=nameWithType> метод, который приводит к возникновению ошибки <xref:System.Windows.UIElement.ManipulationStarting> событий.  
  
-   Когда <xref:System.Windows.UIElement.TouchMove> событиями, логика манипуляции создает <xref:System.Windows.UIElement.ManipulationDelta> события, происходящие до <xref:System.Windows.UIElement.ManipulationInertiaStarting> события.  
  
-   Когда последнее сенсорное устройство элемент вызывает <xref:System.Windows.UIElement.TouchUp> создает логику обработки событий, <xref:System.Windows.UIElement.ManipulationInertiaStarting> событие.  
  
<a name="focus"></a>   
## <a name="focus"></a>Фокус  
 Существует два основных понятия, относящихся к фокусу в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: фокус клавиатуры и логический фокус.  
  
### <a name="keyboard-focus"></a>Фокус клавиатуры  
 Фокус клавиатуры относится к элементу, получающему ввод с клавиатуры.  На всем рабочем столе может быть только один элемент, в котором находится фокус клавиатуры.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], элемент, имеющий фокус будет иметь <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> значение `true`.  Статический <xref:System.Windows.Input.Keyboard> метод <xref:System.Windows.Input.Keyboard.FocusedElement%2A> возвращает элемент, который в данный момент имеет фокус клавиатуры.  
  
 Фокус клавиатуры можно получить, — перехода к элементу или щелкнув мышью определенных элементов, такие как <xref:System.Windows.Controls.TextBox>.  Фокус клавиатуры также могут быть получены программно с помощью <xref:System.Windows.Input.Keyboard.Focus%2A> метод <xref:System.Windows.Input.Keyboard> класса.  <xref:System.Windows.Input.Keyboard.Focus%2A>пытается перевести фокус клавиатуры указанного элемента.  Элемент, возвращаемый <xref:System.Windows.Input.Keyboard.Focus%2A> элемент, который в данный момент имеет фокус клавиатуры.  
  
 Чтобы элемент получает фокус клавиатуры <xref:System.Windows.UIElement.Focusable%2A> свойство и <xref:System.Windows.UIElement.IsVisible%2A> свойства должно быть присвоено **true**.  Некоторые классы, такие как <xref:System.Windows.Controls.Panel>, имеют <xref:System.Windows.UIElement.Focusable%2A> значение `false` по умолчанию; таким образом, может потребоваться присвоить этому свойству значение `true` Если этот элемент, чтобы иметь возможность получать фокус.  
  
 В следующем примере используется <xref:System.Windows.Input.Keyboard.Focus%2A> Чтобы установить фокус на <xref:System.Windows.Controls.Button>.  Рекомендуемым местом для установки начального фокуса в приложении является <xref:System.Windows.FrameworkElement.Loaded> обработчика событий.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Дополнительные сведения о фокусе клавиатуры см. в разделе [Общие сведения о фокусе](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
### <a name="logical-focus"></a>Логический фокус  
 Логический фокус относится к <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> в области фокуса.  В приложении может быть несколько элементов, имеющих логический фокус, но в отдельной области фокуса может быть только один элемент, имеющий логический фокус.  
  
 Областью фокуса является элемент-контейнер, который отслеживает <xref:System.Windows.Input.FocusManager.FocusedElement%2A> в своей области действия.  Когда фокус покидает область фокуса, элемент с фокусом теряет фокус клавиатуры, но сохраняет логический фокус.  При возвращении фокуса в область фокуса элемент с логическим фокусом получит фокус клавиатуры.  Это позволяет переносить фокус клавиатуры между несколькими областями фокуса, но гарантирует, что элемент с фокусом в области фокуса останется элементом с фокусом, когда фокус вернется в эту область.  
  
 Элемент может быть включен в область фокуса в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , установив <xref:System.Windows.Input.FocusManager> вложенное свойство <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> для `true`, или в коде, задав значение вложенного свойства с помощью <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> метод.  
  
 В нижеследующем примере <xref:System.Windows.Controls.StackPanel> область фокуса, задав <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> вложенное свойство.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 Классы в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являющиеся областью фокуса по умолчанию являются <xref:System.Windows.Window>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolBar>, и <xref:System.Windows.Controls.ContextMenu>.  
  
 Элемент, имеющий фокус клавиатуры, также будет иметь логический фокус для области фокуса, которой он принадлежит. Таким образом, при установке фокуса на элемент с <xref:System.Windows.Input.Keyboard.Focus%2A> метод <xref:System.Windows.Input.Keyboard> класса или классов базовых элементов будет предпринята попытка задания фокуса клавиатуры и логический фокус.  
  
 Чтобы определить конкретное элемент в области фокуса, используйте <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>. Чтобы изменить элемент, имеющий фокус для области фокуса, используйте <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>.  
  
 Дополнительные сведения о логическом фокусе см. в разделе [Общие сведения о фокусе](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
<a name="mouse_position"></a>   
## <a name="mouse-position"></a>Положение мыши  
 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] ввода в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет полезные сведения о координатных пространствах.  Например, координата `(0,0)` является верхней левой координатой, но какого элемента в дереве? Элемента, который является целевым объектом ввода? Элемента, к которому присоединен обработчик событий? Или какого-нибудь другого элемента? Чтобы избежать путаницы, [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] ввода в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] требует указания системы координат при работе с координатами, полученными посредством мыши. <xref:System.Windows.Input.Mouse.GetPosition%2A> Метод возвращает координаты указателя мыши относительно заданного элемента.  
  
<a name="mouse_capture"></a>   
## <a name="mouse-capture"></a>Захват мыши  
 Устройства мыши специально поддерживают модальную характеристику, которая называется захватом мыши. Захват мыши используется для поддержания промежуточного состояния ввода при запуске операции перетаскивания, так что другие операции, связанные с номинальным положением указателя мыши на экране указателя мыши, не всегда происходят. Во время перетаскивания пользователь не может щелкнуть мышью без прерывания операции перетаскивания, что делает большинство указаний мыши нецелесообразными, пока захват мыши удерживается источником перетаскивания. Система ввода предоставляет [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], которые могут определить состояние захвата мыши, а также [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], которые могут обеспечить захват мыши в определенном элементе или очистить состояние захвата мыши. Дополнительные сведения об операциях перетаскивания см. в разделе [Общие сведения о перетаскивании](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md).  
  
<a name="commands"></a>   
## <a name="commands"></a>Команды  
 Команды позволяют обрабатывать входные данные на более семантическом уровне по сравнению с устройствами ввода.  Команды — это простые директивы, такие как `Cut`, `Copy`, `Paste` или `Open`.  Команды удобно использовать для централизации командной логики.  Та же команда может осуществляться из <xref:System.Windows.Controls.Menu>на <xref:System.Windows.Controls.ToolBar>, или с помощью сочетания клавиш. Команды также предоставляют механизм для отключения элементов управления, когда команда становится недоступной.  
  
 <xref:System.Windows.Input.RoutedCommand>— [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализация <xref:System.Windows.Input.ICommand>.  Когда <xref:System.Windows.Input.RoutedCommand> выполняется, <xref:System.Windows.Input.CommandManager.PreviewExecuted> и <xref:System.Windows.Input.CommandManager.Executed> событие для целевого объекта команды, какие проходят и поднимаются по дереву элементов, таких как другие входные данные.  Если целевой объект команды не задан, в качестве целевого объекта будет использоваться элемент с фокусом клавиатуры.  Логику, которая выполняет команду присоединяется к <xref:System.Windows.Input.CommandBinding>.  Когда <xref:System.Windows.Input.CommandManager.Executed> событий достигает <xref:System.Windows.Input.CommandBinding> для указанной команды, <xref:System.Windows.Input.ExecutedRoutedEventHandler> на <xref:System.Windows.Input.CommandBinding> вызывается.  Этот обработчик выполняет действие команды.  
  
 Дополнительные сведения о системе команд см. в разделе [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет библиотеку общих команд, которые состоит из <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, и <xref:System.Windows.Documents.EditingCommands>, или определить собственные.  
  
 В следующем примере показано, как настроить <xref:System.Windows.Controls.MenuItem> так, что при его выборе вызывается <xref:System.Windows.Input.ApplicationCommands.Paste%2A> на <xref:System.Windows.Controls.TextBox>, исходя из <xref:System.Windows.Controls.TextBox> фокус клавиатуры.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
 Дополнительные сведения о командах в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="the_input_system_and_base_elements"></a>   
## <a name="the-input-system-and-base-elements"></a>Система ввода и базовые элементы  
 События, например вложенные события, определенные ввода <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, и <xref:System.Windows.Input.Stylus> классы возникает системой ввода и вставить в определенное место в объект модели, основанной на нажатия визуального дерева во время выполнения.  
  
 Каждое из этих событий, <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, и <xref:System.Windows.Input.Stylus> определить как вложенное событие, также переопределяется классами базового элемента <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement> как новое маршрутизируемое событие. Перенаправленные события базовых элементов создаются классами, обрабатывающими исходное присоединенное событие и повторно использующими данные события.  
  
 Когда событие ввода становится связанным с определенным исходным элементом через реализацию события ввода его базового элемента, оно может перенаправляться через оставшуюся часть маршрута события, основанного на комбинации объектов логического и визуального дерева, и обрабатываться кодом приложения.  Как правило, удобнее обрабатывать эти связанные с устройством события ввода с помощью перенаправленных событий в <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement>, поскольку может использовать более понятный синтаксис обработчика событий и в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и в коде. Вместо этого можно обрабатывать присоединенное событие, инициированное процессом, но это сопряжено с некоторыми проблемами: присоединенное событие может быть отмечено как обработанное обработчиком класса базовых элементов класса и придется использовать методы доступа вместо действительного синтаксиса событий, чтобы подключить обработчики для присоединенных событий.  
  
<a name="whats_next"></a>   
## <a name="whats-next"></a>Что дальше?  
 Теперь вам известно несколько методов обработки ввода в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Вы также должны лучше понимать разные типы событий ввода и механизмы перенаправленных событий, используемые в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Доступны дополнительные ресурсы, в которых более подробно разъясняются элементы инфраструктуры [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и маршрутизация событий. Дополнительные сведения см. в следующих обзорах: [Общие сведения о командах](../../../../docs/framework/wpf/advanced/commanding-overview.md), [Общие сведения о фокусе](../../../../docs/framework/wpf/advanced/focus-overview.md), [Общие сведения о базовых элементах](../../../../docs/framework/wpf/advanced/base-elements-overview.md), [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md) и [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о фокусе](../../../../docs/framework/wpf/advanced/focus-overview.md)  
 [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Общие сведения о базовых элементах](../../../../docs/framework/wpf/advanced/base-elements-overview.md)  
 [Свойства](../../../../docs/framework/wpf/advanced/properties-wpf.md)
