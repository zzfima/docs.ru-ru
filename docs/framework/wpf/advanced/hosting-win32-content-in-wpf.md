---
title: Размещение содержимого Win32 в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: 3c00539eb5f2a96fec974accda2fea1c0200aeec
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "63807756"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="10b6c-102">Размещение содержимого Win32 в WPF</span><span class="sxs-lookup"><span data-stu-id="10b6c-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10b6c-103">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="10b6c-103">Prerequisites</span></span>

<span data-ttu-id="10b6c-104">См. в разделе [взаимодействие WPF и Win32](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="10b6c-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="10b6c-105">Пошаговое руководство на основе Win32 в Windows Presentation Framework (HwndHost)</span><span class="sxs-lookup"><span data-stu-id="10b6c-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="10b6c-106">Для повторного использования [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] содержимое внутри [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения, используют <xref:System.Windows.Interop.HwndHost>, который является элементом управления, который заставляет HWND выглядеть [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого.</span><span class="sxs-lookup"><span data-stu-id="10b6c-106">To reuse [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="10b6c-107">Как <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> проста в использовании: являются производными от <xref:System.Windows.Interop.HwndHost> и реализовать `BuildWindowCore` и `DestroyWindowCore` методы, затем экземпляр вашего <xref:System.Windows.Interop.HwndHost> производного класса и поместите его внутри вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение.</span><span class="sxs-lookup"><span data-stu-id="10b6c-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="10b6c-108">Если ваш [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] логики уже упакован как элемент управления, то `BuildWindowCore` реализации нечто большее, чем вызов `CreateWindow`.</span><span class="sxs-lookup"><span data-stu-id="10b6c-108">If your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="10b6c-109">Например, чтобы создать [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] управления LISTBOX в [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="10b6c-109">For example, to create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX control in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span></span>

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

<span data-ttu-id="10b6c-110">Но предположим, что [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] код не столь автономно?</span><span class="sxs-lookup"><span data-stu-id="10b6c-110">But suppose the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] code is not quite so self-contained?</span></span> <span data-ttu-id="10b6c-111">Если таким образом, можно создать [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] диалоговое окно и внедрить его содержимое в одно крупное [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="10b6c-111">If so, you can create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="10b6c-112">В этом примере это в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] и [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], несмотря на то, что это также можно сделать на другом языке или из командной строки.</span><span class="sxs-lookup"><span data-stu-id="10b6c-112">The sample shows this in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="10b6c-113">Начните с простого диалога, который компилируется в [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="10b6c-113">Start with a simple dialog, which is compiled into a [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] project.</span></span>

<span data-ttu-id="10b6c-114">Затем поместим диалог в большее [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения:</span><span class="sxs-lookup"><span data-stu-id="10b6c-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="10b6c-115">Скомпилируйте [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] как управляемый (`/clr`)</span><span class="sxs-lookup"><span data-stu-id="10b6c-115">Compile the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] as managed (`/clr`)</span></span>

- <span data-ttu-id="10b6c-116">Включить диалоговое окно в элемент управления</span><span class="sxs-lookup"><span data-stu-id="10b6c-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="10b6c-117">Определить класс, производный от <xref:System.Windows.Interop.HwndHost> с `BuildWindowCore` и `DestroyWindowCore` методы</span><span class="sxs-lookup"><span data-stu-id="10b6c-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="10b6c-118">Переопределить `TranslateAccelerator` метод для обработки ключей диалоговое окно</span><span class="sxs-lookup"><span data-stu-id="10b6c-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="10b6c-119">Переопределить `TabInto` метод для поддержки переходов</span><span class="sxs-lookup"><span data-stu-id="10b6c-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="10b6c-120">Переопределить `OnMnemonic` метод для поддержки назначенных клавиш</span><span class="sxs-lookup"><span data-stu-id="10b6c-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="10b6c-121">Создать экземпляр <xref:System.Windows.Interop.HwndHost> подкласс и поместить его в правом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемент</span><span class="sxs-lookup"><span data-stu-id="10b6c-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="10b6c-122">Включить диалоговое окно в элемент управления</span><span class="sxs-lookup"><span data-stu-id="10b6c-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="10b6c-123">Диалоговое окно можно превратить в дочерний элемент с использованием стилей WS_CHILD и DS_CONTROL HWND.</span><span class="sxs-lookup"><span data-stu-id="10b6c-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="10b6c-124">Перейдите в файл ресурсов (.rc), где определено диалоговое окно и найти начало определения диалогового окна:</span><span class="sxs-lookup"><span data-stu-id="10b6c-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="10b6c-125">Измените второй строки, чтобы:</span><span class="sxs-lookup"><span data-stu-id="10b6c-125">Change the second line to:</span></span>

```
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="10b6c-126">Это действие не полностью его в автономное элемента управления; необходимо по-прежнему вызвать `IsDialogMessage()` , [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] может обрабатывать определенные сообщения, но изменение элемента управления предоставляют простой способ размещения этих элементов управления внутри другого HWND.</span><span class="sxs-lookup"><span data-stu-id="10b6c-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="10b6c-127">Подкласс HwndHost</span><span class="sxs-lookup"><span data-stu-id="10b6c-127">Subclass HwndHost</span></span>

<span data-ttu-id="10b6c-128">Импортируйте такие пространства имен:</span><span class="sxs-lookup"><span data-stu-id="10b6c-128">Import the following namespaces:</span></span>

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

<span data-ttu-id="10b6c-129">Создайте класс, производный от <xref:System.Windows.Interop.HwndHost> и переопределить `BuildWindowCore` и `DestroyWindowCore` методов:</span><span class="sxs-lookup"><span data-stu-id="10b6c-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

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

<span data-ttu-id="10b6c-130">Здесь используется `CreateDialog` Создание диалогового окна, которое на самом деле элемент управления.</span><span class="sxs-lookup"><span data-stu-id="10b6c-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="10b6c-131">Так как это один из первых методов, вызванных внутри [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], необходимо выполнить некоторые стандартные [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] инициализацию путем вызова функции, будут определены позже, вызывается `InitializeGlobals()`:</span><span class="sxs-lookup"><span data-stu-id="10b6c-131">Since this is one of the first methods called inside the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], you should also do some standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="10b6c-132">Переопределите метод TranslateAccelerator обрабатывать ключи диалоговое окно</span><span class="sxs-lookup"><span data-stu-id="10b6c-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="10b6c-133">Если запустить этот пример, получится элемент управления диалогового окна, отображающий, но будет игнорировать всю обработку, которая делает клавиатуры диалоговое окно функциональной диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="10b6c-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="10b6c-134">Теперь необходимо переопределить `TranslateAccelerator` реализации (который поставляется вместе с `IKeyboardInputSink`, интерфейс, <xref:System.Windows.Interop.HwndHost> реализует).</span><span class="sxs-lookup"><span data-stu-id="10b6c-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="10b6c-135">Этот метод вызывается, когда приложение получает WM_KEYDOWN и WM_SYSKEYDOWN.</span><span class="sxs-lookup"><span data-stu-id="10b6c-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

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

<span data-ttu-id="10b6c-136">Это много кода, поэтому она может использовать более подробные пояснения.</span><span class="sxs-lookup"><span data-stu-id="10b6c-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="10b6c-137">Во-первых, код, используя [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] и [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] макросы; вы должны знать, что уже макрос с именем `TranslateAccelerator`, который определен в winuser.h:</span><span class="sxs-lookup"><span data-stu-id="10b6c-137">First, the code using [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="10b6c-138">Поэтому убедитесь, что определение `TranslateAccelerator` метода и не `TranslateAcceleratorW` метод.</span><span class="sxs-lookup"><span data-stu-id="10b6c-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="10b6c-139">Таким же образом есть неуправляемый код winuser.h MSG и управляемое `Microsoft::Win32::MSG` структуры.</span><span class="sxs-lookup"><span data-stu-id="10b6c-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="10b6c-140">Чтобы устранить неоднозначность между ними с помощью [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` оператор.</span><span class="sxs-lookup"><span data-stu-id="10b6c-140">You can disambiguate between the two using the [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` operator.</span></span>

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

<span data-ttu-id="10b6c-141">К `TranslateAccelerator`.</span><span class="sxs-lookup"><span data-stu-id="10b6c-141">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="10b6c-142">Основным критерием является вызов [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] функция `IsDialogMessage` делать столько работы, возможно, но `IsDialogMessage` не имеет доступа к любому за пределами диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="10b6c-142">The basic principle is to call the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="10b6c-143">По мере выполнения вне диалогового окна, заставляя следующую за последним элементом управления в нашем диалоге, вам потребуется установить фокус на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часть путем вызова `IKeyboardInputSite::OnNoMoreStops`.</span><span class="sxs-lookup"><span data-stu-id="10b6c-143">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

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

<span data-ttu-id="10b6c-144">Теперь вызовите `IsDialogMessage`.</span><span class="sxs-lookup"><span data-stu-id="10b6c-144">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="10b6c-145">Но один из ответственности `TranslateAccelerator` метод сообщается [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ли нажатие клавиши или нет.</span><span class="sxs-lookup"><span data-stu-id="10b6c-145">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="10b6c-146">Если вы не обрабатывает его, событие ввода может Туннелировать и поднимаются по остальной части приложения.</span><span class="sxs-lookup"><span data-stu-id="10b6c-146">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="10b6c-147">Здесь, будут предоставлены особенности обработки клавиатуры и характера архитектура ввода в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10b6c-147">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span></span> <span data-ttu-id="10b6c-148">К сожалению `IsDialogMessage` не возвращает никоим образом обрабатывает ли конкретное нажатие клавиши.</span><span class="sxs-lookup"><span data-stu-id="10b6c-148">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="10b6c-149">Что еще хуже, он вызывает `DispatchMessage()` на нажатия клавиш, он не должен обрабатывать!</span><span class="sxs-lookup"><span data-stu-id="10b6c-149">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="10b6c-150">Чтобы вы могли реконструировать `IsDialogMessage`и вызвать его только для ключей, вы знаете, что он будет обрабатывать:</span><span class="sxs-lookup"><span data-stu-id="10b6c-150">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

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

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="10b6c-151">Переопределение метода TabInto для поддержки переходов</span><span class="sxs-lookup"><span data-stu-id="10b6c-151">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="10b6c-152">Теперь, когда вы реализовали `TranslateAccelerator`, пользователь может совершать переходы внутри диалогового окна поле и выйти в большее [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="10b6c-152">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="10b6c-153">Но пользователь не может перейти обратно в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="10b6c-153">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="10b6c-154">Чтобы разрешить это, переопределите `TabInto`:</span><span class="sxs-lookup"><span data-stu-id="10b6c-154">To solve that, you override `TabInto`:</span></span>

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

<span data-ttu-id="10b6c-155">`TraversalRequest` Параметр указывает, является ли действие tab или shift.</span><span class="sxs-lookup"><span data-stu-id="10b6c-155">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="10b6c-156">Переопределение метода OnMnemonic для поддержки назначенных клавиш</span><span class="sxs-lookup"><span data-stu-id="10b6c-156">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="10b6c-157">Обработка событий клавиатуры почти завершена, но имеется еще один аспекте — назначенные клавиши не работают.</span><span class="sxs-lookup"><span data-stu-id="10b6c-157">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="10b6c-158">Если пользователь нажимает клавишу alt-F, фокус не переходит в «First name:» поле ввода.</span><span class="sxs-lookup"><span data-stu-id="10b6c-158">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="10b6c-159">Таким образом, необходимо переопределить `OnMnemonic` метод:</span><span class="sxs-lookup"><span data-stu-id="10b6c-159">So, you override the `OnMnemonic` method:</span></span>

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

<span data-ttu-id="10b6c-160">Почему бы не вызвать `IsDialogMessage` здесь?</span><span class="sxs-lookup"><span data-stu-id="10b6c-160">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="10b6c-161">Имеют ту же проблему как — необходимо иметь возможность сообщить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] кода, обработал ли код нажатие клавиши или нет, и `IsDialogMessage` не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="10b6c-161">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="10b6c-162">Есть также вторая проблема, так как `IsDialogMessage` отказывается обрабатывать мнемонический символ, если фокус HWND не содержится в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="10b6c-162">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="10b6c-163">Создать экземпляр производного класса HwndHost</span><span class="sxs-lookup"><span data-stu-id="10b6c-163">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="10b6c-164">Наконец, после того, вся поддержка ключа и вкладку на месте, можно поместить в <xref:System.Windows.Interop.HwndHost> в большее [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="10b6c-164">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="10b6c-165">Если основное приложение создается на языке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], чтобы поместить его в нужном месте проще всего оставить пустым <xref:System.Windows.Controls.Border> элемент, где необходимо поместить <xref:System.Windows.Interop.HwndHost>.</span><span class="sxs-lookup"><span data-stu-id="10b6c-165">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="10b6c-166">Вы создадите <xref:System.Windows.Controls.Border> с именем `insertHwndHostHere`:</span><span class="sxs-lookup"><span data-stu-id="10b6c-166">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

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

<span data-ttu-id="10b6c-167">Затем все, что остается лишь найти правильное место в коде для создания экземпляра <xref:System.Windows.Interop.HwndHost> и подключите его к <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="10b6c-167">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="10b6c-168">В этом примере будет поместить его в конструктор для <xref:System.Windows.Window> производного класса:</span><span class="sxs-lookup"><span data-stu-id="10b6c-168">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

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

<span data-ttu-id="10b6c-169">Что позволяет:</span><span class="sxs-lookup"><span data-stu-id="10b6c-169">Which gives you:</span></span>

![Снимок экрана запуска приложения WPF.](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a><span data-ttu-id="10b6c-171">См. также</span><span class="sxs-lookup"><span data-stu-id="10b6c-171">See also</span></span>

- [<span data-ttu-id="10b6c-172">Взаимодействие WPF и Win32</span><span class="sxs-lookup"><span data-stu-id="10b6c-172">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
