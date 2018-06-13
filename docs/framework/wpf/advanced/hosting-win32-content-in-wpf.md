---
title: Размещение содержимого Win32 в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: beb7d5e6e1f934b89bb7516eb7e9bbbaad696238
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547359"
---
# <a name="hosting-win32-content-in-wpf"></a>Размещение содержимого Win32 в WPF
## <a name="prerequisites"></a>Предварительные требования  
 В разделе [WPF и взаимодействие Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Пошаговое руководство по Win32 внутри Windows Presentation Framework (HwndHost)  
 Для повторного использования [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] содержимое внутри [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения, используют <xref:System.Windows.Interop.HwndHost>, являющийся элементом управления, который делает HWND выглядеть как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого.  Как <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> проста в использовании: являются производными от <xref:System.Windows.Interop.HwndHost> и реализовать `BuildWindowCore` и `DestroyWindowCore` методы, затем экземпляр вашего <xref:System.Windows.Interop.HwndHost> производного класса и разместите его внутри вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение.  
  
 Если ваш [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] логику уже упакован как элемент управления, то ваше устройство `BuildWindowCore` реализацию больше, чем вызов `CreateWindow`.  Например, чтобы создать [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] управления LISTBOX в [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:  
  
```  
virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {  
    HWND handle = CreateWindowEx(0, L"LISTBOX",   
    L"this is a Win32 listbox",  
    WS_CHILD | WS_VISIBLE | LBS_NOTIFY  
    | WS_VSCROLL | WS_BORDER,  
    0, 0, // x, y  
    30, 70, // height, width  
    (HWND) hwndParent.Handle.ToPointer(), // parent hwnd  
    0, // hmenu  
    0, // hinstance  
    0); // lparam  
  
    return HandleRef(this, IntPtr(handle));  
}  
  
virtual void DestroyWindowCore(HandleRef hwnd) override {  
    // HwndHost will dispose the hwnd for us  
}  
```  
  
 Однако предположим, что [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] кода не так автономно? Если Да, можно создать [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] диалоговое окно и внедрить его содержимое в большее [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения.  В этом примере это в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] и [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], несмотря на то, что можно сделать на другом языке или из командной строки.  
  
 Начать с простого диалога, который компилируется в [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] проекта.  
  
 Теперь необходимо реализовать диалоговое окно в большее [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения:  
  
-   Скомпилируйте [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] как управляемый (`/clr`)  
  
-   Превращение диалога в элемент управления  
  
-   Определите производный класс от <xref:System.Windows.Interop.HwndHost> с `BuildWindowCore` и `DestroyWindowCore` методов  
  
-   Переопределить `TranslateAccelerator` метод для обработки ключей диалоговое окно  
  
-   Переопределить `TabInto` метод для поддержки переходов  
  
-   Переопределить `OnMnemonic` метод для поддержки назначенных клавиш  
  
-   Создать экземпляр <xref:System.Windows.Interop.HwndHost> подкласс и поместить его в правом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемент  
  
### <a name="turn-the-dialog-into-a-control"></a>Превращение диалога в элемент управления  
 Диалоговое окно можно превратить в дочерний HWND, с помощью стилей WS_CHILD и DS_CONTROL.  Перейдите в файл ресурсов (.rc), где определено диалоговое окно и найдите начало определения диалогового окна:  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 Измените второй строки, чтобы:  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 Это действие не полностью его в элемент управления самодостаточным; по-прежнему необходимо вызвать `IsDialogMessage()` , [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] может обрабатывать определенные сообщения, но изменение элемента управления предоставляет простой и понятный способ размещения этих элементов управления внутри другого HWND.  
  
## <a name="subclass-hwndhost"></a>Подкласс HwndHost  
 Импортируйте следующие пространства имен:  
  
```  
namespace ManagedCpp  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Input;  
    using namespace System::Windows::Media;  
    using namespace System::Runtime::InteropServices;  
```  
  
 Затем создайте производный класс <xref:System.Windows.Interop.HwndHost> и Переопределите `BuildWindowCore` и `DestroyWindowCore` методов:  
  
```  
public ref class MyHwndHost : public HwndHost, IKeyboardInputSink {  
    private:  
        HWND dialog;  
  
    protected:   
        virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {  
            InitializeGlobals();   
            dialog = CreateDialog(hInstance,   
                MAKEINTRESOURCE(IDD_DIALOG1),   
                (HWND) hwndParent.Handle.ToPointer(),  
                (DLGPROC) About);   
            return HandleRef(this, IntPtr(dialog));  
        }  
  
        virtual void DestroyWindowCore(HandleRef hwnd) override {  
            // hwnd will be disposed for us  
        }  
```  
  
 Здесь используется `CreateDialog` Создание диалогового окна, которое на самом деле элемент управления.  Так как это один из первых методов, вызванных внутри [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], нужно также сделать некоторые стандартные [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] инициализации с помощью вызова функции, будут определены позже, вызывается `InitializeGlobals()`:  
  
```  
bool initialized = false;  
    void InitializeGlobals() {  
        if (initialized) return;  
        initialized = true;  
  
        // TODO: Place code here.  
        MSG msg;  
        HACCEL hAccelTable;  
  
        // Initialize global strings  
        LoadString(hInstance, IDS_APP_TITLE, szTitle, MAX_LOADSTRING);  
        LoadString(hInstance, IDC_TYPICALWIN32DIALOG, szWindowClass, MAX_LOADSTRING);  
        MyRegisterClass(hInstance);  
```  
  
### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>Переопределение метода TranslateAccelerator метод для обработки ключей диалоговое окно  
 При запуске этого образца теперь, получаемому управления диалогового окна, который отображается, но будет игнорировать всю обработку, которая делает клавиатуры функциональной диалоговое окно диалоговым окном.  Теперь необходимо переопределить `TranslateAccelerator` реализацию (который поставляется вместе с `IKeyboardInputSink`, интерфейс, <xref:System.Windows.Interop.HwndHost> реализует).  Этот метод вызывается, когда приложение получает WM_KEYDOWN и WM_SYSKEYDOWN.  
  
```  
#undef TranslateAccelerator  
        virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
            ModifierKeys modifiers) override   
        {  
            ::MSG m = ConvertMessage(msg);  
  
            // Win32's IsDialogMessage() will handle most of our tabbing, but doesn't know   
            // what to do when it reaches the last tab stop  
            if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {  
                HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
                HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
                TraversalRequest^ request = nullptr;  
  
                if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {  
                    // this code should work, but there’s a bug with interop shift-tab in current builds                      
                    request = gcnew TraversalRequest(FocusNavigationDirection::Last);  
                }  
                else if (!GetKeyState(VK_SHIFT) && GetFocus() == lastTabStop) {  
                    request = gcnew TraversalRequest(FocusNavigationDirection::Next);  
                }  
  
                if (request != nullptr)  
                    return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);  
  
            }  
  
            // Only call IsDialogMessage for keys it will do something with.  
            if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {  
                switch (m.wParam) {  
                    case VK_TAB:  
                    case VK_LEFT:  
                    case VK_UP:  
                    case VK_RIGHT:  
                    case VK_DOWN:  
                    case VK_EXECUTE:  
                    case VK_RETURN:  
                    case VK_ESCAPE:  
                    case VK_CANCEL:  
                        IsDialogMessage(dialog, &m);  
                        // IsDialogMessage should be called ProcessDialogMessage --  
                        // it processes messages without ever really telling you  
                        // if it handled a specific message or not  
                        return true;  
                }  
            }  
  
            return false; // not a key we handled  
        }  
```  
  
 Это большой объем кода в одном фрагменте, поэтому он может использовать более подробные пояснения.  Во-первых, код, использующий [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] и [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] макросов, вы должны знать, что уже макрос с именем `TranslateAccelerator`, который определен в winuser.h:  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 Поэтому убедитесь, что определение `TranslateAccelerator` метода и не `TranslateAcceleratorW` метод.  
  
 Таким же образом есть неуправляемый код winuser.h MSG и управляемая `Microsoft::Win32::MSG` структуры.  Чтобы устранить неоднозначность между ними с помощью [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` оператор.  
  
```  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 Оба msg имеют те же данные, но иногда проще работать с неуправляемым определением, поэтому в этом образце можно определить подпрограмма очевидным преобразования:  
  
```  
::MSG ConvertMessage(System::Windows::Interop::MSG% msg) {  
    ::MSG m;  
    m.hwnd = (HWND) msg.hwnd.ToPointer();  
    m.lParam = (LPARAM) msg.lParam.ToPointer();  
    m.message = msg.message;  
    m.wParam = (WPARAM) msg.wParam.ToPointer();  
  
    m.time = msg.time;  
  
    POINT pt;  
    pt.x = msg.pt_x;  
    pt.y = msg.pt_y;  
    m.pt = pt;  
  
    return m;  
}  
```  
  
 К `TranslateAccelerator`.  Основным принципом является вызов [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] функция `IsDialogMessage` делать максимально возможный объем работы, возможно, но `IsDialogMessage` не имеет доступа к чему-либо за пределами диалогового окна. Во время выполнения вне окна, заставляя за последним элементом управления в нашем диалогового окна необходимо задать фокус для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часть путем вызова `IKeyboardInputSite::OnNoMoreStops`.  
  
```  
// Win32's IsDialogMessage() will handle most of the tabbing, but doesn't know   
// what to do when it reaches the last tab stop  
if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {  
    HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
    HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
    TraversalRequest^ request = nullptr;  
  
    if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {  
        request = gcnew TraversalRequest(FocusNavigationDirection::Last);  
    }  
    else if (!GetKeyState(VK_SHIFT) && GetFocus() ==  lastTabStop) { {  
        request = gcnew TraversalRequest(FocusNavigationDirection::Next);  
    }  
  
    if (request != nullptr)  
        return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);  
}  
```  
  
 Теперь вызовите `IsDialogMessage`.  Но одно обязанности `TranslateAccelerator` указывает метод [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ли обрабатываться нажатие клавиши или нет. Если вы не обрабатывает его, событие ввода может Туннелировать и поднимаются по остальной части приложения. Здесь будут предоставлены особенности обработки клавиатуры и природа архитектуры ввода в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. К сожалению `IsDialogMessage` не возвращает каким-либо образом обрабатывает ли он конкретное нажатие клавиши.  Более того, он вызывает `DispatchMessage()` на нажатия клавиш, он не должен обрабатывать!  Поэтому нужно выполнить реконструирование `IsDialogMessage`и вызывать ее только для ключей, вы знаете, что он будет обрабатывать:  
  
```  
// Only call IsDialogMessage for keys it will do something with.  
if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {  
    switch (m.wParam) {  
        case VK_TAB:  
        case VK_LEFT:  
        case VK_UP:  
        case VK_RIGHT:  
        case VK_DOWN:  
        case VK_EXECUTE:  
        case VK_RETURN:  
        case VK_ESCAPE:  
        case VK_CANCEL:  
            IsDialogMessage(dialog, &m);  
            // IsDialogMessage should be called ProcessDialogMessage --  
            // it processes messages without ever really telling you  
            // if it handled a specific message or not  
            return true;  
    }  
```  
  
### <a name="override-tabinto-method-to-support-tabbing"></a>Переопределение метода TabInto для поддержки переходов  
 Теперь, когда вы применили `TranslateAccelerator`, пользователь может совершать переходы внутри диалогового окна поле и перехода от него в большее [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения.  Однако пользователь не может перейти обратно в диалоговом окне.  Чтобы разрешить это, переопределите `TabInto`:  
  
```  
public:   
    virtual bool TabInto(TraversalRequest^ request) override {  
        if (request->FocusNavigationDirection == FocusNavigationDirection::Last) {  
            HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
            SetFocus(lastTabStop);  
        }  
        else {  
            HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
            SetFocus(firstTabStop);  
        }  
        return true;  
    }  
```  
  
 `TraversalRequest` Параметр указывает, является ли действие вкладки tab или shift tab.  
  
### <a name="override-onmnemonic-method-to-support-mnemonics"></a>Переопределение метода OnMnemonic для поддержки назначенных клавиш  
 Обработка событий клавиатуры практически завершена, но имеется один аспекте — назначенные клавиши не работают.  Если пользователь нажимает сочетание клавиш alt-F, фокус не переходит в «имя:» поле ввода. Таким образом, необходимо переопределить `OnMnemonic` метод:  
  
```  
virtual bool OnMnemonic(System::Windows::Interop::MSG% msg, ModifierKeys modifiers) override {  
    ::MSG m = ConvertMessage(msg);  
  
    // If it's one of our mnemonics, set focus to the appropriate hwnd  
    if (msg.message == WM_SYSCHAR && GetKeyState(VK_MENU /*alt*/)) {  
        int dialogitem = 9999;  
        switch (m.wParam) {  
            case 's': dialogitem = IDOK; break;  
            case 'c': dialogitem = IDCANCEL; break;  
            case 'f': dialogitem = IDC_EDIT1; break;  
            case 'l': dialogitem = IDC_EDIT2; break;  
            case 'p': dialogitem = IDC_EDIT3; break;  
            case 'a': dialogitem = IDC_EDIT4; break;  
            case 'i': dialogitem = IDC_EDIT5; break;  
            case 't': dialogitem = IDC_EDIT6; break;  
            case 'z': dialogitem = IDC_EDIT7; break;  
        }  
        if (dialogitem != 9999) {  
            HWND hwnd = GetDlgItem(dialog, dialogitem);  
            SetFocus(hwnd);  
            return true;  
        }  
    }  
    return false; // key unhandled  
};  
```  
  
 Почему бы не вызвать `IsDialogMessage` здесь?  У вас есть такая же проблема — необходимо иметь возможность информирования [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] кода, обработал ли код нажатие клавиши или нет, и `IsDialogMessage` сделать это невозможно.  Имеется также вторая проблема, поскольку `IsDialogMessage` отказывается обрабатывать мнемоническую, если фокус HWND не находится внутри диалоговым окном.  
  
### <a name="instantiate-the-hwndhost-derived-class"></a>Создать экземпляр производного класса HwndHost  
 Наконец, теперь, когда вся поддержка раздел и вкладку на месте, можно поместить в <xref:System.Windows.Interop.HwndHost> в большее [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения.  Если основное приложение написано на [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], является самым простым способом поместить его в нужном месте, оставьте пустым <xref:System.Windows.Controls.Border> которой вы хотите поместить элемент <xref:System.Windows.Interop.HwndHost>.  Здесь можно создать <xref:System.Windows.Controls.Border> с именем `insertHwndHostHere`:  
  
```  
<Window x:Class="WPFApplication1.Window1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    Title="Windows Presentation Framework Application"  
    Loaded="Window1_Loaded"  
    >  
    <StackPanel>  
        <Button Content="WPF button"/>  
        <Border Name="insertHwndHostHere" Height="200" Width="500"/>  
        <Button Content="WPF button"/>  
    </StackPanel>  
</Window>  
```  
  
 Затем все, что остается лишь найти правильное место в коде для создания экземпляра <xref:System.Windows.Interop.HwndHost> и подключите его к <xref:System.Windows.Controls.Border>.  В этом примере он помещается внутри конструктора для <xref:System.Windows.Window> производного класса:  
  
```  
public partial class Window1 : Window {  
    public Window1() {  
    }  
  
    void Window1_Loaded(object sender, RoutedEventArgs e) {  
        HwndHost host = new ManagedCpp.MyHwndHost();  
        insertHwndHostHere.Child = host;  
    }  
}  
```  
  
 Которое позволяет:  
  
 ![Снимок экрана приложения WPF](../../../../docs/framework/wpf/advanced/media/interoparch09.PNG "InteropArch09")  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
