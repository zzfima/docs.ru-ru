---
title: "Общие сведения о входных данных | Microsoft Docs"
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
  - "команды [WPF]"
  - "Ввод [WPF], общие сведения"
  - "фокус клавиатуры [WPF]"
  - "ввод с клавиатуры [WPF]"
  - "события касания [WPF]"
  - "маршрутизация событий [WPF]"
  - "сенсорный ввод [WPF]"
  - "обработка [WPF]"
  - "логический фокус [WPF]"
  - "ввод с пера [WPF]"
  - "ввод текста [WPF]"
  - "события ввода [WPF] обработка"
  - "Обзор ввода WPF"
  - "события обработки [WPF]"
  - "ввод с помощью мыши [WPF]"
  - "захват мыши [WPF]"
  - "фокус [WPF]"
  - "положение мыши [WPF]"
ms.assetid: ee5258b7-6567-415a-9b1c-c0cbe46e79ef
caps.latest.revision: 50
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 50
---
# Общие сведения о входных данных
<a name="introduction"></a>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Подсистема предоставляет мощный [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] для получения входных данных от разнообразных устройств, включая мышь, клавиатура, прикосновения и пера. В этом разделе описываются службы, предоставляемые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и объясняется архитектура систем ввода.  
  
  
<a name="input_api"></a>   
## <a name="input-api"></a>Входные данные API  
 Основной поток данных [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] основано на базовых классах элемента: <xref:System.Windows.UIElement>, <xref:System.Windows.ContentElement>, <xref:System.Windows.FrameworkElement>, и <xref:System.Windows.FrameworkContentElement>.  Дополнительные сведения о базовых элементах см. в разделе [Обзор базовых элементов](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  Эти классы предоставляют функциональные возможности для входных событий, связанных с нажатий клавиш, кнопок мыши, колеса мыши, движением мыши, управление фокусом и захватом мыши. Поместив входные данные [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] на базовых элементах вместо обработки всех событий ввода в качестве службы, архитектура ввода позволяет события ввода порождать определенного объекта в пользовательском Интерфейсе, которые поддерживают схему маршрутизации событий, при которой более одного элемента имеет возможность обработать событие ввода. Многие события ввода имеют пары событий, связанных с ними.  Например, событие Нажатие клавиши связан с <xref:System.Windows.Input.Keyboard.KeyDown> и <xref:System.Windows.Input.Keyboard.PreviewKeyDown> события.  Разница в этих событиях заключается в того, как они перенаправляются на целевой элемент.  События предварительного просмотра проходят вниз по дереву элементов от корневого элемента в целевой элемент.  События восходящей маршрутизации восходящей от целевого элемента до корневого элемента.  Маршрутизация событий в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] рассматривается более подробно далее в этом обзоре и в [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
### <a name="keyboard-and-mouse-classes"></a>Классы клавиатуры и мыши  
 Кроме ввода [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] на базовых классах элемента, <xref:System.Windows.Input.Keyboard> класса и <xref:System.Windows.Input.Mouse> классы предоставляют дополнительные [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] для работы с клавиатуры и мыши.  
  
 Примерами входных [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] на <xref:System.Windows.Input.Keyboard> класса <xref:System.Windows.Input.Keyboard.Modifiers%2A> свойство, которое возвращает <xref:System.Windows.Input.ModifierKeys> в настоящее время нажаты и <xref:System.Windows.Input.Keyboard.IsKeyDown%2A> метод, который определяет, является ли указанная клавиша нажата.  
  
 В следующем примере используется <xref:System.Windows.Input.Keyboard.GetKeyStates%2A> метод для определения <xref:System.Windows.Input.Key> находится в состоянии down.  
  
 [!code-csharp[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyArgsSnippetSample/CSharp/Window1.xaml.cs#keyeventargskeyboardgetkeystates)]
 [!code-vb[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyArgsSnippetSample/visualbasic/window1.xaml.vb#keyeventargskeyboardgetkeystates)]  
  
 Примерами входных [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] на <xref:System.Windows.Input.Mouse> класса <xref:System.Windows.Input.Mouse.MiddleButton%2A>, который получает состояние средней кнопки мыши, и <xref:System.Windows.Input.Mouse.DirectlyOver%2A>, который возвращает элемент указатель мыши наведен.  
  
 В следующем примере определяется ли <xref:System.Windows.Input.Mouse.LeftButton%2A> мыши находится в <xref:System.Windows.Input.MouseButtonState> состояния.  
  
 [!code-csharp[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MouseRelatedSnippets/CSharp/Window1.xaml.cs#mouserelatedsnippetsgetleftbuttonmouse)]
 [!code-vb[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MouseRelatedSnippets/visualbasic/window1.xaml.vb#mouserelatedsnippetsgetleftbuttonmouse)]  
  
 <xref:System.Windows.Input.Mouse> и <xref:System.Windows.Input.Keyboard> классы рассматриваются более подробно в этом обзоре.  
  
### <a name="stylus-input"></a>Ввод с пера  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]имеет встроенную поддержку <xref:System.Windows.Input.Stylus>.  <xref:System.Windows.Input.Stylus> — рукописный ввод, ставший популярным благодаря устройствам [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)].  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]приложения могут обрабатывать перо как мышь с помощью мыши [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], но [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также предоставляет перо как абстрактное устройство, используйте модели, похожей на клавиатуру и мышь.  Все связанные с пером [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] содержат слово «Перо».  
  
 Поскольку перо может вести себя как мышь, приложения, поддерживающие только ввод от мыши можно по-прежнему получить определенный уровень поддержки пера автоматически. При использовании пера таким образом, приложению дается возможность обработать соответствующее событие пера и обрабатывает соответствующее событие мыши. Кроме того службы более высокого уровня, например рукописного ввода также доступны через абстрактное устройство пера.  Дополнительные сведения о рукописных данных в качестве входного см. в разделе [Приступая к работе с рукописным вводом](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).  
  
<a name="event_routing"></a>   
## <a name="event-routing"></a>Маршрутизация событий  
 Объект <xref:System.Windows.FrameworkElement> может содержать другие элементы в качестве дочерних элементов в своей модели содержимого, формируя тем самым дерево элементов.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], родительский элемент может участвовать в вводе, ориентированном на дочерние элементы или других потомков, обрабатывая события. Это особенно полезно для построения элементов управления из меньших элементов управления, этот процесс называется «композиции элемента управления» или «совмещение». Дополнительные сведения о деревьях элемента и как деревья элемента связаны с маршрутами события см. в разделе [деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
 Маршрутизация событий — это процесс пересылки событий нескольким элементам, так, что определенный объект или элемент на маршруте можно предоставлять значимый ответ (с помощью обработки) для события, которое может порождаться другим элементом.  Перенаправленные события используют один из трех механизмов маршрутизации: прямая, восходящая и нисходящая.  При прямой маршрутизации исходный элемент является единственным элементом, уведомление и событие не маршрутизируется с любыми другими элементами. Тем не менее, событие с прямой маршрутизацией тем не менее предоставляет некоторые дополнительные возможности, доступные только для перенаправленных событий, в отличие от стандартных [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] события. Маршрутизация по восходящей обрабатывает дерево элементов уведомляя первый элемент, являющийся источником события, затем родительского элемента и т. д.  Нисходящая маршрутизация начинается в корне дерева элемента и спускается вниз, заканчивая исходным элементом источника.  Дополнительные сведения о маршрутизируемых событиях см. в разделе [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]события ввода обычно представлены парами, состоящими из событий нисходящей и восходящей маршрутизации событий.  События нисходящей маршрутизации отличаются от событий восходящей маршрутизации префиксом «Preview».  Например <xref:System.Windows.Input.Mouse.PreviewMouseMove> является нисходящей версией события перемещения мыши и <xref:System.Windows.Input.Mouse.MouseMove> — восходящей версией этого события. Пары событий являются соглашением, реализованным на уровне элемента и не являются неотъемлемой характеристикой [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] событий системы. Дополнительные сведения см. в разделе событий ввода WPF в [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
<a name="handling_input_events"></a>   
## <a name="handling-input-events"></a>Обработка событий ввода  
 Для получения входных данных для элемента, обработчик событий должен быть связан с данным конкретным событием.  В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] это осуществляется напрямую: необходимо сослаться на имя события как атрибут элемента, который будет ожидать это событие.  Задайте значение атрибута имени обработчика событий, который можно определить на основе делегата.  Обработчик событий должен быть написан в коде, таких как [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] и может быть включено в файл кода.  
  
 События клавиатуры возникают, когда операционная система сообщает ключевые действия, которые могут возникнуть при фокус находится на элементе. События мыши и пера каждого делятся на две категории: события, отчет изменениях положения указателя относительно элемента и событий, сообщающих состояния кнопок устройства.  
  
### <a name="keyboard-input-event-example"></a>Пример события ввода клавиатуры  
 Следующий пример осуществляет прослушивание клавиши со стрелкой влево.  Объект <xref:System.Windows.Controls.StackPanel> создается, имеет <xref:System.Windows.Controls.Button>.  Обработчик событий для ожидания нажатия клавиши со стрелкой влево присоединяется к <xref:System.Windows.Controls.Button> экземпляра.  
  
 Первый раздел примера создает <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.Button> и присоединяет обработчик событий для <xref:System.Windows.UIElement.KeyDown>.  
  
 [!code-xml[InputOvw#Input_OvwKeyboardExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwkeyboardexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexampleuicodebehind)]  
  
 Второй раздел прописывается в коде и определяет обработчик событий.  При нажатии клавиши со стрелкой влево и <xref:System.Windows.Controls.Button> установлен фокус клавиатуры, программа запускает обработчик и <xref:System.Windows.Controls.Control.Background%2A> цвет <xref:System.Windows.Controls.Button> изменяется.  При нажатии клавиши, но не клавишу Стрелка влево <xref:System.Windows.Controls.Control.Background%2A> цвет <xref:System.Windows.Controls.Button> изменяется обратно на первоначальный.  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexamplehandlercodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexamplehandlercodebehind)]  
  
### <a name="mouse-input-event-example"></a>Пример события ввода мыши  
 В следующем примере <xref:System.Windows.Controls.Control.Background%2A> цвет <xref:System.Windows.Controls.Button> меняется, когда указатель мыши оказывается <xref:System.Windows.Controls.Button>.  <xref:System.Windows.Controls.Control.Background%2A> цвет восстанавливается в том случае, когда указатель мыши покидает <xref:System.Windows.Controls.Button>.  
  
 Первый раздел примера создает <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.Button> управления и присоединяет обработчики событий для <xref:System.Windows.UIElement.MouseEnter> и <xref:System.Windows.UIElement.MouseLeave> событий <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[InputOvw#Input_OvwMouseExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwmouseexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleuicodebehind)]  
  
 Второй раздел примера прописывается в коде и определяет обработчики событий.  Когда указатель мыши перемещается <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Control.Background%2A> цвет <xref:System.Windows.Controls.Button> изменяется на <xref:System.Windows.Media.Brushes.SlateGray%2A>.  Когда указатель мыши покидает <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Control.Background%2A> цвет <xref:System.Windows.Controls.Button> изменяется обратно на <xref:System.Windows.Media.Brushes.AliceBlue%2A>.  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleeneterhandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleeneterhandler)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleleavehandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleleavehandler)]  
  
<a name="text_input"></a>   
## <a name="text-input"></a>Текстовый ввод  
 <xref:System.Windows.ContentElement.TextInput> событий позволяет ожидать ввода текста в аппаратно независимым образом. Клавиатура является основным средством для рукописного ввода, но речь, текст и другие устройства ввода можно создать также ввод текста.  
  
 Для ввода с клавиатуры [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сначала вызывает соответствующие <xref:System.Windows.ContentElement.KeyDown>/<xref:System.Windows.ContentElement.KeyUp> события. Если эти события не обрабатываются, и клавиша является текстовой вместо (ключ управления например клавишей со стрелкой) или функциональные клавиши, а затем <xref:System.Windows.ContentElement.TextInput> события.  Не всегда существует простое однозначное сопоставление между <xref:System.Windows.ContentElement.KeyDown>/<xref:System.Windows.ContentElement.KeyUp> и <xref:System.Windows.ContentElement.TextInput> событий из-за нажатия нескольких клавиш может создавать один знак ввода текста и одного нажатия клавиш можно создавать нескольких символов строки.  Это особенно верно для языков, таких как китайский, японский и корейский, которые используют [!INCLUDE[TLA#tla_ime#plural](../../../../includes/tlasharptla-imesharpplural-md.md)] для формирования тысячи возможных символов в соответствующем алфавите.  
  
 При [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отправляет <xref:System.Windows.ContentElement.KeyUp>/<xref:System.Windows.ContentElement.KeyDown> событий, <xref:System.Windows.Input.KeyEventArgs.Key%2A> равен <xref:System.Windows.Input.Key?displayProperty=fullName> если нажатие клавиш может стать частью <xref:System.Windows.ContentElement.TextInput> событий (если ALT + S, например). Это позволяет коду в <xref:System.Windows.ContentElement.KeyDown> обработчик событий для проверки <xref:System.Windows.Input.Key?displayProperty=fullName> и, если он найден, оставьте обработки обработчику сгенерированного впоследствии <xref:System.Windows.ContentElement.TextInput> события. В этих случаях различные свойства <xref:System.Windows.Input.TextCompositionEventArgs> аргумент может использоваться для определения первоначальных нажатий клавиш. Аналогично Если [!INCLUDE[TLA2#tla_ime](../../../../includes/tla2sharptla-ime-md.md)] активен, <xref:System.Windows.Input.Key> имеет значение <xref:System.Windows.Input.Key?displayProperty=fullName>, и <xref:System.Windows.Input.KeyEventArgs.ImeProcessedKey%2A> дает первоначальное нажатие клавиши или клавиш.  
  
 В следующем примере определяется обработчик для <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событие и обработчик для <xref:System.Windows.UIElement.KeyDown> события.  
  
 Первый сегмент кода или разметки создает интерфейс пользователя.  
  
 [!code-xml[InputOvw#Input_OvwTextInputXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwtextinputxaml)]  
  
 [!code-csharp[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputuicodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputuicodebehind)]  
  
 Второй сегмент кода содержит обработчики событий.  
  
 [!code-csharp[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputhandlerscodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputhandlerscodebehind)]  
  
 Поскольку входные события восходящей маршрутизации событий, <xref:System.Windows.Controls.StackPanel> получает входные данные независимо от того, какой элемент имеет фокус клавиатуры. <xref:System.Windows.Controls.TextBox> сначала уведомляется элемент управления и `OnTextInputKeyDown` обработчик вызывается, только если <xref:System.Windows.Controls.TextBox> не обработал входные данные. Если <xref:System.Windows.UIElement.PreviewKeyDown> событий используется вместо <xref:System.Windows.UIElement.KeyDown> событий, `OnTextInputKeyDown` сначала вызывается обработчик.  
  
 В этом примере логика обработки записывается два раза — один раз для CTRL + O, а еще раз для кнопки событие нажатия. Это можно упростить, используя команды вместо обработки событий ввода напрямую.  Команды описаны в этом обзоре и в [Общие сведения о командах](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="touch_and_manipulation"></a>   
## <a name="touch-and-manipulation"></a>Сенсорный ввод и манипуляции  
 Новое оборудование и API в операционной системе Windows 7 позволяют приложениям одновременно получать входные данные из нескольких штрихов. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]позволяет приложениям обнаруживать и реагировать на касание так же, как отвечать на другие входные данные, такие как действия мыши и клавиатуры, путем генерирования событий при возникновении touch.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет два типа событий при возникновении touch: прикосновение и манипуляция. События прикосновения предоставляют необработанные данные о каждой пальцем на сенсорном экране и перемещения. События манипуляции интерпретируют входные данные в них определенные действия. В этом разделе рассматриваются оба типа событий.  
  
### <a name="prerequisites"></a>Предварительные требования  
 Вам необходимы следующие компоненты для разработки приложений, реагирующая на касание.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7.  
  
-   Устройства, например сенсорный экран, который поддерживает Windows Touch.  
  
### <a name="terminology"></a>Терминология  
 Следующие термины используются сенсорного экрана.  
  
-   **Touch** является типом ввода пользователя, распознаваемых системой Windows 7. Обычно это событие инициируется когда пользователь прикасается пальцами сенсорного экрана. Обратите внимание, устройств, таких как сенсорной панели, который чаще всего на переносных компьютерах не поддерживают касания, если устройство просто преобразует палец позиции и движении как ввод от мыши.  
  
-   **Мультисенсорный** — это прикосновение из более чем одной точки одновременно. Windows 7 и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддержкой мультисенсорных функций. Каждый раз, когда touch описана в документации по [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], также относятся к мультисенсорных функций.  
  
-   Объект **управления** возникает, когда касание интерпретируется как физическое действие, которое применяется к объекту. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], события манипуляции интерпретируют ввод как трансляции, расширения или поворота манипуляции.  
  
-   Объект `touch device` представляет устройство для сенсорного ввода, например одним пальцем на сенсорном экране.  
  
### <a name="controls-that-respond-to-touch"></a>Элементы управления, реагирующие на касания  
 Следующие элементы управления можно прокручивать, перетащив палец через элемент управления, если у него есть содержимое, которое находится вне области просмотра.  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.DataGrid>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.TextBox>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
 <xref:System.Windows.Controls.ScrollViewer> определяет <xref:System.Windows.Controls.ScrollViewer.PanningMode%2A?displayProperty=fullName> вложенное свойство, которое позволяет указать панорамирования touch включении по горизонтали, по вертикали, оба или ни одно. <xref:System.Windows.Controls.ScrollViewer.PanningDeceleration%2A?displayProperty=fullName> свойство определяет, насколько быстро замедляется прокрутка, когда пользователь поднимает палец с сенсорного экрана. <xref:System.Windows.Controls.ScrollViewer.PanningRatio%2A?displayProperty=fullName> вложенное свойство задает отношение смещения прокрутки к смещению обработки преобразования.  
  
### <a name="touch-events"></a>События касания  
 Базовые классы, <xref:System.Windows.UIElement>, <xref:System.Windows.UIElement3D>, и <xref:System.Windows.ContentElement>, определяют события, которые можно подписаться, приложение будет реагировать на touch. События касания полезны в тех случаях, когда приложение интерпретирует прикосновений помимо манипуляций с объектами. Например приложение, позволяющее пользователю рисовать на один или более пальцев будет подписаться на события касания.  
  
 Все три класса определены следующие события, которые ведут себя похожим образом независимо от того, определяющего класса.  
  
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
  
 Как события клавиатуры и мыши события сенсорного экрана являются маршрутизированные события. События, которые начинаются с `Preview` туннелирование события и события, которые начинаются с `Touch` восходящей маршрутизации событий. Дополнительные сведения о маршрутизируемых событиях см. в разделе [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md). При обработке этих событий, позицию ввода, относительно любого элемента можно получить, вызвав <xref:System.Windows.Input.TouchEventArgs.GetTouchPoint%2A> или <xref:System.Windows.Input.TouchEventArgs.GetIntermediateTouchPoints%2A> метод.  
  
 Чтобы лучше понять взаимодействие между события сенсорного экрана, рассмотрим ситуацию, где пользователь помещает элемент одним пальцем, передвигает палец в элементе и убирает палец из элемента. На следующем рисунке выполнения восходящей маршрутизации событий (события нисходящей маршрутизации указаны для наглядности).  
  
 ![Последовательность событий сенсорного экрана.](../../../../docs/framework/wpf/advanced/media/ndp-touchevents.png "NDP_TouchEvents")  
События касания  
  
 Следующий список описывает последовательность событий на предыдущем рисунке.  
  
1.  <xref:System.Windows.UIElement.TouchEnter> событие происходит один раз, когда пользователь прикасается элемента.  
  
2.  <xref:System.Windows.UIElement.TouchDown> событие происходит один раз.  
  
3.  <xref:System.Windows.UIElement.TouchMove> событие возникает несколько раз, когда пользователь перемещает палец в пределах элемента.  
  
4.  <xref:System.Windows.UIElement.TouchUp> событие происходит один раз, когда пользователь поднимает палец от элемента.  
  
5.  <xref:System.Windows.UIElement.TouchLeave> событие происходит один раз.  
  
 При использовании более чем двумя пальцами, события возникают для каждого пальца.  
  
### <a name="manipulation-events"></a>События манипуляции  
 Для случаев, когда приложение позволяет манипулировать объектом <xref:System.Windows.UIElement> класс определяет события манипуляции. В отличие от событий сенсорного ввода, указывающих только позицию точки касания события манипуляции отчетов интерпретации входных данных. Существует три типа манипуляции, преобразования, расширения и поворота. Ниже перечислены способы вызова трех типов манипуляций.  
  
-   Поместите палец на объект и переместить пальцем по сенсорному экрану для вызова манипуляции. Обычно это перемещение объекта.  
  
-   Поместите два пальца на объект и Сведите ближе к другу или дальше друг от друга, чтобы выполнить манипуляцию расширения. Это действие обычно изменяет размер объекта.  
  
-   Поместите два пальца на объект и Поворачивайте пальцы друг от друга, чтобы выполнить манипуляцию поворота вокруг. Это действие обычно Поворачивает объект.  
  
 Несколько типов манипуляций можно выполнять одновременно.  
  
 Реализовав реагирование объектов на манипуляцию может иметь объект инерции нет. Это может сделать имитировать реальные объекты. Например при отправке книги по столу силой достаточно книги будет продолжать перемещения после выпуска. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]позволяет имитировать это поведение, генерируя события манипуляции после пальцы пользователя освобождает объект.  
  
 Сведения о том, как создать приложение, которое дает пользователю возможность перемещать, масштабировать и поворачивать объект в разделе [Пошаговое руководство: создание первого касания приложения](../../../../docs/framework/wpf/advanced/walkthrough-creating-your-first-touch-application.md).  
  
 <xref:System.Windows.UIElement> определяет следующие события манипуляции.  
  
-   <xref:System.Windows.UIElement.ManipulationStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationStarted>  
  
-   <xref:System.Windows.UIElement.ManipulationDelta>  
  
-   <xref:System.Windows.UIElement.ManipulationInertiaStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationCompleted>  
  
-   <xref:System.Windows.UIElement.ManipulationBoundaryFeedback>  
  
 По умолчанию <xref:System.Windows.UIElement> не получит эти события манипуляции. Для получения события манипуляции на <xref:System.Windows.UIElement>, задайте <xref:System.Windows.UIElement.IsManipulationEnabled%2A?displayProperty=fullName> в `true`.  
  
#### <a name="the-execution-path-of-manipulation-events"></a>Путь выполнения событий манипуляции  
 Рассмотрим ситуацию, когда пользователь «создается» объект. Пользователь прикасается объекта, перемещает пальцем по сенсорному экрану коротких расстояний и затем убирает палец при перемещении. Таким образом, чтобы объект будет переместить в палец пользователя и продолжает движение после пользователь поднимает палец.  
  
 Ниже показан путь выполнения событий манипуляции и важные сведения о каждом событии.  
  
 ![Последовательность событий манипуляции.](../../../../docs/framework/wpf/advanced/media/ndp-manipulationevents.png "NDP_ManipulationEvents")  
События манипуляции  
  
 Следующий список описывает последовательность событий на предыдущем рисунке.  
  
1.  <xref:System.Windows.UIElement.ManipulationStarting> событие происходит, когда пользователь прикасается объекта. Помимо прочего, это событие позволяет задать <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> свойство. В последующих событиях позиция манипуляций будет относительно <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>. В событиях, отличных от <xref:System.Windows.UIElement.ManipulationStarting>, это свойство доступно только для чтения, поэтому <xref:System.Windows.UIElement.ManipulationStarting> событие является только время, это свойство можно задать.  
  
2.  <xref:System.Windows.UIElement.ManipulationStarted> затем возникает событие. Это событие сообщает исходная точка манипуляции.  
  
3.  <xref:System.Windows.UIElement.ManipulationDelta> событие возникает несколько раз, как пальцы пользователя двигаются на сенсорном экране. <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> свойство <xref:System.Windows.Input.ManipulationDeltaEventArgs> класса сообщает ли манипуляции интерпретируется как движение, расширение или преобразование. Это большая часть работы по манипуляций с объектами.  
  
4.  <xref:System.Windows.UIElement.ManipulationInertiaStarting> событие возникает, когда пальцы пользователя разрыва связи с объектом. Это событие позволяет указать замедление манипуляции во время инерции. Это позволяет имитировать различные физические пробелов и атрибутов при выборе. Например, предположим, что приложение имеет двух объектов, представляющих элементы в реальном мире, а второй — тяжелее другого. Можно сделать более сложной объект быстрее, чем легкий замедлением.  
  
5.  <xref:System.Windows.UIElement.ManipulationDelta> событие возникает несколько раз, как происходит инерции. Обратите внимание, что это событие возникает, когда пальцы пользователя двигаются по сенсорному экрану и когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имитирует инерции. Другими словами <xref:System.Windows.UIElement.ManipulationDelta> происходит до и после <xref:System.Windows.UIElement.ManipulationInertiaStarting> событий. <xref:System.Windows.Input.ManipulationDeltaEventArgs.IsInertial%2A?displayProperty=fullName> отчетов о свойствах ли <xref:System.Windows.UIElement.ManipulationDelta> событие возникает при движении по инерции, чтобы можно было проверять это свойство и выполнять различные действия в зависимости от его значения.  
  
6.  <xref:System.Windows.UIElement.ManipulationCompleted> событие возникает при завершении манипуляции и инерции, все. То есть после всех <xref:System.Windows.UIElement.ManipulationDelta> событиями, <xref:System.Windows.UIElement.ManipulationCompleted> событие для оповещения о завершении манипуляции.  
  
 <xref:System.Windows.UIElement> также определяет <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> событий. Это событие возникает, когда <xref:System.Windows.Input.ManipulationDeltaEventArgs.ReportBoundaryFeedback%2A> метод вызывается в <xref:System.Windows.UIElement.ManipulationDelta> событий. <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> событие позволяет приложений или компонентов для обеспечения визуальной обратной связи, когда объект достигает границы. Например <xref:System.Windows.Window> класса дескрипторов <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> событий окно немного сдвигая при достижении его границы.  
  
 Манипуляцию можно отменить, вызвав <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> метод в аргументах события при любой манипуляции за исключением <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> событий. При вызове <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A>, события манипуляции более не возникают, и события мыши происходят для сенсорного ввода. В следующей таблице описаны отношения между моментом отмены манипуляции и возникающих событий мыши.  
  
|Событие, которое вызывается "Отмена"|События мыши, возникающие для ввода, который уже произошел|  
|----------------------------------------|-----------------------------------------------------------------|  
|<xref:System.Windows.UIElement.ManipulationStarting> и <xref:System.Windows.UIElement.ManipulationStarted>|События нажатия кнопки мыши.|  
|<xref:System.Windows.UIElement.ManipulationDelta>|Указатель мыши вниз и перемещения мыши.|  
|<xref:System.Windows.UIElement.ManipulationInertiaStarting> и <xref:System.Windows.UIElement.ManipulationCompleted>|Нажатия кнопки мыши, перемещение мыши и отпускания события.|  
  
 Обратите внимание, что при вызове метода <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> во время манипуляции по инерции, метод возвращает `false` и входные данные не вызывает события мыши.  
  
### <a name="the-relationship-between-touch-and-manipulation-events"></a>Связь между сенсорного экрана и событиями манипуляции  
 Объект <xref:System.Windows.UIElement> всегда может принимать события сенсорного экрана. Когда <xref:System.Windows.UIElement.IsManipulationEnabled%2A> свойству `true`, <xref:System.Windows.UIElement> может получать события сенсорный ввод и манипуляции.  Если <xref:System.Windows.UIElement.TouchDown> событие не обрабатывается (то есть, <xref:System.Windows.RoutedEventArgs.Handled%2A> свойство `false`), логика манипуляции перехватывает касание элемента и создает события манипуляции. Если <xref:System.Windows.RoutedEventArgs.Handled%2A> свойству `true` в <xref:System.Windows.UIElement.TouchDown> событие, логика манипуляции не создает события манипуляции. Ниже показана связь между событиями сенсорного экрана и событиями манипуляции.  
  
 ![Связь между событиями сенсорного экрана и манипуляции](../../../../docs/framework/wpf/advanced/media/ndp-touchmanipulateevents.png "NDP_TouchManipulateEvents")  
Сенсорный ввод и манипуляции события  
  
 Следующий список описывает связь между событиями сенсорного экрана и манипуляции, показанными на предыдущем рисунке.  
  
-   Когда первое сенсорное устройство создает <xref:System.Windows.UIElement.TouchDown> события <xref:System.Windows.UIElement>, логика манипуляции вызывает <xref:System.Windows.UIElement.CaptureTouch%2A> метод, который создает <xref:System.Windows.UIElement.GotTouchCapture> событий.  
  
-   Когда <xref:System.Windows.UIElement.GotTouchCapture> происходит, логика манипуляции вызывает <xref:System.Windows.Input.Manipulation.AddManipulator%2A?displayProperty=fullName> метод, который создает <xref:System.Windows.UIElement.ManipulationStarting> событий.  
  
-   Когда <xref:System.Windows.UIElement.TouchMove> событиями, логика манипуляции создает <xref:System.Windows.UIElement.ManipulationDelta> события, происходящие до <xref:System.Windows.UIElement.ManipulationInertiaStarting> событий.  
  
-   Когда последнее сенсорное устройство элемент вызывает <xref:System.Windows.UIElement.TouchUp> событий, логика манипуляции создает <xref:System.Windows.UIElement.ManipulationInertiaStarting> событий.  
  
<a name="focus"></a>   
## <a name="focus"></a>Фокус  
 Существует два основных понятия фокуса [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: фокус клавиатуры и логический фокус.  
  
### <a name="keyboard-focus"></a>Фокус клавиатуры  
 Фокус ввода ссылается на элемент, получающий ввод с клавиатуры.  Может существовать только один элемент на всем рабочем столе установлен фокус клавиатуры.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], будет иметь элемент, имеющий фокус клавиатуры <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> значение `true`.  Статический <xref:System.Windows.Input.Keyboard> метод <xref:System.Windows.Input.Keyboard.FocusedElement%2A> возвращает элемент, который в данный момент имеет фокус.  
  
 Можно получить фокус клавиатуры — перехода к элементу или щелчка мышью определенных элементов, таких как <xref:System.Windows.Controls.TextBox>.  Фокус клавиатуры также можно получить программным путем с помощью <xref:System.Windows.Input.Keyboard.Focus%2A> метод <xref:System.Windows.Input.Keyboard> класса.  <xref:System.Windows.Input.Keyboard.Focus%2A> пытается предоставить указанный элемент фокус ввода с клавиатуры.  Элемент, возвращаемый <xref:System.Windows.Input.Keyboard.Focus%2A> является элементом, который в данный момент имеет фокус.  
  
 Чтобы получить фокус элемент <xref:System.Windows.UIElement.Focusable%2A> свойство и <xref:System.Windows.UIElement.IsVisible%2A> свойства должно быть присвоено **true**.  Некоторые классы, такие как <xref:System.Windows.Controls.Panel>, имеют <xref:System.Windows.UIElement.Focusable%2A> значение `false` по умолчанию; таким образом, может потребоваться присвоить этому свойству значение `true` , если этот элемент, чтобы иметь возможность получать фокус.  
  
 В следующем примере используется <xref:System.Windows.Input.Keyboard.Focus%2A> Чтобы установить фокус на <xref:System.Windows.Controls.Button>.  Рекомендуемым местом для установки начального фокуса в приложении является <xref:System.Windows.FrameworkElement.Loaded> обработчика событий.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Дополнительные сведения о фокусе клавиатуры в разделе [фокус Обзор](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
### <a name="logical-focus"></a>Логический фокус  
 Логический фокус относится к <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=fullName> в области фокуса.  Может существовать несколько элементов, имеющих логический фокус в приложении, но может быть только один элемент, который имеет логический фокус в отдельной области фокуса.  
  
 Областью фокуса является элемент-контейнер, который отслеживает <xref:System.Windows.Input.FocusManager.FocusedElement%2A> в своей области действия.  Когда фокус покидает область фокуса, элемент с фокусом теряет фокус клавиатуры, но сохраняет логический фокус.  При возвращении фокуса к области фокуса элемент с фокусом получит фокус клавиатуры.  Это позволяет фокус клавиатуры между несколькими областями фокуса, но гарантирует, что элемент с фокусом в области фокуса остается элемент с фокусом, когда фокус возвращается.  
  
 Элемент может быть включен в область фокуса в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , установив <xref:System.Windows.Input.FocusManager> вложенное свойство <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> для `true`, или в коде, посредством задания вложенного свойства с помощью <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> метод.  
  
 В следующем примере <xref:System.Windows.Controls.StackPanel> в области фокуса путем установки <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> вложенного свойства.  
  
 [!code-xml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 Классы в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , являющиеся областью фокуса по умолчанию <xref:System.Windows.Window>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolBar>, и <xref:System.Windows.Controls.ContextMenu>.  
  
 Элемент, имеющий фокус клавиатуры, также будет иметь логический фокус для области фокуса, которой он принадлежит. Таким образом, при установке фокуса на элемент с <xref:System.Windows.Input.Keyboard.Focus%2A> метод <xref:System.Windows.Input.Keyboard> класса или классов базовых элементов будет предпринята попытка задания фокуса клавиатуры и логический фокус.  
  
 Чтобы определить конкретное элемент в области фокуса, используйте <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>. Чтобы изменить элемент фокусом для области фокуса, используйте <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>.  
  
 Дополнительные сведения о логическом фокусе см. в разделе [фокус Обзор](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
<a name="mouse_position"></a>   
## <a name="mouse-position"></a>Положение мыши  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ввода [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] предоставляет полезные сведения относительно координатного пространства.  Например, координировать `(0,0)` координаты левого верхнего, но в левом верхнем углу для какого элемента в дереве? Элемент, который является целью ввода? Элемент, к которому присоединяется обработчик событий для? Или что-то еще? Чтобы избежать путаницы, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ввода [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] требует указания системы координат при работе с координатами, полученными посредством мыши. <xref:System.Windows.Input.Mouse.GetPosition%2A> метод возвращает координаты указателя мыши относительно заданного элемента.  
  
<a name="mouse_capture"></a>   
## <a name="mouse-capture"></a>Захват мыши  
 Специально мыши удерживайте модальную характеристику, называющуюся захватом мыши. Захват мыши используется для поддержания промежуточного состояния ввода при запуске операции и перетащите, чтобы других операций, касающихся номинального экранную позицию указателя мыши не происходят обязательно. Во время перетаскивания пользователь не может щелкнуть без прерывания и перетаскивания, что делает большинство подсказки mouseover нежелательного пока захват мыши удерживается исходным перетаскиванием. Система ввода предоставляет [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] , можно определить состояние захвата мыши, а также [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] , захвата мыши на определенный элемент или очистить состояние захвата мыши. Дополнительные сведения об операциях и перетащите в разделе [Drop Обзор и перетащите](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md).  
  
<a name="commands"></a>   
## <a name="commands"></a>Команды  
 Команды допускают обработку ввода на более семантическом уровне по сравнению с устройствами ввода.  Команды являются простыми директивы, такие как `Cut`, `Copy`, `Paste`, или `Open`.  Команды полезны для централизации командной логики.  Та же команда может осуществляться из <xref:System.Windows.Controls.Menu>на <xref:System.Windows.Controls.ToolBar>, или с помощью сочетания клавиш. Команды также предоставляет механизм для отключения элементов управления, когда команда становится недоступной.  
  
 <xref:System.Windows.Input.RoutedCommand> — [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализацию <xref:System.Windows.Input.ICommand>.  Когда <xref:System.Windows.Input.RoutedCommand> выполняется, <xref:System.Windows.Input.CommandManager.PreviewExecuted> и <xref:System.Windows.Input.CommandManager.Executed> событие для целевого объекта команды, которые проходят и поднимаются по дереву элементов подобно другому вводу.  Если цель команды не задано, элемент с фокусом клавиатуры будет целевой объект команды.  Логика, выполняющая команду, присоединяется к <xref:System.Windows.Input.CommandBinding>.  Когда <xref:System.Windows.Input.CommandManager.Executed> событие достигает <xref:System.Windows.Input.CommandBinding> для указанной команды, <xref:System.Windows.Input.ExecutedRoutedEventHandler> на <xref:System.Windows.Input.CommandBinding> вызывается.  Этот обработчик выполняет действие команды.  
  
 Дополнительные сведения о командах см. в разделе [Общие сведения о командах](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет библиотеку общих команд, которые состоит из <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, и <xref:System.Windows.Documents.EditingCommands>, или определить собственные.  
  
 Приведенный ниже показано, как настроить <xref:System.Windows.Controls.MenuItem> так, что при его выборе вызывается <xref:System.Windows.Input.ApplicationCommands.Paste%2A> на <xref:System.Windows.Controls.TextBox>, если <xref:System.Windows.Controls.TextBox> установлен фокус клавиатуры.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
 Дополнительные сведения о командах в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в разделе [Общие сведения о командах](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="the_input_system_and_base_elements"></a>   
## <a name="the-input-system-and-base-elements"></a>Система ввода и базовые элементы  
 Входные события, такие как вложенные события, определенные <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, и <xref:System.Windows.Input.Stylus> классы создано системой ввода и вставленных в определенном положении в объектной модели, в зависимости от попадания визуального дерева во время выполнения.  
  
 Каждое из этих событий, <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, и <xref:System.Windows.Input.Stylus> определяется, как вложенное событие, также переопределяется классами базового элемента <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement> как новый перенаправленных событий. Перенаправленные события базового элемента создаются классами, обработка исходное вложенное событие и повторное использование данных события.  
  
 Событие ввода становится связанным с особым элементом источника через его реализацию события ввода базового элемента, могут направляться через остаток маршрута события, основанного на комбинации логических и визуальных объектов дерева и обрабатываться кодом приложения.  Как правило, удобнее обрабатывать эти связанные с устройством события ввода с помощью перенаправленных событий в <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement>, поскольку можно использовать более интуитивно понятный синтаксис обработчика событий и в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и в коде. Можно обрабатывать вложенное событие, инициированное процесса, вместо этого, но это сопряжено с несколько проблем: вложенное событие может быть отмечено как обработанное обработка базового элемента класса, и необходимо использовать методы доступа вместо действительного синтаксиса для присоединения обработчиков вложенных событий.  
  
<a name="whats_next"></a>   
## <a name="whats-next"></a>Что дальше?  
 Можно использовать несколько методов обработки ввода в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Следует также были рассмотрены различные типы событий ввода и механизмы события маршрутизации, используемые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Доступны дополнительные ресурсы, объяснить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементам структуры и маршрутизация событий более подробно. Следующие обзоры, Дополнительные сведения см. в разделе [Общие сведения о командах](../../../../docs/framework/wpf/advanced/commanding-overview.md), [фокус Обзор](../../../../docs/framework/wpf/advanced/focus-overview.md), [Обзор элементов базы](../../../../docs/framework/wpf/advanced/base-elements-overview.md), [деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md), и [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о фокусе](../../../../docs/framework/wpf/advanced/focus-overview.md)   
 [Общие сведения о командах](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Обзор маршрутизированных событий](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Общие сведения о базовых элементах](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [Свойства](../../../../docs/framework/wpf/advanced/properties-wpf.md)