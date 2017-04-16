---
title: "Размещение содержимого Win32 в WPF | Microsoft Docs"
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
  - "взаимодействие [WPF], учебники"
  - "взаимодействие [WPF], Win32"
  - "код Win32, взаимодействие с WPF"
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Размещение содержимого Win32 в WPF
## Обязательные компоненты  
 См. раздел [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## Пошаговое руководство Win32 в Windows Presentation Framework \(HwndHost\)  
 Для повторного использования содержимого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] внутри приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используйте <xref:System.Windows.Interop.HwndHost>, являющийся элементом управления, который заставляет HWND выглядеть как содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Как и <xref:System.Windows.Interop.HwndSource>, использовать <xref:System.Windows.Interop.HwndHost> очень просто: наследуйте от <xref:System.Windows.Interop.HwndHost> и реализуйте методы `BuildWindowCore` и `DestroyWindowCore`, затем создайте производный класс <xref:System.Windows.Interop.HwndHost> и разместите его внутри приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Если логика [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] уже собрана как элемент управления, тогда реализация `BuildWindowCore` окажется не только вызовом `CreateWindow`.  Например, чтобы создать элемент управления [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX в [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] понадобится следующий код:  
  
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
  
 Но что если код [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] не вполне самодостаточен?  В этом случае можно создать диалоговое окно [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и внедрить его содержимое в большее приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Это демонстрируется это на примере [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] и [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], хотя это также можно сделать на другом языке или из командной строки.  
  
 Начнем с простого диалога, который компилируется в проект [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)].  
  
 Далее, поместим диалог в большее приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   Скомпилируйте [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] как управляемый код \(`/clr`\)  
  
-   Превратите диалог в элемент управления  
  
-   Определите производный класс <xref:System.Windows.Interop.HwndHost> с методами `BuildWindowCore` и `DestroyWindowCore`  
  
-   Переопределите метод `TranslateAccelerator` для обработки клавиш диалога  
  
-   Переопределите метод `TabInto` для поддержки переходов  
  
-   Переопределите метод `OnMnemonic` для поддержки назначенных клавиш  
  
-   Создайте экземпляр подкласса <xref:System.Windows.Interop.HwndHost> и поместите его под нужным элементом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
### Превращение диалога в элемент управления  
 Диалоговое окно можно превратить в дочерний элемент HWND с помощью стилей WS\_CHILD и DS\_CONTROL.  Перейдите в файл ресурсов \(.rc\), где определено диалоговое окно, и найдите начало определения диалога:  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 Измените вторую строку на следующую:  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 Это действие не полностью собирает его в независимый элемент управления: вам по\-прежнему будет необходимо вызвать `IsDialogMessage()`, чтобы [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] мог обрабатывать определенные сообщения. В то же время изменение элемента управления не предоставляет прямого способа размещения этих элементов управления внутри другого HWND.  
  
## Подкласс HwndHost  
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
  
 Затем создайте производный класс от <xref:System.Windows.Interop.HwndHost> и переопределите методы `BuildWindowCore` и `DestroyWindowCore`:  
  
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
  
 Здесь `CreateDialog` используется для создания диалогового окна, которое на самом деле является элементом управления.  Поскольку это один из первых методов, вызванных внутри [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], необходимо также произвести стандартную инициализацию [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] путем вызова функции с именем `InitializeGlobals()`, которая будет определена позже:  
  
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
  
### Переопределение метода TranslateAccelerator для обработки клавиш диалога  
 Если запустить этот пример сейчас, результатом выполнения будет диалоговый элемент управления, который отобразится, но будет игнорировать всю клавиатурную обработку, которая делает диалоговое окно функциональным.  Теперь необходимо переопределить реализацию метода `TranslateAccelerator`, который поставляется вместе с `IKeyboardInputSink` — интерфейсом, который реализует <xref:System.Windows.Interop.HwndHost>.  Этот метод вызывается, когда приложение получает WM\_KEYDOWN и WM\_SYSKEYDOWN.  
  
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
  
 В этом примере много кода, поэтому нужны более подробные пояснения.  Во\-первых, здесь содержится код, использующий макросы [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] и [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]. Вам необходимо иметь в виду, что макрос с именем `TranslateAccelerator` уже существует и определен в WinUser.h:  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 Поэтому убедитесь в том, что определяется метод `TranslateAccelerator`, а не метод `TranslateAcceleratorW`.  
  
 Аналогичным образом здесь присутствует неуправляемый код WinUser.h MSG и управляемая структура `Microsoft::Win32::MSG`.  Чтобы устранить неоднозначность между ними, используйте оператор [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::`.  
  
```  
  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 Оба MSG имеют одинаковые данные, но иногда проще работать с неуправляемым определением. Таким образом, в этом примере можно определить обычную процедуру преобразования:  
  
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
  
 Вернемся к `TranslateAccelerator`.  Основным принципом является вызов функции `IsDialogMessage` в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Это позволяет сделать максимально возможное количество работы, не заставляя `IsDialogMessage` обращаться к объектам вне диалогового окна. Если при переходе по диалоговому окну пользователь выходит за пределы последнего элемента управления, необходимо установить фокус на часть [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] путем вызова `IKeyboardInputSite::OnNoMoreStops`.  
  
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
  
 Теперь вызовите `IsDialogMessage`.  Метода `TranslateAccelerator` как раз и предназначен для того, чтобы сообщить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], обработано ли нажатие клавиши или нет.  Если обработать его не удалось, событие ввода может пройти и передаться через оставшуюся часть приложения.  Все особенности обработки сообщений клавиатуры и природа архитектуры ввода предоставляются [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  К сожалению, `IsDialogMessage` никак не возвращает информацию о том, обрабатывает ли он конкретное нажатие клавиши.  Кроме того, он будет вызывать `DispatchMessage()` даже для тех нажатий клавиш, которые он не должен обрабатывать\!  Поэтому необходимо реконструировать `IsDialogMessage` и вызывать ее только для тех клавиш, которые заведомо будут обрабатываться.  
  
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
  
### Переопределение метода TabInto для поддержки переходов  
 Теперь, когда `TranslateAccelerator` реализован, пользователь может совершать переходы внутри окна диалога и переходить из него в большее приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Однако пользователь пока не может перейти обратно в диалоговое окно.  Чтобы разрешить это, переопределите `TabInto`:  
  
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
  
 Параметр `TraversalRequest` сообщит о том, что действие вкладки является переходом или переходом сдвига.  
  
### Переопределение метода OnMnemonic для поддержки назначенных клавиш  
 Обработка клавиатуры практически завершена, за исключением одного аспекте — назначенные клавиши не работают.  Если пользователь нажимает ALT\-F, фокус не переходит к полю ввода "Имя:".  Чтобы решить эту проблему, переопределяете метод `OnMnemonic`:  
  
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
  
 Почему бы не вызвать `IsDialogMessage`?  Возникла уже знакомая проблема — необходимо иметь возможность уведомить код [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] о том, обработал ли код нажатие клавиши или нет, а `IsDialogMessage` не может сделать этого.  Также есть другая проблема: `IsDialogMessage` отказывается обрабатывать нажатые клавиши, если фокусируемый HWND не находится внутри диалогового окна.  
  
### Создание экземпляра производного класса HWndHost  
 Теперь все клавиши и переходы работают, и объект <xref:System.Windows.Interop.HwndHost> можно поместить в большее приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Если главное приложение написано на [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], то для помещения его в нужное место проще всего оставить пустой элемент <xref:System.Windows.Controls.Border>, в том месте, куда вы хотите поместить <xref:System.Windows.Interop.HwndHost>.  На этом этапе создается <xref:System.Windows.Controls.Border> под именем `insertHwndHostHere`:  
  
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
  
 Затем, остается лишь найти правильное место в коде для создания экземпляра <xref:System.Windows.Interop.HwndHost> и соединения его с <xref:System.Windows.Controls.Border>.  В этом примере он помещается внутрь конструктора для производного класса <xref:System.Windows.Window>:  
  
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
  
 Результат выполнения показан ниже:  
  
 ![Снимок экрана приложения WPF](../../../../docs/framework/wpf/advanced/media/interoparch09.png "InteropArch09")  
  
## См. также  
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)