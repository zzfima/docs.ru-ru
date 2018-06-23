---
title: Пошаговое руководство. Размещение элемента управления Win32 в WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: af8491a2887f4a35e2cd9926304948c12a67623a
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314982"
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>Пошаговое руководство. Размещение элемента управления Win32 в WPF
Windows Presentation Foundation (WPF) предоставляет среду с широкими возможностями для создания приложений. Тем не менее, если имеются существенные преимущества в коде Win32 может быть более эффективным будет повторное использование по крайней мере некоторые этого кода в приложении WPF, а не переписывать его заново. WPF предоставляет простой механизм для размещения окна Win32, на странице WPF.  
  
 В этом разделе рассматриваются приложения, [размещения элемента управления ListBox Win32 в образце WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control), что узлы управления поле со списком Win32. Эта общая процедура может быть расширена для размещения любого окна Win32.  
  
  
<a name="requirements"></a>   
## <a name="requirements"></a>Требования  
 В этом разделе предполагается Знакомство с программированием WPF и Win32. Основные сведения о программировании WPF, в разделе [Приступая к работе](../../../../docs/framework/wpf/getting-started/index.md). Основные сведения о программировании Win32, вы должны ссылаться на любые многочисленные книги по вопросам, в частности *программирования Windows* , Чарльз Петцольд.  
  
 Пример, используемый в этом разделе реализована на C#, он использует службы вызова платформы (PInvoke) для доступа к Win32 API. Знакомство с PInvoke является полезным, но не необходимым.  
  
> [!NOTE]
>  Этот учебник включает ряд примеров кода из связанного примера. Однако для удобства чтения он не содержит полный пример кода. Можно получить или просмотреть полный исходный код из [размещения элемента управления ListBox Win32 в образце WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Основная процедура  
 В этом разделе описаны основные процедура по размещению окна Win32 на странице WPF. В остальных разделах подробно описывается каждый шаг.  
  
 Основная процедура размещения  
  
1.  Реализуйте страницу WPF для размещения окна. Один из способов — создание <xref:System.Windows.Controls.Border> элемент, чтобы зарезервировать раздел страницы для размещаемого окна.  
  
2.  Реализация класса для размещения элемента управления, который наследует от <xref:System.Windows.Interop.HwndHost>.  
  
3.  В этом классе переопределите <xref:System.Windows.Interop.HwndHost> член класса <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  
  
4.  Создайте размещаемое окно как дочерний элемент окна, содержащего страницу WPF. Несмотря на то, что обычная программирования WPF не требуется явно использовать, размещающая страница представляет собой окно с дескриптор (HWND). Появляется страница HWND через `hwndParent` параметр <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> метода. Размещаемое окно необходимо создать в качестве дочернего объекта этого окна HWND.  
  
5.  Создав главное окно, верните HWND размещаемого окна. Если необходимо разместить один или несколько элементов управления Win32, обычно создайте главное окно как дочерний элемент HWND и дочерние элементы управления, главного окна. Размещение элементов управления в главном окне предоставляет простой способ для страницы WPF для получения уведомлений от элементов управления, которые выполняет некоторые конкретные проблемы Win32 с уведомлениями через границу HWND.  
  
6.  Обрабатывайте некоторые сообщения, которые отправляются в главное окно, например уведомления от дочерних элементов управления. Это можно сделать двумя способами.  
  
    -   Если вы предпочитаете обработку сообщений в размещающем классе, переопределите <xref:System.Windows.Interop.HwndHost.WndProc%2A> метод <xref:System.Windows.Interop.HwndHost> класса.  
  
    -   Если вы предпочитаете WPF, которые обрабатывают сообщения, обрабатывать <xref:System.Windows.Interop.HwndHost> класса <xref:System.Windows.Interop.HwndHost.MessageHook> события в фоновом коде. Это событие возникает для каждого сообщения, получаемого размещаемым окном. Если выбран этот параметр, необходимо переопределить <xref:System.Windows.Interop.HwndHost.WndProc%2A>, но достаточно минимальную реализацию.  
  
7.  Переопределить <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> и <xref:System.Windows.Interop.HwndHost.WndProc%2A> методы <xref:System.Windows.Interop.HwndHost>. Необходимо переопределить эти методы, выполняющие <xref:System.Windows.Interop.HwndHost> контракт, но может потребоваться указать минимальную реализацию.  
  
8.  В файле кода, создайте экземпляр класса, размещающего элементы управления и сделайте его дочерним элементом <xref:System.Windows.Controls.Border> элемент, предназначенный для размещения окна.  
  
9. Обмениваться данными с размещенным окном путем отправки их [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] сообщения и сообщения обработки из его дочерних окон, таких как уведомления, отправленные элементами управления.  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>Реализация макета страницы  
 Макет страницы WPF, на котором размещается элемент управления ListBox состоит из двух областей. В левой части страницы содержит несколько элементов управления WPF, которые предоставляют [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] , позволяющий работать с элементом управления Win32. В правом верхнем углу страницы имеется квадратная область для размещенного элемента управления ListBox.  
  
 Код для реализации этого макета довольно проста. Корневой элемент — <xref:System.Windows.Controls.DockPanel> , имеющий два дочерних элемента. Во-первых, <xref:System.Windows.Controls.Border> элемент, на котором размещается элемент управления ListBox. Он занимает квадрат размером 200 x 200 в верхнем правом углу страницы. Во-вторых, <xref:System.Windows.Controls.StackPanel> элемент, который содержит набор элементов управления WPF, которые отображают информацию и позволяют работать с элементом управления ListBox, задав предоставленных свойств взаимодействия. Для каждого из элементов, которые являются потомками <xref:System.Windows.Controls.StackPanel>, справочные материалы по различным элементам, используемым для детализации на эти элементы являются и что они делают, перечислены в приведенном ниже примере кода, но не будут описаны здесь (basic модели взаимодействия не требуются, они предоставлены для добавления интерактивности в пример).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Реализация размещения элемента управления Microsoft Win32 в классе  
 Ядром этого образца является класс, который фактически размещает в себе элемент управления, ControlHost.cs. Он наследуется от <xref:System.Windows.Interop.HwndHost>. Конструктор принимает два параметра, высоту и ширину, которые соответствуют высоту и ширину <xref:System.Windows.Controls.Border> элемент, на котором размещается элемент управления ListBox. Эти значения используются позднее, чтобы убедиться, что размер элемента управления соответствует <xref:System.Windows.Controls.Border> элемента.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Кроме того, имеется набор констант. Эти константы в основном берутся из Winuser.h и позволяют использовать обычные имена при вызове функции Win32.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Переопределение класса BuildWindowCore для создания окна Microsoft Win32  
 Можно переопределить этот метод для создания окна Win32, будут размещаться на странице и создайте связь между окном и страницы. Поскольку в этом примере также показано размещение элемента управления ListBox, создаются два окна. Первый — это окно, фактически размещенное на странице WPF. Элемент управления ListBox создается в качестве дочернего элемента этого окна.  
  
 Это делается для того, чтобы упростить получение уведомлений от элемента управления. <xref:System.Windows.Interop.HwndHost> Позволяет обрабатывать сообщения, отправляемые в окно, на котором он размещен. Если непосредственно контролировать узла Win32, вы получите сообщения, отправленные во внутреннем цикле сообщений элемента управления. Можно отображать элемент управления и отправлять ему сообщения, но не получать уведомления, которые элемент управления отправляет своему родительскому окну. Это означает, среди прочего, что нет способа обнаружения взаимодействия пользователя с элементом управления. Вместо этого следует создать главное окно и сделать элемент управления дочерним элементом этого окна. Это позволит обрабатывать сообщения для главного окна, включая уведомления, отправляемые элементом управления. Для удобства, поскольку главное окно — это всего лишь программа-оболочка для элемента управления, мы будем называть этот пакет "элементом управления ListBox".  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>Создание главного окна и элемента управления ListBox  
 Можно использовать PInvoke для создания главного окна для элемента управления путем создания и регистрации класса окна и т. д. Однако гораздо проще создать окно с помощью готового "статического" класса окон. Это позволит реализовать в окне процедуру, необходимую для получения уведомлений из элемента управления, и требует минимальной работы с кодом.  
  
 HWND элемента управления предоставляется через доступное только для чтения свойство, чтобы главная страница могла использовать его для отправки сообщения элементу управления.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Элемент управления ListBox создается в качестве дочернего элемента главного окна. Высота и ширина обоих окон задается с помощью значений, передаваемых конструктору (см. выше). Это гарантирует, что размер главного окна и элемента управления идентичен размеру отведенной для них области на странице.  После создания окон, в образце кода возвращается <xref:System.Runtime.InteropServices.HandleRef> , содержащий HWND главного окна.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>Реализация классов DestroyWindow и WndProc  
 В дополнение к <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>, необходимо также переопределить <xref:System.Windows.Interop.HwndHost.WndProc%2A> и <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> методы <xref:System.Windows.Interop.HwndHost>. В этом примере сообщения для элемента управления обрабатываются <xref:System.Windows.Interop.HwndHost.MessageHook> обработчик, таким образом реализация <xref:System.Windows.Interop.HwndHost.WndProc%2A> и <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> сводится к минимуму. В случае использования <xref:System.Windows.Interop.HwndHost.WndProc%2A>, задайте `handled` для `false` для указания, что сообщение не было обработано и возвращают значение 0. Для <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, просто удалить окно.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>Размещение элемента управления на странице  
 Чтобы разместить элемент управления на странице, сначала создайте новый экземпляр `ControlHost` класса. Передайте высоту и ширину границы элемента, содержащего элемент управления (`ControlHostElement`) для `ControlHost` конструктор. Это позволит гарантировать, что ListBox имеет правильный размер. Затем разместить элемент управления на странице путем назначения `ControlHost` объект <xref:System.Windows.Controls.Decorator.Child%2A> свойство узла <xref:System.Windows.Controls.Border>.  
  
 В образце задается обработчик <xref:System.Windows.Interop.HwndHost.MessageHook> событие `ControlHost` для получения сообщений из элемента управления. Это событие вызывается для каждого сообщения, отправляемого в главное окно. В данном случае это сообщения, отправленные в окно, которое служит оболочкой текущего элемента управления ListBox, включая уведомления от элемента управления. В этом примере вызывается метод SendMessage, чтобы получать информацию от элемента управления и менять его содержимое. Подробные сведения о том, как страница обменивается данными с элементом управления, рассматриваются в следующем разделе.  
  
> [!NOTE]
>  Обратите внимание, что имеются два объявления PInvoke для SendMessage. Это необходимо, так как одна использует `wParam` параметр для передачи строки, а другой используется для передачи целого числа. Необходимо отдельно объявить каждую сигнатуру, чтобы обеспечить правильный маршалинг данных.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>Обмен данными между элементом управления и страницей  
 Управление элементом управления путем отправки ему сообщений Windows. Элемент управления уведомляет вас, когда пользователь взаимодействует с ним, отправляя уведомления в главное окно. [Размещения элемента управления ListBox Win32 в WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) пример включает пользовательский Интерфейс, который предоставляет несколько примеров того, как это работает:  
  
-   Добавить элемент в список  
  
-   Удалить выбранный элемент из списка  
  
-   Отобразить текст выбранного в настоящее время элемента  
  
-   Отобразить число элементов в списке  
  
 Пользователь может также выбрать элемент в поле со списком, щелкнув его, так же, как и для обычных приложений Win32. Отображаемые данные обновляются каждый раз, когда пользователь меняет состояние списка, выбирая, добавляя или изменяя документы.  
  
 Чтобы добавить элементы, отправьте списку [ `LB_ADDSTRING` сообщение](https://msdn.microsoft.com/library/windows/desktop/bb775181(v=vs.85).aspx). Чтобы удалить элементы, отправлять [ `LB_GETCURSEL` ](https://msdn.microsoft.com/library/windows/desktop/bb775197(v=vs.85).aspx) необходимо получить индекс текущего выделенного фрагмента и затем [ `LB_DELETESTRING` ](https://msdn.microsoft.com/library/windows/desktop/bb775183(v=vs.85).aspx) для удаления элемента. Образец также отправляет [ `LB_GETCOUNT` ](https://msdn.microsoft.com/library/windows/desktop/bb775195(v=vs.85).aspx), а возвращенное значение используется для обновления экрана, показывающий количество элементов. Оба эти экземпляры [ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx) использовать одно из объявлений PInvoke, рассмотренных в предыдущем подразделе.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Когда пользователь выбирает элемент или изменяет свой выбор, элемент управления уведомляет главное окно путем отправки их [ `WM_COMMAND` сообщение](https://msdn.microsoft.com/library/windows/desktop/ms647591(v=vs.85).aspx), что вызывает <xref:System.Windows.Interop.HwndHost.MessageHook> событий для страницы. Обработчик получает те же сведения, что и процедура главного окна в главном окне. Он также передает ссылку на логическое значение, `handled`. Задать `handled` для `true` , чтобы указать, что сообщение было обработано и дальнейшая обработка не требуется.  
  
 [`WM_COMMAND`](https://msdn.microsoft.com/library/windows/desktop/ms647591(v=vs.85).aspx) отправляется по ряду причин, поэтому необходимо проверить идентификатор уведомления, чтобы определить, является ли событие, которое вы хотите обработать. Идентификатор содержится в старшем слове `wParam` параметра. Образец использует побитовые операторы для получения идентификатора. Если пользователь сделать выбор или изменил его, Идентификатором будет [ `LBN_SELCHANGE` ](https://msdn.microsoft.com/library/windows/desktop/bb775161(v=vs.85).aspx).  
  
 При [ `LBN_SELCHANGE` ](https://msdn.microsoft.com/library/windows/desktop/bb775161(v=vs.85).aspx) будет получено, образец получает индекс выбранного элемента путем отправки элементу управления [ `LB_GETCURSEL` сообщение](https://msdn.microsoft.com/library/windows/desktop/bb775197(v=vs.85).aspx). Чтобы получить текст, сначала необходимо создать <xref:System.Text.StringBuilder>. Затем следует отправить управления [ `LB_GETTEXT` сообщение](https://msdn.microsoft.com/library/windows/desktop/bb761313(v=vs.85).aspx). Передать пустые <xref:System.Text.StringBuilder> объекта в виде `wParam` параметра. Когда [ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx) возвращает, <xref:System.Text.StringBuilder> будет содержать текст выбранного элемента. Такое использование [ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx) требуется еще один объявление PInvoke.  
  
 Задайте `handled` для `true` для указания, что сообщение было обработано.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Interop.HwndHost>  
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Пошаговое руководство. Создание первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)
