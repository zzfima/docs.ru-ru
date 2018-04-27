---
title: Пошаговое руководство. Размещение элемента управления Win32 в WPF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ab80f39a15952bee8296166ea19a78498c3c1b23
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>Пошаговое руководство. Размещение элемента управления Win32 в WPF
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Тем не менее, если имеются существенные преимущества в [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] код, он может быть более эффективным будет повторное использование по крайней мере часть этого кода в ваш [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения, а не переписывать его заново. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет простой механизм для размещения [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы.  
  
 В этом разделе рассматриваются приложения, [размещения элемента управления ListBox Win32 в образце WPF](http://go.microsoft.com/fwlink/?LinkID=159998), что узлы [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] списка. Эта общая процедура может расширяться для размещения любого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна.  
  
  
<a name="requirements"></a>   
## <a name="requirements"></a>Требования  
 В этом разделе предполагается Знакомство с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] программирования. Основные сведения о [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] программирования, в разделе [Приступая к работе](../../../../docs/framework/wpf/getting-started/index.md). Основные сведения о [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] программирования, вы должны ссылаться на любые многочисленные книги по вопросам, в частности *программирования Windows* , Чарльз Петцольд.  
  
 Пример, используемый в этом разделе реализована на C#, делает использование [!INCLUDE[TLA#tla_pinvoke](../../../../includes/tlasharptla-pinvoke-md.md)] для доступа к [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]. Знакомство с [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] является полезным, но не необходимым.  
  
> [!NOTE]
>  Этот учебник включает ряд примеров кода из связанного примера. Однако для удобства чтения он не содержит полный пример кода. Можно получить или просмотреть полный исходный код из [размещения элемента управления ListBox Win32 в образце WPF](http://go.microsoft.com/fwlink/?LinkID=159998).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Основная процедура  
 В этом разделе описаны основные процедура по размещению [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы. В остальных разделах подробно описывается каждый шаг.  
  
 Основная процедура размещения  
  
1.  Реализуйте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы для размещения окна. Один из способов — создание <xref:System.Windows.Controls.Border> элемент, чтобы зарезервировать раздел страницы для размещаемого окна.  
  
2.  Реализация класса для размещения элемента управления, который наследует от <xref:System.Windows.Interop.HwndHost>.  
  
3.  В этом классе переопределите <xref:System.Windows.Interop.HwndHost> член класса <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  
  
4.  Создайте размещаемое окно как дочерний элемент окна, содержащего [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы. Хотя в традиционном [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] программирование не требуется явно использовать, размещающая страница представляет собой окно с дескриптор (HWND). Появляется страница HWND через `hwndParent` параметр <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> метода. Размещаемое окно необходимо создать в качестве дочернего объекта этого окна HWND.  
  
5.  Создав главное окно, верните HWND размещаемого окна. Если вы хотите разместить один или несколько [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] элементов управления, обычно создайте главное окно как дочерний элемент HWND и дочерние элементы управления, главного окна. Размещение элементов управления в главном окне предоставляет простой способ вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы для получения уведомлений от элементов управления, которой решаются некоторые [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проблемы, связанные с передачей уведомлений через границу HWND.  
  
6.  Обрабатывайте некоторые сообщения, которые отправляются в главное окно, например уведомления от дочерних элементов управления. Это можно сделать двумя способами.  
  
    -   Если вы предпочитаете обработку сообщений в размещающем классе, переопределите <xref:System.Windows.Interop.HwndHost.WndProc%2A> метод <xref:System.Windows.Interop.HwndHost> класса.  
  
    -   Если вы предпочитаете [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обрабатывают сообщения, обрабатывать <xref:System.Windows.Interop.HwndHost> класса <xref:System.Windows.Interop.HwndHost.MessageHook> события в фоновом коде. Это событие возникает для каждого сообщения, получаемого размещаемым окном. Если выбран этот параметр, необходимо переопределить <xref:System.Windows.Interop.HwndHost.WndProc%2A>, но достаточно минимальную реализацию.  
  
7.  Переопределить <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> и <xref:System.Windows.Interop.HwndHost.WndProc%2A> методы <xref:System.Windows.Interop.HwndHost>. Необходимо переопределить эти методы, выполняющие <xref:System.Windows.Interop.HwndHost> контракт, но может потребоваться указать минимальную реализацию.  
  
8.  В файле кода, создайте экземпляр класса, размещающего элементы управления и сделайте его дочерним элементом <xref:System.Windows.Controls.Border> элемент, предназначенный для размещения окна.  
  
9. Обмениваться данными с размещенным окном путем отправки их [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] сообщения и сообщения обработки из его дочерних окон, таких как уведомления, отправленные элементами управления.  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>Реализация макета страницы  
 Макет для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы, на котором размещается элемент управления ListBox состоит из двух областей. В левой части страницы размещены несколько [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления, обеспечивающих [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] , позволяющий управлять [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] элемента управления. В правом верхнем углу страницы имеется квадратная область для размещенного элемента управления ListBox.  
  
 Код для реализации этого макета довольно проста. Корневой элемент — <xref:System.Windows.Controls.DockPanel> , имеющий два дочерних элемента. Во-первых, <xref:System.Windows.Controls.Border> элемент, на котором размещается элемент управления ListBox. Он занимает квадрат размером 200 x 200 в верхнем правом углу страницы. Во-вторых, <xref:System.Windows.Controls.StackPanel> элемент, который содержит набор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления, отображающих сведения и позволяют работать с элементом управления ListBox, задав предоставленных свойств взаимодействия. Для каждого из элементов, которые являются потомками <xref:System.Windows.Controls.StackPanel>, справочные материалы по различным элементам, используемым для детализации на эти элементы являются и что они делают, перечислены в приведенном ниже примере кода, но не будут описаны здесь (basic модели взаимодействия не требуются, они предоставлены для добавления интерактивности в пример).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Реализация размещения элемента управления Microsoft Win32 в классе  
 Ядром этого образца является класс, который фактически размещает в себе элемент управления, ControlHost.cs. Он наследуется от <xref:System.Windows.Interop.HwndHost>. Конструктор принимает два параметра, высоту и ширину, которые соответствуют высоту и ширину <xref:System.Windows.Controls.Border> элемент, на котором размещается элемент управления ListBox. Эти значения используются позднее, чтобы убедиться, что размер элемента управления соответствует <xref:System.Windows.Controls.Border> элемента.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Кроме того, имеется набор констант. Эти константы в основном берутся из Winuser.h и позволяют использовать обычные имена при вызове [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] функции.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Переопределение класса BuildWindowCore для создания окна Microsoft Win32  
 Переопределите этот метод для создания [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окно, в котором будут размещаться на странице и создайте связь между окном и страницы. Поскольку в этом примере также показано размещение элемента управления ListBox, создаются два окна. Первый — это окно, фактически размещенное на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы. Элемент управления ListBox создается в качестве дочернего элемента этого окна.  
  
 Это делается для того, чтобы упростить получение уведомлений от элемента управления. <xref:System.Windows.Interop.HwndHost> Позволяет обрабатывать сообщения, отправляемые в окно, на котором он размещен. При размещении [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] управления напрямую, получать сообщения, отправленные во внутреннем цикле сообщений элемента управления. Можно отображать элемент управления и отправлять ему сообщения, но не получать уведомления, которые элемент управления отправляет своему родительскому окну. Это означает, среди прочего, что нет способа обнаружения взаимодействия пользователя с элементом управления. Вместо этого следует создать главное окно и сделать элемент управления дочерним элементом этого окна. Это позволит обрабатывать сообщения для главного окна, включая уведомления, отправляемые элементом управления. Для удобства, поскольку главное окно — это всего лишь программа-оболочка для элемента управления, мы будем называть этот пакет "элементом управления ListBox".  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>Создание главного окна и элемента управления ListBox  
 Можно использовать [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] для создания главного окна для элемента управления путем создания и регистрации класса окна и т. д. Однако гораздо проще создать окно с помощью готового "статического" класса окон. Это позволит реализовать в окне процедуру, необходимую для получения уведомлений из элемента управления, и требует минимальной работы с кодом.  
  
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
>  Обратите внимание, что имеются два [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] объявления для SendMessage. Это необходимо, так как одна использует `wParam` параметр для передачи строки, а другой используется для передачи целого числа. Необходимо отдельно объявить каждую сигнатуру, чтобы обеспечить правильный маршалинг данных.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>Обмен данными между элементом управления и страницей  
 Управление элементом управления путем отправки их [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)] сообщений. Элемент управления уведомляет вас, когда пользователь взаимодействует с ним, отправляя уведомления в главное окно. [Размещения элемента управления ListBox Win32 в образце WPF](http://go.microsoft.com/fwlink/?LinkID=159998) пример включает пользовательский Интерфейс, который предоставляет несколько примеров того, как это работает:  
  
-   Добавить элемент в список  
  
-   Удалить выбранный элемент из списка  
  
-   Отобразить текст выбранного в настоящее время элемента  
  
-   Отобразить число элементов в списке  
  
 Пользователь может также выбрать элемент в поле со списком, щелкнув его, так же, как для обычного [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложения. Отображаемые данные обновляются каждый раз, когда пользователь меняет состояние списка, выбирая, добавляя или изменяя документы.  
  
 Чтобы добавить элементы, отправьте списку сообщение LB_ADDSTRING. Чтобы удалить элементы, отправьте сообщение LB_GETCURSEL, чтобы получить индекс текущего выделения, а затем отправьте сообщение LB_DELETESTRING, чтобы удалить элемент. В образце также отправляется сообщение LB_GETCOUNT и используется возвращаемое значение для обновления отображаемого числа элементов. Обоих экземплярах SendMessage используйте один из [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] объявления, рассмотренных в предыдущем подразделе.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Когда пользователь выбирает элемент или изменяет свой выбор, элемент управления уведомляет главное окно путем отправки ему сообщения WM_COMMAND, которое вызывает <xref:System.Windows.Interop.HwndHost.MessageHook> событий для страницы. Обработчик получает те же сведения, что и процедура главного окна в главном окне. Он также передает ссылку на логическое значение, `handled`. Задать `handled` для `true` , чтобы указать, что сообщение было обработано и дальнейшая обработка не требуется.  
  
 Сообщение WM_COMMAND отправляется по нескольким причинам, поэтому следует проанализировать идентификатор уведомления, чтобы понять, то ли это событие, которое вам необходимо обработать. Идентификатор содержится в старшем слове `wParam` параметра. Поскольку [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] does нет макроса HIWORD, в образце используются битовые операторы для получения идентификатора. Если пользователь сделал выбор или изменил его, идентификатор изменится на LBN_SELCHANGE.  
  
 При получении LBN_SELCHANGE пример кода также получает индекс выбранного элемента, отправляя элементу управления сообщение LB_GETCURSEL. Чтобы получить текст, сначала необходимо создать <xref:System.Text.StringBuilder>. Затем элементу управления отправляется сообщение LB_GETTEXT. Передать пустые <xref:System.Text.StringBuilder> объекта в виде `wParam` параметра. После возвращения SendMessage, <xref:System.Text.StringBuilder> будет содержать текст выбранного элемента. Такое использование SendMessage еще требуется другой [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] объявления.  
  
 Задайте `handled` для `true` для указания, что сообщение было обработано.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Interop.HwndHost>  
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Пошаговое руководство. Создание первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)
