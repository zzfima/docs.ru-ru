---
title: "Общие сведения о фокусе | Microsoft Docs"
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
  - "приложения, фокус"
  - "фокус в приложениях"
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Общие сведения о фокусе
Приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеет два основных понятия фокуса: фокус ввода и логический фокус.  Фокус ввода ссылается на элемент, который получает ввод данных с клавиатуры, а логической фокус ссылается на элемент в области, на которой установлен фокус.  Эти понятия подробно обсуждаются в этом разделе.  Общее представление о различии в этих понятиях важно для создания сложных приложений, имеющих несколько областей, в которых можно получить фокус.  
  
 Основными классами, которые участвуют в управлении фокусом, является класс <xref:System.Windows.Input.Keyboard>, класс <xref:System.Windows.Input.FocusManager> и классы базовых элементов, такие как <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement>.  Дополнительные сведения о базовых элементах содержатся в разделе [Общие сведения о базовых элементах](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  
  
 Класс <xref:System.Windows.Input.Keyboard> относится, в основном, к фокусу ввода, а класс <xref:System.Windows.Input.FocusManager> — к логическому фокусу, но это не абсолютное различие.  Элемент, имеющий фокус ввода, также будет иметь логический фокус, но элемент, имеющий логический фокус, не обязательно имеет фокус ввода.  Это видно при использовании класса <xref:System.Windows.Input.Keyboard> для задания элемента, имеющего фокус ввода, потому что он также задает логический фокус на этом элементе.  
  
   
  
<a name="Keyboard_Focus"></a>   
## Фокус клавиатуры  
 Фокус ввода ссылается на элемент, который получает текущий ввод данных с клавиатуры.  На всем рабочем столе одновременно может существовать только один элемент, имеющий фокус ввода.  В приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемент, имеющий фокус ввода, будет иметь для свойства <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> значение `true`.  Статическое свойство <xref:System.Windows.Input.Keyboard.FocusedElement%2A> класса <xref:System.Windows.Input.Keyboard> получает элемент, имеющий текущий фокус ввода.  
  
 Чтобы элемент получил фокус ввода, для свойства <xref:System.Windows.UIElement.Focusable%2A> и <xref:System.Windows.UIElement.IsVisible%2A> базовых элементов должно быть установлено значение `true`.  Некоторые классы, например базовый класс <xref:System.Windows.Controls.Panel>, имеют по умолчанию для свойства <xref:System.Windows.UIElement.Focusable%2A> значение `false`; поэтому необходимо установить для свойства <xref:System.Windows.UIElement.Focusable%2A> значение `true`, чтобы элемент мог получить фокус ввода.  
  
 Фокус ввода может быть получен с помощью взаимодействия пользователя с [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], например — перехода к элементу или щелчка мышью определенных элементов.  Фокус клавиатуры также может быть получен программными средствами с помощью метода <xref:System.Windows.Input.Keyboard.Focus%2A> для класса <xref:System.Windows.Input.Keyboard>.  Метод <xref:System.Windows.Input.Keyboard.Focus%2A> пытается предоставить фокус ввода указанному элементу.  Возвращаемый элемент является элементом, имеющим фокус ввода, который может отличаться от запрошенного элемента, если старый или новый объект фокуса блокирует запрос.  
  
 Следующий пример использует метод <xref:System.Windows.Input.Keyboard.Focus%2A>, чтобы установить фокус ввода на объекте <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Свойство <xref:System.Windows.UIElement.IsKeyboardFocused%2A> для классов базовых элементов получает значение, указывающее, имеет ли элемент фокус ввода.  Свойство <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> для классов базовых элементов получает значение, указывающее, имеет ли элемент, или один из его видимых дочерних элементов, фокус ввода.  
  
 Когда устанавливается начальный фокус при запуске приложения, элемент, получающий фокус, должен находиться в визуальном дереве исходного окна, загруженного приложением, а свойствам <xref:System.Windows.UIElement.Focusable%2A> и <xref:System.Windows.UIElement.IsVisible%2A> элемента должно быть присвоено значение `true`.  Рекомендуемым местом для установки начального фокуса является обработчик событий <xref:System.Windows.FrameworkElement.Loaded>.  Обратный вызов <xref:System.Windows.Threading.Dispatcher> может также использоваться посредством вызова метода <xref:System.Windows.Threading.Dispatcher.Invoke%2A> или <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>.  
  
<a name="Logical_Focus"></a>   
## Логический фокус  
 Логический фокус относится к свойству <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=fullName> в области фокуса.  Областью фокуса является элемент, который хранит путь свойства <xref:System.Windows.Input.FocusManager.FocusedElement%2A> в этой области.  Когда фокус ввода покидает область фокуса, фокусируемый элемент теряет фокус ввод, но сохраняет логический фокус.  При возвращении фокуса ввода к области фокуса, фокусируемый элемент снова получает фокус ввода.  Это позволяет фокусу ввода переходить между несколькими областями фокуса, но гарантирует, что фокусируемый элемент в области фокуса снова получает фокус ввода, когда фокус возвращается в область фокуса.  
  
 В приложении может существовать несколько элементов, имеющих логический фокус, но в отдельной области фокуса только один элемент может иметь логический фокус.  
  
 Элемент с фокусом ввода имеет логический фокус для области фокуса к которой он принадлежит.  
  
 Элемент может быть включен в область фокуса в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] путем задания для вложенного свойства зависимостей <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> объекта <xref:System.Windows.Input.FocusManager> значения `true`.  В коде элемент может быть включен в область фокуса путем вызова метода <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.  
  
 В следующем примере создается объект <xref:System.Windows.Controls.StackPanel> в области фокуса путем установки присоединенного значения <xref:System.Windows.Input.FocusManager.IsFocusScope%2A>.  
  
 [!code-xml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 Метод <xref:System.Windows.Input.FocusManager.GetFocusScope%2A> возвращает область фокуса для указанного элемента.  
  
 Классы в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], являющиеся областью фокуса, по умолчанию являются объектами <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar> и <xref:System.Windows.Controls.ContextMenu>.  
  
 Метод <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A> возвращает фокусируемый элемент для заданной области фокуса.  Метод <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> устанавливает фокусируемый элемент в заданной области фокуса.  Как правило, метод <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> используется для задания начального фокусируемого элемента.  
  
 В следующем примере задается и устанавливается сфокусированный элемент в области фокуса.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## Навигация с помощью клавиатуры  
 Класс <xref:System.Windows.Input.KeyboardNavigation> отвечает за реализацию навигации фокуса ввода по умолчанию при нажатии одной из клавиш навигации.  К клавишам навигации относятся TAB, SHIFT \+ TAB, CTRL \+ TAB, CTRL \+ SHIFT \+ TAB, стрелка вверх, стрелка вниз, левая стрелка и правая стрелка.  
  
 Поведение перехода контейнера перехода можно изменить при помощи вложенных свойств <xref:System.Windows.Input.KeyboardNavigation> <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A> и <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>.  Эти свойства являются объектом <xref:System.Windows.Input.KeyboardNavigationMode> типа, и возможными значениями являются: <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode> и <xref:System.Windows.Input.KeyboardNavigationMode>.  Значение по умолчанию — <xref:System.Windows.Input.KeyboardNavigationMode>, которое означает, что элемент не является контейнером навигации.  
  
 В следующем примере создается объект <xref:System.Windows.Controls.Menu> с объектами <xref:System.Windows.Controls.MenuItem>.  Для вложенного свойства <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> в объекте <xref:System.Windows.Controls.Menu> устанавливается значение <xref:System.Windows.Input.KeyboardNavigationMode>.  При изменении фокуса с помощью клавиши tab в объекте <xref:System.Windows.Controls.Menu> фокус последовательно перемещается между элементами и при достижении последнего элемента переходит на первый элемент.  
  
 [!code-xml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## Перемещение фокуса программными средствами  
 Дополнительными[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] для работы с фокусом являются <xref:System.Windows.UIElement.MoveFocus%2A> и <xref:System.Windows.UIElement.PredictFocus%2A>.  
  
 Метод <xref:System.Windows.FrameworkElement.MoveFocus%2A> перемещает фокус на следующий элемент в приложении.  Объект <xref:System.Windows.Input.TraversalRequest> используется для указания направления.  Объект <xref:System.Windows.Input.FocusNavigationDirection>, переданный методу <xref:System.Windows.UIElement.MoveFocus%2A>, задает различные возможные направления передвижения фокуса, например <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection> и <xref:System.Windows.Input.FocusNavigationDirection>.  
  
 В следующем примере используется метод <xref:System.Windows.FrameworkElement.MoveFocus%2A> для изменения сфокусированного элемента.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 Метод <xref:System.Windows.FrameworkElement.PredictFocus%2A> возвращает объект, который мог бы получить фокус, если фокус будет изменен.  В текущий момент только свойства <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection> <xref:System.Windows.Input.FocusNavigationDirection> и <xref:System.Windows.Input.FocusNavigationDirection> поддерживаются методом <xref:System.Windows.FrameworkElement.PredictFocus%2A>.  
  
<a name="Focus_Events"></a>   
## События фокуса  
 Событиями, связанными с фокусом ввода, являются <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> и <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>, <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.  События определяются как вложенные события в классе <xref:System.Windows.Input.Keyboard>, но более легко доступны как эквивалентные маршрутизированные события в классах базовых элементов.  Дополнительные сведениями о событиях см. в разделе [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Событие <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> возникает в том случае, когда элемент получает фокус ввода.  Событие <xref:System.Windows.Input.Keyboard.LostKeyboardFocus> возникает в том случае, когда элемент теряет фокус ввода.  Если обрабатывается событие <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> или <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> и для свойства <xref:System.Windows.RoutedEventArgs.Handled%2A> установлено значение `true`, тогда фокус не изменяется.  
  
 В следующем примере присоединяются обработчики событий <xref:System.Windows.UIElement.GotKeyboardFocus> и <xref:System.Windows.UIElement.LostKeyboardFocus> к объекту <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Когда объект <xref:System.Windows.Controls.TextBox> получает фокус ввода, свойство <xref:System.Windows.Controls.Control.Background%2A> объекта <xref:System.Windows.Controls.TextBox> изменяется на свойство <xref:System.Windows.Media.Brushes.LightBlue%2A>.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Когда объект <xref:System.Windows.Controls.TextBox> теряет фокус ввода, свойство <xref:System.Windows.Controls.Control.Background%2A> объекта <xref:System.Windows.Controls.TextBox> снова становится пустым.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Событиями, связанными с логическим фокусом, являются <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus>.  Эти события определяются в объекте <xref:System.Windows.Input.FocusManager> в качестве вложенных событий, но <xref:System.Windows.Input.FocusManager> не предоставляет оболочки событий среды CLR.  Элементы <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement> предоставляют эти события более удобным образом.  
  
## См. также  
 <xref:System.Windows.Input.FocusManager>   
 <xref:System.Windows.UIElement>   
 <xref:System.Windows.ContentElement>   
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Общие сведения о базовых элементах](../../../../docs/framework/wpf/advanced/base-elements-overview.md)