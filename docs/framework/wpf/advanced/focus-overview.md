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
ms.openlocfilehash: 620839a0060469604d0affa6637c3cafac0f62c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548114"
---
# <a name="focus-overview"></a>Общие сведения о фокусе
Существует два основных понятия, относящихся к фокусу в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: фокус клавиатуры и логический фокус.  Фокус клавиатуры ссылается на элемент, получающий ввод с клавиатуры, а логический фокус ссылается на элемент в области фокуса, имеющий фокус.  Эти понятия подробно освещаются в этом обзоре.  Важно понимать разницу между этими понятиями, чтобы создавать сложные приложения с несколькими областями, в которых можно получить фокус.  
  
 Основные классы, участвующие в управление фокусом <xref:System.Windows.Input.Keyboard> класса <xref:System.Windows.Input.FocusManager> класс и базовым элементом классов, таких как <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement>.  Дополнительные сведения о базовых элементах см. в разделе [Общие сведения о базовых элементах](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  
  
 <xref:System.Windows.Input.Keyboard> Класс занимается главным образом с фокусом клавиатуры и <xref:System.Windows.Input.FocusManager> занимается главным образом с логическим фокусом, но это не абсолютное различие.  Элемент, имеющий фокус клавиатуры, также будет иметь логический фокус, но элемент, имеющий логический фокус, не обязательно будет иметь фокус клавиатуры.  Это видно при использовании <xref:System.Windows.Input.Keyboard> класса, чтобы задать элемент, имеющий фокус ввода, для него также задает логический фокус на элемент.  
  

  
<a name="Keyboard_Focus"></a>   
## <a name="keyboard-focus"></a>Фокус клавиатуры  
 Фокус клавиатуры относится к элементу, получающему ввод с клавиатуры.  На всем рабочем столе может быть только один элемент, в котором находится фокус клавиатуры.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], элемент, имеющий фокус будет иметь <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> значение `true`.  Статическое свойство <xref:System.Windows.Input.Keyboard.FocusedElement%2A> на <xref:System.Windows.Input.Keyboard> классе, возвращает элемент, который в данный момент имеет фокус клавиатуры.  
  
 Чтобы получить фокус, элемент <xref:System.Windows.UIElement.Focusable%2A> и <xref:System.Windows.UIElement.IsVisible%2A> свойства базовых элементов должно быть присвоено `true`.  Некоторые классы, такие как <xref:System.Windows.Controls.Panel> базового класса, имеют <xref:System.Windows.UIElement.Focusable%2A> значение `false` по умолчанию; таким образом, необходимо задать <xref:System.Windows.UIElement.Focusable%2A> для `true` Если такой элемент, чтобы иметь возможность получать фокус клавиатуры.  
  
 Фокус клавиатуры можно получить с помощью взаимодействия пользователя с [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], например перехода к элементу или щелчка мышью определенных элементов.  Фокус клавиатуры также могут быть получены программно с помощью <xref:System.Windows.Input.Keyboard.Focus%2A> метод <xref:System.Windows.Input.Keyboard> класса.  <xref:System.Windows.Input.Keyboard.Focus%2A> Метод пытается передать фокус клавиатуры указанного элемента.  Возвращаемый элемент — это элемент, имеющий фокус клавиатуры, который может отличаться от запрошенного, если старый или новый объект фокуса блокирует запрос.  
  
 В следующем примере используется <xref:System.Windows.Input.Keyboard.Focus%2A> метод, чтобы установить фокус на <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 <xref:System.Windows.UIElement.IsKeyboardFocused%2A> Свойства в классах базовых элементов получает значение, указывающее, имеет ли элемент фокус клавиатуры.  <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> Свойство классов базовых элементов получает значение, указывающее, имеет ли элемент, или один из его видимых дочерних элементов фокус клавиатуры.  
  
 Когда устанавливается начальный фокус при запуске приложения, элемент, получающий фокус должен быть в визуальном дереве исходного окна, загруженных приложением, и элемент должен иметь <xref:System.Windows.UIElement.Focusable%2A> и <xref:System.Windows.UIElement.IsVisible%2A> значение `true`.  Рекомендуемым местом для установки начального фокуса является <xref:System.Windows.FrameworkElement.Loaded> обработчика событий.  Объект <xref:System.Windows.Threading.Dispatcher> обратного вызова также можно использовать путем вызова <xref:System.Windows.Threading.Dispatcher.Invoke%2A> или <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>.  
  
<a name="Logical_Focus"></a>   
## <a name="logical-focus"></a>Логический фокус  
 Логический фокус относится к <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> в области фокуса.  Областью фокуса является элемент, который отслеживает <xref:System.Windows.Input.FocusManager.FocusedElement%2A> в своей области действия.  Когда фокус клавиатуры покидает область фокуса, элемент с фокусом теряет фокус клавиатуры, но сохраняет логический фокус.  При возвращении фокуса клавиатуры в область фокуса элемент с логическим фокусом получит фокус клавиатуры.  Это позволяет переносить фокус клавиатуры между несколькими областями фокуса, но гарантирует, что элемент с фокусом в области фокуса останется элементом с фокусом клавиатуры, когда фокус вернется в эту область.  
  
 В приложении может быть несколько элементов, имеющих логический фокус, но в отдельной области фокуса может быть только один элемент, имеющий логический фокус.  
  
 Элемент, имеющий фокус клавиатуры, имеет логический фокус для области фокуса, которой он принадлежит.  
  
 Элемент может быть включен в область фокуса в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , установив <xref:System.Windows.Input.FocusManager> вложенное свойство <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> для `true`.  В коде, элемент может быть включен в область фокуса путем вызова <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.  
  
 В нижеследующем примере <xref:System.Windows.Controls.StackPanel> область фокуса, задав <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> вложенное свойство.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A> Возвращает область фокуса для указанного элемента.  
  
 Классы в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являющиеся областью фокуса по умолчанию являются <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar>, и <xref:System.Windows.Controls.ContextMenu>.  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A> Получает элемент с фокусом для заданной области фокуса.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> Задает элемент с фокусом в заданной области фокуса.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> обычно используется для задания начального элемента фокус.  
  
 В следующем примере элемент с фокусом задается в области фокуса и возвращает элемент с фокусом для области фокуса.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## <a name="keyboard-navigation"></a>Навигация с помощью клавиатуры  
 <xref:System.Windows.Input.KeyboardNavigation> Класс отвечает за реализацию навигации фокуса ввода по умолчанию при нажатии одной из клавиш навигации.  Клавиши навигации: TAB, SHIFT+TAB, CTRL+TAB, CTRL+SHIFT+TAB, стрелка вверх, стрелка вниз, стрелка влево и стрелка вправо.  
  
 Можно изменить поведение перехода контейнера при помощи вложенных <xref:System.Windows.Input.KeyboardNavigation> свойства <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>, и <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>.  Эти свойства имеют тип <xref:System.Windows.Input.KeyboardNavigationMode> и возможные значения: <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, <xref:System.Windows.Input.KeyboardNavigationMode.Local>, <xref:System.Windows.Input.KeyboardNavigationMode.Contained>, <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>, <xref:System.Windows.Input.KeyboardNavigationMode.Once>, и <xref:System.Windows.Input.KeyboardNavigationMode.None>.  Значение по умолчанию — <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, означает, что элемент не является контейнером навигации.  
  
 В следующем примере создается <xref:System.Windows.Controls.Menu> с количеством <xref:System.Windows.Controls.MenuItem> объектов.  <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> Вложенному свойству задано <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> на <xref:System.Windows.Controls.Menu>.  При изменении фокуса ввода с помощью клавиши tab в <xref:System.Windows.Controls.Menu>, фокус перемещается из каждого элемента, и при достижении последнего элемента переходит к первому элементу.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## <a name="navigating-focus-programmatically"></a>Перемещение фокуса программными средствами  
 Дополнительные [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] для работы с фокусом являются <xref:System.Windows.UIElement.MoveFocus%2A> и <xref:System.Windows.UIElement.PredictFocus%2A>.  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A> изменения фокуса к следующему элементу в приложении.  Объект <xref:System.Windows.Input.TraversalRequest> используется для указания направления.   <xref:System.Windows.Input.FocusNavigationDirection> Передаваемый <xref:System.Windows.UIElement.MoveFocus%2A> указывает, можно переместить фокус другое направление, таких как <xref:System.Windows.Input.FocusNavigationDirection.First>, <xref:System.Windows.Input.FocusNavigationDirection.Last>, <xref:System.Windows.Input.FocusNavigationDirection.Up> и <xref:System.Windows.Input.FocusNavigationDirection.Down>.  
  
 В следующем примере используется <xref:System.Windows.FrameworkElement.MoveFocus%2A> Чтобы изменить элемент с фокусом.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A> Возвращает объект, который должен получить фокус, если фокус должен быть изменен.  В настоящее время только <xref:System.Windows.Input.FocusNavigationDirection.Up>, <xref:System.Windows.Input.FocusNavigationDirection.Down>, <xref:System.Windows.Input.FocusNavigationDirection.Left>, и <xref:System.Windows.Input.FocusNavigationDirection.Right> поддерживаемых <xref:System.Windows.FrameworkElement.PredictFocus%2A>.  
  
<a name="Focus_Events"></a>   
## <a name="focus-events"></a>События фокуса  
 События, связанные с фокусом клавиатуры, <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> и <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>, <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.  События определяются как вложенные события в <xref:System.Windows.Input.Keyboard> класса, но более легко доступны как эквивалентные маршрутизированные события в классах базовых элементов.  Дополнительные сведения о событиях см. в разделе [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> возникает, когда элемент получает фокус клавиатуры.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus> возникает, когда элемент теряет фокус клавиатуры.  Если <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> событий или <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> событие обрабатывается и <xref:System.Windows.RoutedEventArgs.Handled%2A> имеет значение `true`, а затем фокус не изменяется.  
  
 В следующем примере присоединяется <xref:System.Windows.UIElement.GotKeyboardFocus> и <xref:System.Windows.UIElement.LostKeyboardFocus> обработчиков событий к <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Когда <xref:System.Windows.Controls.TextBox> получает фокус клавиатуры, <xref:System.Windows.Controls.Control.Background%2A> свойство <xref:System.Windows.Controls.TextBox> изменяется на <xref:System.Windows.Media.Brushes.LightBlue%2A>.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Когда <xref:System.Windows.Controls.TextBox> теряет фокус ввода, <xref:System.Windows.Controls.Control.Background%2A> свойство <xref:System.Windows.Controls.TextBox> изменяется обратно на белый.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 События, связанные с логическим фокусом, <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus>.  Эти события определяются в <xref:System.Windows.Input.FocusManager> как вложенные события, но <xref:System.Windows.Input.FocusManager> не предоставляет оболочки событий среды CLR.  <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement> предоставляют эти события более удобным образом.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Input.FocusManager>  
 <xref:System.Windows.UIElement>  
 <xref:System.Windows.ContentElement>  
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Общие сведения о базовых элементах](../../../../docs/framework/wpf/advanced/base-elements-overview.md)
