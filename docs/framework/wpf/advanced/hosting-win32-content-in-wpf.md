---
title: Размещение содержимого Win32 в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: 10bdeae8fe46f78e60d278fdbe93883a1c6bd356
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629880"
---
# <a name="hosting-win32-content-in-wpf"></a>Размещение содержимого Win32 в WPF

## <a name="prerequisites"></a>Предварительные требования

См. раздел [взаимодействие WPF и Win32](wpf-and-win32-interoperation.md).

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Пошаговое руководство по Win32 в Windows Presentation Framework (HwndHost)

Чтобы повторно [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] использовать содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внутри приложений, <xref:System.Windows.Interop.HwndHost>используйте, который является элементом управления, который делает HWND похожими [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на содержимое. Как <xref:System.Windows.Interop.HwndSource>, `BuildWindowCore` <xref:System.Windows.Interop.HwndHost> `DestroyWindowCore` [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Interop.HwndHost> прост в использовании: наследовать от и реализовать методы и, создать экземпляр производного класса и поместить его в <xref:System.Windows.Interop.HwndHost> приклад.

Если логика уже упакована как элемент управления, ваша `BuildWindowCore` реализация немного `CreateWindow`больше, чем вызов. [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Например, чтобы создать [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] элемент управления ListBox в: C++

```cpp
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

Но предположим, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] что код не вполне сам самодостаточный? В этом случае можно создать [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] диалоговое окно и внедрить его содержимое в более крупное [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение. В этом примере это показано [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] в C++и, хотя это также можно сделать на другом языке или в командной строке.

Начните с простого диалогового окна, которое компилируется в C++ проект DLL.

Затем Познакомьтесь с диалоговым окном [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложении большего размера:

- Компиляция библиотеки DLL как управляемой`/clr`()

- Преобразование диалогового окна в элемент управления

- Определение производного класса <xref:System.Windows.Interop.HwndHost> с помощью `BuildWindowCore` методов `DestroyWindowCore` и

- Переопределение `TranslateAccelerator` метода для работы с диалоговыми ключами

- Переопределение `TabInto` метода для поддержки перехода по клавише TAB

- Переопределение `OnMnemonic` метода для поддержки назначенных клавиш

- Создание экземпляра [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] подкласса и помещение его в правый элемент <xref:System.Windows.Interop.HwndHost>

### <a name="turn-the-dialog-into-a-control"></a>Преобразование диалогового окна в элемент управления

Диалоговое окно можно преобразовать в дочерний HWND с помощью стилей WS_CHILD и DS_CONTROL. Перейдите в файл ресурсов (. RC), в котором определено диалоговое окно, и найдите начало определения диалогового окна:

```
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

Измените вторую строку на:

```
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

Это действие не полностью упаковывается в самодостаточный элемент управления. по-прежнему необходимо вызывать `IsDialogMessage()` , [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] чтобы обрабатывать определенные сообщения, но изменение элемента управления обеспечивает простой способ размещения этих элементов управления в другом HWND.

## <a name="subclass-hwndhost"></a>Подкласс HwndHost

Импортируйте такие пространства имен:

```cpp
namespace ManagedCpp
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Input;
    using namespace System::Windows::Media;
    using namespace System::Runtime::InteropServices;
```

Затем создайте производный класс класса <xref:System.Windows.Interop.HwndHost> и `BuildWindowCore` Переопределите методы `DestroyWindowCore` и:

```cpp
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

Здесь используется `CreateDialog` для создания диалогового окна, которое на самом деле является элементом управления. Поскольку это один из первых методов, вызываемых в библиотеке DLL, необходимо также выполнить стандартную [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] инициализацию, вызвав функцию, которая будет определена `InitializeGlobals()`позже, с именем:

```cpp
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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>Переопределение метода TranslateAccelerator для работы с диалоговыми ключами

Если вы запустили этот пример, вы получите элемент управления диалогового окна, отображающий, но при этом будет игнорироваться вся обработка клавиатуры, которая делает диалоговое окно функциональным. Теперь необходимо переопределить `TranslateAccelerator` реализацию (которая поступает из `IKeyboardInputSink`интерфейса <xref:System.Windows.Interop.HwndHost> , реализующего). Этот метод вызывается, когда приложение получает WM_KEYDOWN и WM_SYSKEYDOWN.

```cpp
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

Это большой объем кода в одной части, поэтому он может использовать некоторые более подробные объяснения. Во первых, код использует C++ макросы и C++ ; необходимо иметь в виду, что уже существует макрос с именем `TranslateAccelerator`, который определен в файле WinUser. h:

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

Поэтому убедитесь, что определен `TranslateAccelerator` метод, а `TranslateAcceleratorW` не метод.

Точно так же существует и неуправляемый Winuser. h MSG, и управляемая `Microsoft::Win32::MSG` структура. Можно определить неоднозначность между двумя с C++ `::` помощью оператора.

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}

Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:

```cpp
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

Вернуться к `TranslateAccelerator`. Основным принципом является вызов [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] функции `IsDialogMessage` для выполнения максимально возможной работы, но `IsDialogMessage` не имеет доступа к каким-либо данным за пределами диалогового окна. В качестве вкладки пользователя в диалоговом окне, когда Табуляция выполняется после последнего элемента управления в нашем диалоговом окне, необходимо установить фокус на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эту часть, `IKeyboardInputSite::OnNoMoreStops`вызвав.

```cpp
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

Теперь вызовите `IsDialogMessage`. Но одной из обязанностей `TranslateAccelerator` метода [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является то, что вы обработали нажатие клавиши. Если вы не обработали его, входное событие может быть туннелем и пузырьковым через остальную часть приложения. Здесь вы узнаете о том, как работать с клавиатурой мессанже и природы входной архитектуры в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. К сожалению, не возвращает никакого способа, `IsDialogMessage` обрабатывает ли он определенное нажатие клавиши. Еще хуже, он будет вызывать `DispatchMessage()` нажатия клавиш, которые не должны обработаны!  Поэтому необходимо выполнить реконструирование `IsDialogMessage`и вызвать его только для тех ключей, которые будут обработаны:

```cpp
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

### <a name="override-tabinto-method-to-support-tabbing"></a>Переопределение метода Табинто для поддержки перехода по клавише TAB

Теперь, когда вы реализуете `TranslateAccelerator`, пользователь может переходить на вкладку внутри диалогового окна и использовать его в более [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] масштабном приложении. Но пользователь не может вернуться на вкладку в диалоговое окно. Чтобы решить эту проблему, переопределите `TabInto`:

```cpp
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

`TraversalRequest` Параметр указывает, является ли действие вкладки вкладкой TAB или Shift.

### <a name="override-onmnemonic-method-to-support-mnemonics"></a>Переопределение метода OnMnemonic для поддержки назначенных клавиш

Обработка клавиатуры почти завершена, но есть одна вещь, что не работает. Если пользователь нажмет клавишу Alt-F, фокус не будет переходить к полю "First Name:" (изменить). Поэтому Переопределите `OnMnemonic` метод:

```cpp
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

Почему это не `IsDialogMessage` вызывается?  У вас есть та же самая ошибка, что и перед--необходимо иметь возможность [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] информировать код о том, обрабатывает ли код нажатие клавиши `IsDialogMessage` или нет, и не может сделать это. Кроме того, существует вторая ошибка, так `IsDialogMessage` как отказывается обрабатывать назначенный символ, если HWND не находится внутри диалогового окна.

### <a name="instantiate-the-hwndhost-derived-class"></a>Создание экземпляра производного класса HwndHost

Наконец, теперь, когда все ключи и поддержка вкладок есть, вы можете поместить их <xref:System.Windows.Interop.HwndHost> в более крупное [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение. Если основное приложение написано в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], самый простой способ поместить его в нужное место — оставить пустой <xref:System.Windows.Controls.Border> элемент, где нужно поместить <xref:System.Windows.Interop.HwndHost>. Здесь вы создадите <xref:System.Windows.Controls.Border> именованную `insertHwndHostHere`:

```xaml
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

Все, что остается, — найти хорошее место в коде, чтобы создать экземпляр <xref:System.Windows.Interop.HwndHost> и подключить его <xref:System.Windows.Controls.Border>к. В этом примере он будет размещен в конструкторе для <xref:System.Windows.Window> производного класса:

```csharp
public partial class Window1 : Window {
    public Window1() {
    }

    void Window1_Loaded(object sender, RoutedEventArgs e) {
        HwndHost host = new ManagedCpp.MyHwndHost();
        insertHwndHostHere.Child = host;
    }
}
```

Это позволяет:

![Снимок экрана: приложение WPF работает.](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a>См. также

- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
