---
title: Общие сведения о фокусе
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
ms.openlocfilehash: de788ec3f0628ff2f7c422c76c73ff7985424113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186670"
---
# <a name="focus-overview"></a>Общие сведения о фокусе
Существует два основных понятия, относящихся к фокусу в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: фокус клавиатуры и логический фокус.  Фокус клавиатуры ссылается на элемент, получающий ввод с клавиатуры, а логический фокус ссылается на элемент в области фокуса, имеющий фокус.  Эти понятия подробно освещаются в этом обзоре.  Важно понимать разницу между этими понятиями, чтобы создавать сложные приложения с несколькими областями, в которых можно получить фокус.  
  
 Основными классами, участвующими в <xref:System.Windows.Input.Keyboard> управлении <xref:System.Windows.Input.FocusManager> фокусами, являются класс, <xref:System.Windows.UIElement> класс <xref:System.Windows.ContentElement>и классы базовых элементов, такие как и .  Дополнительные сведения о базовых элементах см. в разделе [Общие сведения о базовых элементах](base-elements-overview.md).  
  
 Класс <xref:System.Windows.Input.Keyboard> связан в первую очередь <xref:System.Windows.Input.FocusManager> с клавиатурой фокус и касается в первую очередь с логическим фокусом, но это не является абсолютным различием.  Элемент, имеющий фокус клавиатуры, также будет иметь логический фокус, но элемент, имеющий логический фокус, не обязательно будет иметь фокус клавиатуры.  Это очевидно, когда <xref:System.Windows.Input.Keyboard> вы используете класс, чтобы установить элемент, который имеет фокус клавиатуры, потому что он также устанавливает логический фокус на элементе.  

<a name="Keyboard_Focus"></a>
## <a name="keyboard-focus"></a>Фокус клавиатуры  
 Фокус клавиатуры относится к элементу, получающему ввод с клавиатуры.  На всем рабочем столе может быть только один элемент, в котором находится фокус клавиатуры.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], элемент, который имеет <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> клавиатуру фокус будет установлен на `true`.  Статическое <xref:System.Windows.Input.Keyboard.FocusedElement%2A> свойство <xref:System.Windows.Input.Keyboard> в классе получает элемент, который в настоящее время имеет фокус клавиатуры.  
  
 Для того, чтобы элемент получил <xref:System.Windows.UIElement.Focusable%2A> фокус <xref:System.Windows.UIElement.IsVisible%2A> клавиатуры, и свойства на `true`базовых элементах должны быть установлены.  Некоторые классы, <xref:System.Windows.Controls.Panel> такие как <xref:System.Windows.UIElement.Focusable%2A> базовый `false` класс, установлены по умолчанию; поэтому, вы <xref:System.Windows.UIElement.Focusable%2A> должны `true` установить, если вы хотите такой элемент, чтобы иметь возможность получить клавиатуру фокус.  
  
 Фокус клавиатуры можно получить с помощью взаимодействия пользователя с [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], например перехода к элементу или щелчка мышью определенных элементов.  Клавиатура фокус также может быть получена <xref:System.Windows.Input.Keyboard.Focus%2A> программно <xref:System.Windows.Input.Keyboard> с помощью метода на класс.  Метод <xref:System.Windows.Input.Keyboard.Focus%2A> пытается придать заданную клавиатуру элемента фокусировку.  Возвращаемый элемент — это элемент, имеющий фокус клавиатуры, который может отличаться от запрошенного, если старый или новый объект фокуса блокирует запрос.  
  
 В следующем примере <xref:System.Windows.Input.Keyboard.Focus%2A> используется метод для <xref:System.Windows.Controls.Button>настройки фокусировки клавиатуры на .  
  
 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Свойство <xref:System.Windows.UIElement.IsKeyboardFocused%2A> в классах базовых элементов получает значение, указывающее, имеет ли элемент фокус клавиатуры.  Свойство <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> на базовых классах элементов получает значение, указывающее, имеет ли элемент или любой из его визуальных элементов ребенка фокус клавиатуру.  
  
 При настройке первоначального фокуса при запуске приложения элемент для получения фокуса должен находиться в визуальном древе исходного окна, загруженного приложением, а элемент должен иметь <xref:System.Windows.UIElement.Focusable%2A> и <xref:System.Windows.UIElement.IsVisible%2A> устанавливаться на. `true`  Рекомендуемое место для установки <xref:System.Windows.FrameworkElement.Loaded> первоначального фокуса находится в обработчике событий.  Обратный <xref:System.Windows.Threading.Dispatcher> вызов также может <xref:System.Windows.Threading.Dispatcher.Invoke%2A> быть <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>использован по телефону или .  
  
<a name="Logical_Focus"></a>
## <a name="logical-focus"></a>Логический фокус  
 Логическое внимание <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> относится к области фокусировки.  Область фокусировки — это элемент, который отслеживает <xref:System.Windows.Input.FocusManager.FocusedElement%2A> область охвата.  Когда фокус клавиатуры покидает область фокуса, элемент с фокусом теряет фокус клавиатуры, но сохраняет логический фокус.  При возвращении фокуса клавиатуры в область фокуса элемент с логическим фокусом получит фокус клавиатуры.  Это позволяет переносить фокус клавиатуры между несколькими областями фокуса, но гарантирует, что элемент с фокусом в области фокуса останется элементом с фокусом клавиатуры, когда фокус вернется в эту область.  
  
 В приложении может быть несколько элементов, имеющих логический фокус, но в отдельной области фокуса может быть только один элемент, имеющий логический фокус.  
  
 Элемент, имеющий фокус клавиатуры, имеет логический фокус для области фокуса, которой он принадлежит.  
  
 Элемент может быть превращен [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] в область фокусировки, установив <xref:System.Windows.Input.FocusManager> прилагаемое свойство <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> к `true`.  В коде элемент можно превратить в область <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>фокусировки, вызывая .  
  
 Следующий пример <xref:System.Windows.Controls.StackPanel> делает область фокусировки, установив <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> прилагаемое свойство.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>возвращает область фокусировки для указанного элемента.  
  
 Классы, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в которых фокус <xref:System.Windows.Window>областей по умолчанию, <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Controls.ToolBar>и <xref:System.Windows.Controls.ContextMenu>.  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>получает сфокусированный элемент для заданной области фокусировки.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>устанавливает сфокусированный элемент в заданной области фокусировки.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>обычно используется для установки исходного сфокусированного элемента.  
  
 В следующем примере элемент с фокусом задается в области фокуса и возвращает элемент с фокусом для области фокуса.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>
## <a name="keyboard-navigation"></a>Навигация с помощью клавиатуры  
 Класс <xref:System.Windows.Input.KeyboardNavigation> отвечает за реализацию навигации фокусировки клавиатуры по умолчанию при нажатии одного из клавиш навигации.  Клавиши навигации: TAB, SHIFT+TAB, CTRL+TAB, CTRL+SHIFT+TAB, стрелка вверх, стрелка вниз, стрелка влево и стрелка вправо.  
  
 Навигационное поведение навигационного контейнера может быть <xref:System.Windows.Input.KeyboardNavigation> изменено путем настройки прилагаемых свойств <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>и. <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>  Эти свойства типа <xref:System.Windows.Input.KeyboardNavigationMode> и возможные <xref:System.Windows.Input.KeyboardNavigationMode.Continue> <xref:System.Windows.Input.KeyboardNavigationMode.Local>значения, <xref:System.Windows.Input.KeyboardNavigationMode.Contained> <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>, <xref:System.Windows.Input.KeyboardNavigationMode.Once>, <xref:System.Windows.Input.KeyboardNavigationMode.None>и .  Значение по <xref:System.Windows.Input.KeyboardNavigationMode.Continue>умолчанию, что означает, что элемент не является навигационным контейнером.  
  
 Следующий пример <xref:System.Windows.Controls.Menu> создает с <xref:System.Windows.Controls.MenuItem> рядом объектов.  Прилагаемое <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> свойство <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> устанавливается на <xref:System.Windows.Controls.Menu>.  При изменении фокусировки с <xref:System.Windows.Controls.Menu>помощью ключа вкладки в фокусе будет перемещаться от каждого элемента, а при том, как последний элемент будет достигнут, фокус вернется к первому элементу.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>
## <a name="navigating-focus-programmatically"></a>Перемещение фокуса программными средствами  
 Дополнительные API для <xref:System.Windows.UIElement.MoveFocus%2A> работы с фокусом и <xref:System.Windows.UIElement.PredictFocus%2A>.  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>изменения фокусировки на следующий элемент приложения.  A <xref:System.Windows.Input.TraversalRequest> используется для указания направления.   <xref:System.Windows.Input.FocusNavigationDirection> Пройдено <xref:System.Windows.UIElement.MoveFocus%2A> еде для того чтобы обупознавать различные фокусы направлений можно перенести, such <xref:System.Windows.Input.FocusNavigationDirection.First>as, <xref:System.Windows.Input.FocusNavigationDirection.Last> <xref:System.Windows.Input.FocusNavigationDirection.Up> и <xref:System.Windows.Input.FocusNavigationDirection.Down>.  
  
 Следующий пример <xref:System.Windows.FrameworkElement.MoveFocus%2A> используется для изменения сфокусированного элемента.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>возвращает объект, который получил бы фокус, если фокус был изменен.  В настоящее <xref:System.Windows.Input.FocusNavigationDirection.Down> <xref:System.Windows.Input.FocusNavigationDirection.Left>время <xref:System.Windows.Input.FocusNavigationDirection.Right> только <xref:System.Windows.Input.FocusNavigationDirection.Up>, <xref:System.Windows.FrameworkElement.PredictFocus%2A>, , и поддерживаются .  
  
<a name="Focus_Events"></a>
## <a name="focus-events"></a>События фокуса  
 События, связанные с <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> клавиатурой фокус, и , и <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>. <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>  События определяются как прилагаемые события в <xref:System.Windows.Input.Keyboard> классе, но более легко доступны как эквивалентные маршрутизированные события в классах базовых элементов.  Дополнительные сведения о событиях см. в разделе [Общие сведения о перенаправленных событиях](routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>поднимается, когда элемент получает фокус клавиатуры.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>поднимается, когда элемент теряет фокус клавиатуры.  Если <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> событие или <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> событие обработано <xref:System.Windows.RoutedEventArgs.Handled%2A> и `true`настроено на, то фокус не изменится.  
  
 Следующий пример <xref:System.Windows.UIElement.GotKeyboardFocus> прикрепляет и <xref:System.Windows.UIElement.LostKeyboardFocus> <xref:System.Windows.Controls.TextBox>обработчики событий к .  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Когда <xref:System.Windows.Controls.TextBox> получает фокус клавиатуры, <xref:System.Windows.Controls.Control.Background%2A> свойство <xref:System.Windows.Controls.TextBox> изменяется на <xref:System.Windows.Media.Brushes.LightBlue%2A>.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Когда <xref:System.Windows.Controls.TextBox> теряет фокус клавиатуры, <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.TextBox> свойство изменено назад к белому цвету.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 События, связанные с <xref:System.Windows.UIElement.GotFocus> <xref:System.Windows.UIElement.LostFocus>логическим фокусом и .  Эти события определяются <xref:System.Windows.Input.FocusManager> на как прикрепленные <xref:System.Windows.Input.FocusManager> события, но не разоблачают обертки событий CLR.  <xref:System.Windows.UIElement>и <xref:System.Windows.ContentElement> разоблачить эти события более удобно.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Input.FocusManager>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.ContentElement>
- [Общие сведения о входных данных](input-overview.md)
- [Общие сведения о базовых элементах](base-elements-overview.md)
