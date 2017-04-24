---
title: "Пошаговое руководство. Размещение элемента управления Win32 в WPF | Microsoft Docs"
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
  - "размещение элемента управления Win32 в WPF"
  - "код Win32, взаимодействие с WPF"
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Пошаговое руководство. Размещение элемента управления Win32 в WPF
Клиент [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений.  Однако при создании сложного кода [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] более эффективно использовать, по крайней мере, часть этого кода повторно в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вместо того, чтобы переписывать его заново.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет простой механизм для размещения окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] на странице [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 В этом разделе представлено пошаговое руководство по разработке приложения, пример которого представлен в документе [Hosting a Win32 ListBox Control in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159998). В этом приложении размещается элемент управления "Список" [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Эта общая процедура может быть расширена для размещения любого окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
   
  
<a name="requirements"></a>   
## Требования  
 В материалах данного раздела предполагается начальное знакомство с программированием [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Основные сведения о программировании [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Начало работы](../../../../docs/framework/wpf/getting-started/index.md).  Для знакомства с программированием [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] следует обратиться к любой из многочисленных книг по этой теме, например, к *Programming Windows*, автор Charles Petzold.  
  
 Поскольку пример, используемый в этом разделе, реализован на языке [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], в нем применяется [!INCLUDE[TLA#tla_pinvoke](../../../../includes/tlasharptla-pinvoke-md.md)] для доступа к [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)].  Знакомство с [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] является полезным, но не необходимым.  
  
> [!NOTE]
>  Раздел включает ряд примеров кода из связанного с ним примера.  Тем не менее, для удобства чтения, он не включает в себя полный код примера.  Полный код можно получить или посмотреть в разделе [Пример размещения элемента управления Win32 ListBox в приложении WPF](http://go.microsoft.com/fwlink/?LinkID=159998).  
  
<a name="basic_procedure"></a>   
## Основная процедура  
 В этом подразделе описывается основная процедура размещения окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] на странице [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  В остальных подразделах рассмотрены детали каждого шага.  
  
 Основная процедура размещения:  
  
1.  Реализуйте страницу [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в которой будет размещено окно.  Одним из способов является создание элемента <xref:System.Windows.Controls.Border> для того, чтобы зарезервировать раздел страницы для размещаемого окна.  
  
2.  Реализуйте класс для размещения элемента управления, наследующего от <xref:System.Windows.Interop.HwndHost>.  
  
3.  В этом классе переопределите для члена класса <xref:System.Windows.Interop.HwndHost> метод <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  
  
4.  Создайте размещаемое окно как дочерний элемент окна, содержащего страницу [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Хотя в традиционном программировании [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не требуется явно это использовать, размещающая страница представляет собой окно с дескриптором \(HWND\).  HWND страницы можно получить с помощью параметра `hwndParent` метода <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  Размещаемое окно должно быть создано как дочерний элемент этого HWND.  
  
5.  После создания ведущего окна нужно вернуть HWND размещаемого окна.  Если требуется разместить один или несколько элементов управления [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], окно, как правило, создается как дочерний элемент HWND, и элементы управления создаются как его дочерние элементы.  Размещение элементов управления в главном окне предоставляет простой способ получения страницей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] уведомлений от элементов управления, таким образом решаются некоторые проблемы [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] с передачей уведомлений через границу HWND.  
  
6.  Обрабатывайте выбранные сообщения, посланные главному окну, такие как уведомления от дочерних элементов управления.  Это можно сделать двумя способами.  
  
    -   Если вы предпочитаете обработку сообщений в размещающем классе, переопределите метод <xref:System.Windows.Interop.HwndHost.WndProc%2A> класса <xref:System.Windows.Interop.HwndHost>.  
  
    -   Если вы предпочитаете обработку сообщений в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], обрабатывайте событие <xref:System.Windows.Interop.HwndHost.MessageHook> класса <xref:System.Windows.Interop.HwndHost> в фоновом коде.  Это событие возникает для каждого сообщения, получаемого размещаемым окном.  Если выбрать такой вариант, по\-прежнему необходимо переопределить <xref:System.Windows.Interop.HwndHost.WndProc%2A>, но достаточно минимальной реализации.  
  
7.  Переопределите методы <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> и <xref:System.Windows.Interop.HwndHost.WndProc%2A> для <xref:System.Windows.Interop.HwndHost>.  Эти методы необходимо переопределить для соблюдения контракта <xref:System.Windows.Interop.HwndHost>, но может потребоваться лишь минимальная реализация.  
  
8.  В файле кода программной части создайте экземпляр класса, размещающего элементы управления, и сделайте его дочерним элементом элемента <xref:System.Windows.Controls.Border>, предназначенного для размещения окна.  
  
9. Производите обмен данными с размещенным окном с помощью отправки сообщений [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] и обработки сообщений его дочерних окон, например, уведомлений, отправленных элементами управления.  
  
<a name="page_layout"></a>   
## Реализация макета страницы  
 Макет для страницы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], на которой размещен элемент управления ListBox, состоит из двух областей.  В левой части страницы размещены несколько элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые предоставляют [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], позволяющий управлять элементом управления [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  В верхнем правом углу страницы есть квадратная область для размещенного элемента управления ListBox.  
  
 Код реализации этого макета довольно прост.  Корневой элемент — это <xref:System.Windows.Controls.DockPanel>, имеющий два дочерних элемента.  Первый элемент — это <xref:System.Windows.Controls.Border>, в котором размещен элемент управления ListBox.  Он занимает квадрат 200x200 в верхнем правом углу страницы.  Второй элемент — это <xref:System.Windows.Controls.StackPanel>, содержащий набор элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], отображающих сведения и позволяющих управлять элементом управления ListBox путем задания предоставленных свойств взаимодействия.  Для каждого из элементов, являющихся потомками <xref:System.Windows.Controls.StackPanel>, справочные материалы по различным элементам, используемым для детализации того, чем эти элементы являются и что они делают, перечислены в примере ниже, но они не будут описаны здесь \(в базовой модели взаимодействия они не требуются, они предоставлены для добавления интерактивности в пример\).  
  
 [!code-xml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## Реализация класса для размещения элемента управления Microsoft Win32  
 Ядром этого образца является класс, фактически размещающий элемент управления ControlHost.cs.  Он наследуется от <xref:System.Windows.Interop.HwndHost>.  Конструктор принимает два параметра, высоту и ширину, которые соответствуют высоте и ширине элемента <xref:System.Windows.Controls.Border>, размещающего элемент управления ListBox.  Эти значения используются позднее, чтобы убедиться, что размер элемента управления соответствует элементу <xref:System.Windows.Controls.Border>.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Имеется также набор констант.  Эти константы в основном берутся из Winuser.h и позволяют использовать обычные имена при вызове функций [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### Переопределение BuildWindowCore для создания окна Microsoft Win32  
 Переопределите этот метод для создания окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], которое будет размещаться на странице, и создайте связь между окном и страницей.  Поскольку в этом примере также размещается элемент управления ListBox, создаются два окна.  Первое окно — это окно, фактически размещенное на странице [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Элемент управления ListBox создается в качестве дочернего элемента этого окна.  
  
 Причиной такого подхода является упрощение процесса получения уведомлений от элемента управления.  Класс <xref:System.Windows.Interop.HwndHost> позволяет обрабатывать сообщения, отправленные размещаемому окну.  Если разместить элемент управления [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] непосредственно, то будут приходить сообщения, отправленные во внутреннем цикле сообщений элемента управления.  Можно отображать элемент управления и отправлять ему сообщения, но не получать уведомления, которые элемент управления отправляет своему родительскому окну.  Это означает, помимо прочего, что нет способа обнаружения взаимодействия пользователя с элементом управления.  Вместо этого создайте главное окно и сделайте элемент управления дочерним элементом этого окна.  Это позволяет обрабатывать сообщения для главного окна, в том числе уведомления, отправленные ему элементом управления.  Поскольку главное окно является большим, чем простая обертка для элемента управления, для удобства пакет будет называться элементом управления ListBox.  
  
<a name="create_the_window_and_listbox"></a>   
#### Создание главного окна и элемента управления ListBox  
 [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] можно использовать для создания главного окна для элемента управления путем создания и регистрации класса окна и т.д.  Однако намного более простым способом является создание окна с помощью предопределенного "статического" класса окна.  При этом можно использовать процедуру окна, необходимую для получения уведомлений от элемента управления, причем в этом случае требуется минимум кода.  
  
 HWND элемента управления предоставляется только через свойство только для чтения, чтобы главная страница могла использовать его для отправки сообщений элементу управления.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Элемент управления ListBox создается в качестве дочернего элемента главного окна.  Высота и ширина обоих окон задаются значениями, передаваемыми конструктору, описанному выше.  Это гарантирует, что размеры главного окна и элемента управления совпадают с зарезервированной областью на странице.  После создания окна образец возвращает объект <xref:System.Runtime.InteropServices.HandleRef>, содержащий HWND главного окна.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### Реализация DestroyWindow и WndProc  
 В дополнение к <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> необходимо также переопределить методы <xref:System.Windows.Interop.HwndHost.WndProc%2A> и <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> для <xref:System.Windows.Interop.HwndHost>.  В этом примере сообщения для элемента управления обрабатываются обработчиком <xref:System.Windows.Interop.HwndHost.MessageHook>, таким образом, реализация <xref:System.Windows.Interop.HwndHost.WndProc%2A> и <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> минимальна.  В случае <xref:System.Windows.Interop.HwndHost.WndProc%2A> задайте параметру `handled` значение `false` для указания того, что сообщение не было обработано, и верните 0.  В случае <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> просто уничтожьте окно.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## Размещение элемента управления на странице  
 Чтобы разместить элемент управления на странице, сначала создайте новый экземпляр класса `ControlHost`.  Передайте высоту и ширину элемента границы, содержащего элемент управления \(`ControlHostElement`\), конструктору `ControlHost`.  При этом гарантируется корректность размеров элемента управления ListBox.  Затем разместите элемент управления на странице путем назначения объекта `ControlHost` свойству <xref:System.Windows.Controls.Decorator.Child%2A> ведущего <xref:System.Windows.Controls.Border>.  
  
 В образце задается обработчик событий <xref:System.Windows.Interop.HwndHost.MessageHook> для `ControlHost`, чтобы получать сообщения от элемента управления.  Это событие вызывается для каждого сообщения, посланного размещаемому окну.  В этом случае это сообщения, отправленные окну, которое служит оболочкой текущего элемента управления ListBox, включая уведомления от элемента управления.  В примере вызывается метод SendMessage для получения сведений от элемента управления и для изменения его содержимого.  Детали взаимодействия страницы с элементом управления рассматриваются в следующем подразделе.  
  
> [!NOTE]
>  Обратите внимание на то, что для SendMessage присутствуют два объявления [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)].  Это необходимо, так как в одном случае используется параметр `wParam` для передачи строки, а в другом параметр используется для передачи целого числа.  Необходимо отдельно объявить каждую сигнатуру, чтобы убедиться, что данные маршалируются правильно.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## Реализация связи между элементом управления и страницей  
 Осуществляйте управление элементом управления путем отправки ему сообщений [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)].  Элемент управления уведомляет, когда пользователь взаимодействует с ним, путем отправки уведомлений своему главному окну.  [Пример размещения элемента управления Win32 ListBox в приложении WPF](http://go.microsoft.com/fwlink/?LinkID=159998) включает в себя пользовательский интерфейс, который предоставляет несколько примеров того, как это работает.  
  
-   Добавьте элемент в список.  
  
-   Удалите выделенный элемент из списка.  
  
-   Отобразите текст текущего выделенного элемента списка.  
  
-   Отобразите количество элементов в списке.  
  
 Пользователь может также выбрать элемент в списке, щелкнув его, так же, как и для обычного приложения [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Отображаемые данные обновляется каждый раз, когда пользователь изменяет состояние списка путем выбора или добавления элемента.  
  
 Чтобы добавить элементы, отправьте списку сообщение LB\_ADDSTRING.  Чтобы удалить элементы, отправьте LB\_GETCURSEL для получения индекса текущего выделенного элемента, а затем LB\_DELETESTRING для удаления элемента.  В примере также отправляется LB\_GETCOUNT, а возвращенное значение используется для обновления экрана, отображающего число элементов.  В обоих экземплярах SendMessage используется одно из объявлений [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)], рассмотренных в предыдущем подразделе.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Когда пользователь выбирает элемент, изменяется область выделения, и элемент управления уведомляет главное окно путем отправки ему сообщения WM\_COMMAND, которое вызывает событие <xref:System.Windows.Interop.HwndHost.MessageHook> для страницы.  Обработчик получает те же сведения, что и процедура главного окна.  Он также передает ссылку на логическое значение `handled`.  Присвойте параметру `handled` значение `true`, чтобы указать, что сообщение было обработано и дальнейшая обработка не требуется.  
  
 WM\_COMMAND отправляется по различным причинам, поэтому необходимо проверить идентификатор уведомления, чтобы определить, является ли событие тем, которое вы хотите обработать.  Идентификатор содержится в старшем слове параметра `wParam`.  Поскольку в [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] нет макроса HIWORD, в образце используются битовые операции для получения идентификатора.  Если пользователь сделал выбор или изменил его, идентификатором будет LBN\_SELCHANGE.  
  
 При получении LBN\_SELCHANGE образец получает индекс выбранного элемента путем отправки элементу управления сообщения LB\_GETCURSEL.  Чтобы получить текст, сначала следует создать <xref:System.Text.StringBuilder>.  Затем необходимо отправить элементу управления сообщение LB\_GETTEXT.  Передайте пустой объект <xref:System.Text.StringBuilder> как параметр `wParam`.  После возвращения SendMessage <xref:System.Text.StringBuilder> будет содержать текст выбранного элемента.  Для подобного использования SendMessage требуется другое объявление [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)].  
  
 Наконец, присвойте параметру `handled` значение `true`, чтобы указать, что сообщение было обработано.  
  
## См. также  
 <xref:System.Windows.Interop.HwndHost>   
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Пошаговое руководство. Начало работы с WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)