---
title: Проведение управления Win32 в WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 5185e60640c652b79bd105db54830ac3acc57129
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186739"
---
# <a name="walkthrough-host-a-win32-control-in-wpf"></a>Прохождение: Хозяин Win32 Контроль в WPF
Фонд презентации Windows (WPF) предоставляет богатую среду для создания приложений. Однако, если у вас есть значительные инвестиции в код Win32, может быть более эффективным повторно использовать хотя бы часть этого кода в приложении WPF, а не переписывать его полностью. WPF предоставляет простой механизм размещения окна Win32 на странице WPF.  
  
 Эта тема прогулки вас через приложение, [Хостинг Win32 ListBox управления в WPF образец](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control), который хостов Win32 список поле управления. Эта общая процедура может быть распространена на хостинг любого окна Win32.  

<a name="requirements"></a>
## <a name="requirements"></a>Требования  
 Эта тема предполагает базовое знакомство с программированием WPF и Windows API. Для базового введения в программирование WPF [см.](../getting-started/index.md) Для введения в программирование API Windows, см. *Programming Windows*  
  
 Поскольку образец, сопровождающий эту тему, реализован в СЗ, он использует службы вызова платформы (PInvoke) для доступа к API Windows. Некоторое знакомство с PInvoke полезно, но не является существенным.  
  
> [!NOTE]
> Этот учебник включает ряд примеров кода из связанного примера. Однако для удобства чтения он не содержит полный пример кода. Вы можете получить или просмотреть полный код от [хостинга Win32 ListBox Control в образце WPF.](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)  
  
<a name="basic_procedure"></a>
## <a name="the-basic-procedure"></a>Основная процедура  
 В этом разделе излагается основная процедура размещения окна Win32 на странице WPF. В остальных разделах подробно описывается каждый шаг.  
  
 Основная процедура размещения  
  
1. Реализация страницы WPF для размещения окна. Один из методов <xref:System.Windows.Controls.Border> заключается в создании элемента для резервирования раздела страницы для размещенного окна.  
  
2. Реализация класса для размещения элемента <xref:System.Windows.Interop.HwndHost>управления, наследуетемого от .  
  
3. В этом классе переопределить <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>участника класса.  
  
4. Создайте размещенное окно в качестве ребенка окна, содержащего страницу WPF. Хотя обычное программирование WPF не обязательно использовать его, страница хостинга представляет собой окно с ручкой (HWND). Вы получаете страницу HWND по `hwndParent` параметру метода. <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> Размещаемое окно необходимо создать в качестве дочернего объекта этого окна HWND.  
  
5. Создав главное окно, верните HWND размещаемого окна. Если вы хотите разместить один или несколько элементов управления Win32, вы обычно создаете окно хоста в качестве ребенка HWND и создаете элементы управления в этом окне хоста. Упаковка элементов управления в окне хоста обеспечивает простой способ получения уведомлений от элементов управления, которые касались некоторых конкретных проблем Win32 с уведомлениями через границу HWND.  
  
6. Обрабатывайте некоторые сообщения, которые отправляются в главное окно, например уведомления от дочерних элементов управления. Это можно сделать двумя способами.  
  
    - Если вы предпочитаете <xref:System.Windows.Interop.HwndHost.WndProc%2A> обрабатывать сообщения в классе хостинга, переопределить метод <xref:System.Windows.Interop.HwndHost> класса.  
  
    - Если вы предпочитаете, чтобы WPF обрабатывал сообщения, обрабатывают событие <xref:System.Windows.Interop.HwndHost> класса <xref:System.Windows.Interop.HwndHost.MessageHook> в коде за ним. Это событие возникает для каждого сообщения, получаемого размещаемым окном. Если вы выбираете этот вариант, <xref:System.Windows.Interop.HwndHost.WndProc%2A>вы все равно должны переопределить, но вам нужна только минимальная реализация.  
  
7. Переопределить <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> и <xref:System.Windows.Interop.HwndHost.WndProc%2A> методы <xref:System.Windows.Interop.HwndHost>. Вы должны переопределить эти методы, чтобы удовлетворить <xref:System.Windows.Interop.HwndHost> контракт, но вам может потребоваться только обеспечить минимальную реализацию.  
  
8. В файле с кодом создайте экземпляр класса хостинга управления <xref:System.Windows.Controls.Border> и сделайте его ребенком элемента, предназначенного для размещения окна.  
  
9. Общайтесь с размещенным окном, отправляя ему сообщения Microsoft Windows и обрабатывая сообщения из своих детских окон, такие как уведомления, отправленные элементами управления.  
  
<a name="page_layout"></a>
## <a name="implement-the-page-layout"></a>Реализация макета страницы  
 Макет для страницы WPF, на котором размещает сяврей ListBox, состоит из двух регионов. В левой части страницы находится несколько [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] элементов управления WPF, которые обеспечивают, что позволяет манипулировать управлением Win32. В правом верхнем углу страницы имеется квадратная область для размещенного элемента управления ListBox.  
  
 Код для реализации этого макета довольно прост. Корневой элемент <xref:System.Windows.Controls.DockPanel> имеет два элемента ребенка. Первый элемент, <xref:System.Windows.Controls.Border> который размещает контроль ListBox. Он занимает квадрат размером 200 x 200 в верхнем правом углу страницы. Второй <xref:System.Windows.Controls.StackPanel> элемент, который содержит набор элементов управления WPF, которые отображают информацию и позволяют манипулировать Control ListBox, установив открытые свойства интероперации. Для каждого из <xref:System.Windows.Controls.StackPanel>элементов, которые являются детьми, см. справочный материал для различных элементов, используемых для получения подробной информации о том, что эти элементы или что они делают, они перечислены в примере кода ниже, но не будут объяснены здесь (основная модель интероперации не требует любого из них, они предоставляются, чтобы добавить некоторую интерактивность в образец).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Реализация размещения элемента управления Microsoft Win32 в классе  
 Ядром этого образца является класс, который фактически размещает в себе элемент управления, ControlHost.cs. Он наследует от <xref:System.Windows.Interop.HwndHost>. Конструктор принимает два параметра, высоту и ширину, которые <xref:System.Windows.Controls.Border> соответствуют высоте и ширине элемента, который размещает элемент ListBox. Эти значения используются позже для обеспечения соответствия размера элемента элементу. <xref:System.Windows.Controls.Border>  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Кроме того, имеется набор констант. Эти константы в значительной степени взяты из Winuser.h, и позволяют использовать обычные имена при вызове функций Win32.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Переопределение класса BuildWindowCore для создания окна Microsoft Win32  
 Вы переопределить этот метод, чтобы создать окно Win32, которое будет размещено на странице, и сделать соединение между окном и страницей. Поскольку в этом примере также показано размещение элемента управления ListBox, создаются два окна. Во-первых, это окно, которое фактически размещено на странице WPF. Элемент управления ListBox создается в качестве дочернего элемента этого окна.  
  
 Это делается для того, чтобы упростить получение уведомлений от элемента управления. Класс <xref:System.Windows.Interop.HwndHost> позволяет обрабатывать сообщения, отправленные в окно, которое он размещает. Если вы размещаете элемент управления Win32 напрямую, вы получаете сообщения, отправленные во внутренний цикл сообщения элемента управления. Можно отображать элемент управления и отправлять ему сообщения, но не получать уведомления, которые элемент управления отправляет своему родительскому окну. Это означает, среди прочего, что нет способа обнаружения взаимодействия пользователя с элементом управления. Вместо этого следует создать главное окно и сделать элемент управления дочерним элементом этого окна. Это позволит обрабатывать сообщения для главного окна, включая уведомления, отправляемые элементом управления. Для удобства, поскольку главное окно — это всего лишь программа-оболочка для элемента управления, мы будем называть этот пакет "элементом управления ListBox".  
  
<a name="create_the_window_and_listbox"></a>
#### <a name="create-the-host-window-and-listbox-control"></a>Создание главного окна и элемента управления ListBox  
 Можно использовать PInvoke для создания окна-хозяина для управления путем создания и регистрации класса окон и так далее. Однако гораздо проще создать окно с помощью готового "статического" класса окон. Это позволит реализовать в окне процедуру, необходимую для получения уведомлений из элемента управления, и требует минимальной работы с кодом.  
  
 HWND элемента управления предоставляется через доступное только для чтения свойство, чтобы главная страница могла использовать его для отправки сообщения элементу управления.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Элемент управления ListBox создается в качестве дочернего элемента главного окна. Высота и ширина обоих окон задается с помощью значений, передаваемых конструктору (см. выше). Это гарантирует, что размер главного окна и элемента управления идентичен размеру отведенной для них области на странице.  После создания окон образец возвращает <xref:System.Runtime.InteropServices.HandleRef> объект, содержащий HWND окна хоста.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>
### <a name="implement-destroywindow-and-wndproc"></a>Реализация классов DestroyWindow и WndProc  
 В дополнение <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>к , Вы <xref:System.Windows.Interop.HwndHost.WndProc%2A> также <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> должны переопределить и методы <xref:System.Windows.Interop.HwndHost>. В этом примере сообщения для управления обрабатываются <xref:System.Windows.Interop.HwndHost.MessageHook> обработчиком, таким образом, реализация <xref:System.Windows.Interop.HwndHost.WndProc%2A> и <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> минимальна. В <xref:System.Windows.Interop.HwndHost.WndProc%2A>случае, установленный `handled` для `false` указания на то, что сообщение не было обработано и возврат 0. Ибо, <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>просто уничтожить окно.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>
## <a name="host-the-control-on-the-page"></a>Размещение элемента управления на странице  
 Чтобы разместить элемент управления на странице, сначала создайте новый экземпляр `ControlHost` класса. Передайте высоту и ширину элемента`ControlHostElement`границы, `ControlHost` содержащего элемент управления () конструктору. Это позволит гарантировать, что ListBox имеет правильный размер. Затем элемент управления размещается на `ControlHost` странице, <xref:System.Windows.Controls.Decorator.Child%2A> назначая <xref:System.Windows.Controls.Border>объект свойству узла.  
  
 Образец прикрепляет обработчика `ControlHost` к событию <xref:System.Windows.Interop.HwndHost.MessageHook> получения сообщений от элемента управления. Это событие вызывается для каждого сообщения, отправляемого в главное окно. В данном случае это сообщения, отправленные в окно, которое служит оболочкой текущего элемента управления ListBox, включая уведомления от элемента управления. В этом примере вызывается метод SendMessage, чтобы получать информацию от элемента управления и менять его содержимое. Подробные сведения о том, как страница обменивается данными с элементом управления, рассматриваются в следующем разделе.  
  
> [!NOTE]
> Обратите внимание, что для SendMessage есть две декларации PInvoke. Это необходимо, потому `wParam` что один использует параметр для прохождения строки, а другой использует его для прохождения рядов. Необходимо отдельно объявить каждую сигнатуру, чтобы обеспечить правильный маршалинг данных.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>
## <a name="implement-communication-between-the-control-and-the-page"></a>Обмен данными между элементом управления и страницей  
 Вы манипулируете управлением, отправляя ему сообщения Windows. Элемент управления уведомляет вас, когда пользователь взаимодействует с ним, отправляя уведомления в главное окно. [Хостинг Win32 ListBox Control в](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) выборке WPF включает в себя uI, который предоставляет несколько примеров того, как это работает:  
  
- Добавить элемент в список  
  
- Удалить выбранный элемент из списка  
  
- Отобразить текст выбранного в настоящее время элемента  
  
- Отобразить число элементов в списке  
  
 Пользователь также может выбрать элемент в поле списка, нажав на него, так же, как они будут для обычного приложения Win32. Отображаемые данные обновляются каждый раз, когда пользователь меняет состояние списка, выбирая, добавляя или изменяя документы.  
  
 Чтобы присвоить элементы, отправьте в поле списка [ `LB_ADDSTRING` сообщение.](/windows/desktop/Controls/lb-addstring) Чтобы удалить элементы, отправьте, [`LB_GETCURSEL`](/windows/desktop/Controls/lb-getcursel) чтобы получить [`LB_DELETESTRING`](/windows/desktop/Controls/lb-deletestring) индекс текущего выбора, а затем удалить элемент. Образец также [`LB_GETCOUNT`](/windows/desktop/Controls/lb-getcount)отправляет и использует возвращенное значение для обновления дисплея, отображая количество элементов. Оба эти примера [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) использования одной из деклараций PInvoke обсуждались в предыдущем разделе.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Когда пользователь выбирает элемент или изменяет свой выбор, элемент уведомляет окно узла, отправляя ему [ `WM_COMMAND` сообщение,](/windows/desktop/menurc/wm-command)которое поднимает <xref:System.Windows.Interop.HwndHost.MessageHook> событие для страницы. Обработчик получает те же сведения, что и процедура главного окна в главном окне. Он также передает ссылку на `handled`значение Boolean, . Вы `handled` устанавливаете, чтобы `true` указать, что вы обрабатываются сообщение и никакой дальнейшей обработки не требуется.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command)отправляется по разным причинам, поэтому необходимо изучить идентификатор уведомления, чтобы определить, является ли это событием, которым вы хотите справиться. Идентификатор содержится в `wParam` высоком слове параметра. В образце используются более битые операторы для извлечения идентификатора. Если пользователь сделал или изменил свой выбор, [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange)идентификатор будет .  
  
 При [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange) получении образец получает индекс выбранного элемента, отправив [ `LB_GETCURSEL` элемент элемента.](/windows/desktop/Controls/lb-getcursel) Чтобы получить текст, вы <xref:System.Text.StringBuilder>сначала создать . Затем вы отправляете [ `LB_GETTEXT` сообщение](/windows/desktop/Controls/lb-gettext)управления. Передайте <xref:System.Text.StringBuilder> пустой `wParam` объект в качестве параметра. При [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) возврате <xref:System.Text.StringBuilder> будет содержаться текст выбранного элемента. Такое [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) использование требует еще одной декларации PInvoke.  
  
 Наконец, `handled` `true` установите, чтобы указать, что сообщение было обработано.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Interop.HwndHost>
- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
- [Пошаговое руководство. Создание первого классического приложения WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
