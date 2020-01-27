---
title: Размещение содержимого Win32
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: b3113d9f3146e1590363dc9db6f751a429dda74b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747010"
---
# <a name="hosting-win32-content-in-wpf"></a>Размещение содержимого Win32 в WPF

## <a name="prerequisites"></a>Prerequisites

См. раздел [взаимодействие WPF и Win32](wpf-and-win32-interoperation.md).

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Пошаговое руководство по Win32 в Windows Presentation Framework (HwndHost)

Чтобы повторно использовать содержимое Win32 внутри приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], используйте <xref:System.Windows.Interop.HwndHost>, который представляет собой элемент управления, который делает HWND похожими на содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Как и <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> прост в использовании: наследовать от <xref:System.Windows.Interop.HwndHost> и реализовать методы `BuildWindowCore` и `DestroyWindowCore`, создать экземпляр производного класса <xref:System.Windows.Interop.HwndHost> и поместить его в приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Если логика Win32 уже упакована как элемент управления, `BuildWindowCore`ная реализация немного больше, чем вызов `CreateWindow`. Например, для создания элемента управления LISTBOX в Win32 в C++:

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

Но предположим, что код Win32 не так уж сам самодостаточный? Если это так, можно создать диалоговое окно Win32 и внедрить его содержимое в более крупное приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. В этом примере это показано в Visual Studio C++, хотя это также можно сделать на другом языке или в командной строке.

Начните с простого диалогового окна, которое компилируется в C++ проект DLL.

Затем Познакомьтесь с диалоговым окном в более [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложении:

- Компиляция библиотеки DLL как управляемой (`/clr`)

- Преобразование диалогового окна в элемент управления

- Определение производного класса <xref:System.Windows.Interop.HwndHost> с помощью методов `BuildWindowCore` и `DestroyWindowCore`

- Переопределение метода `TranslateAccelerator` для работы с диалоговыми ключами

- Переопределение `TabInto` метода для поддержки перехода по клавише TAB

- Переопределение `OnMnemonic` метода для поддержки назначенных клавиш

- Создание экземпляра подкласса <xref:System.Windows.Interop.HwndHost> и помещение его в правый [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемент

### <a name="turn-the-dialog-into-a-control"></a>Преобразование диалогового окна в элемент управления

Диалоговое окно можно преобразовать в дочерний HWND с помощью стилей WS_CHILD и DS_CONTROL. Перейдите в файл ресурсов (. RC), в котором определено диалоговое окно, и найдите начало определения диалогового окна:

```text
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

Измените вторую строку на:

```text
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

Это действие не полностью упаковывается в самодостаточный элемент управления. по-прежнему необходимо вызвать `IsDialogMessage()` так, чтобы Win32 мог обрабатывать определенные сообщения, но изменение элемента управления обеспечивает простой способ размещения этих элементов управления в другом HWND.

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

Затем создайте производный класс <xref:System.Windows.Interop.HwndHost> и переопределите методы `BuildWindowCore` и `DestroyWindowCore`:

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

Здесь вы используете `CreateDialog`, чтобы создать диалоговое окно, которое на самом деле является элементом управления. Поскольку это один из первых методов, вызываемых в библиотеке DLL, необходимо также выполнить стандартную инициализацию Win32, вызвав функцию, которая будет определена позже, называется `InitializeGlobals()`:

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

Если вы запустили этот пример, вы получите элемент управления диалогового окна, отображающий, но при этом будет игнорироваться вся обработка клавиатуры, которая делает диалоговое окно функциональным. Теперь следует переопределить `TranslateAccelerator`ную реализацию (которая поступает от `IKeyboardInputSink`интерфейс, который <xref:System.Windows.Interop.HwndHost> реализует). Этот метод вызывается, когда приложение получает WM_KEYDOWN и WM_SYSKEYDOWN.

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

Поэтому убедитесь, что определен метод `TranslateAccelerator`, а не метод `TranslateAcceleratorW`.

Аналогично, существует и неуправляемая программа Winuser. h MSG, и управляемая структура `Microsoft::Win32::MSG`. Можно определить неоднозначность между двумя с C++ помощью оператора `::`.

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

Вернитесь к `TranslateAccelerator`. Основной принцип заключается в вызове функции Win32 `IsDialogMessage` для выполнения максимально возможной работы, но `IsDialogMessage` не имеет доступа к чему-либо за пределами диалогового окна. Во время перехода на вкладку пользователя в диалоговом окне, когда Табуляция выполняется после последнего элемента управления в нашем диалоговом окне, необходимо установить фокус на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] части, вызвав `IKeyboardInputSite::OnNoMoreStops`.

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

Теперь вызовите `IsDialogMessage`. Но одна из обязанностей `TranslateAccelerator` метода сообщает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], обрабатывается ли нажатие клавиши. Если вы не обработали его, входное событие может быть туннелем и пузырьковым через остальную часть приложения. Здесь вы узнаете о том, как работать с клавиатурой мессанже и характерность входной архитектуры в Win32. К сожалению, `IsDialogMessage` не возвращает никакого способа, обрабатывает ли он определенное нажатие клавиши. Еще хуже, он вызывает `DispatchMessage()` на нажатые клавиши, которые не должны обработаны!  Поэтому необходимо выполнить реконструирование `IsDialogMessage`и вызвать его только для тех ключей, которые будут обработаны.

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

Теперь, когда вы реализовали `TranslateAccelerator`, пользователь может переходить на вкладку внутри диалогового окна и выключать его из него в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложении. Но пользователь не может вернуться на вкладку в диалоговое окно. Чтобы решить эту проблему, переопределите `TabInto`:

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

Параметр `TraversalRequest` указывает, является ли действие вкладки вкладкой TAB или Shift.

### <a name="override-onmnemonic-method-to-support-mnemonics"></a>Переопределение метода OnMnemonic для поддержки назначенных клавиш

Обработка клавиатуры почти завершена, но есть одна вещь, что не работает. Если пользователь нажмет клавишу Alt-F, фокус не будет переходить к полю "First Name:" (изменить). Таким образом, вы переопределяете метод `OnMnemonic`:

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

Почему не нужно вызывать `IsDialogMessage`?  У вас есть та же самая ошибка, что и перед--необходимо иметь возможность информировать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] код, обработал ли код нажатием клавиши или нет, и `IsDialogMessage` не может сделать это. Кроме того, существует вторая ошибка, так как `IsDialogMessage` отказывается обработать назначенный символ, если HWND, который не находится в диалоговом окне.

### <a name="instantiate-the-hwndhost-derived-class"></a>Создание экземпляра производного класса HwndHost

Наконец, теперь, когда все ключи и поддержка вкладок есть, можно поместить <xref:System.Windows.Interop.HwndHost> в большее [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ное приложение. Если основное приложение написано в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], самый простой способ поместить его в нужное место — оставить пустой элемент <xref:System.Windows.Controls.Border>, где нужно поместить <xref:System.Windows.Interop.HwndHost>. Здесь вы создадите <xref:System.Windows.Controls.Border> с именем `insertHwndHostHere`:

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

Все, что остается, — найти хорошее место в коде, чтобы создать экземпляр <xref:System.Windows.Interop.HwndHost> и подключить его к <xref:System.Windows.Controls.Border>. В этом примере он будет размещен в конструкторе для <xref:System.Windows.Window> производного класса:

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

## <a name="see-also"></a>См. также:

- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
