---
title: Пошаговое руководство. Размещение часов WPF в Win32
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 8d1f376a2c5b3f31407af0100d9a4417f7cff34e
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740237"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>Пошаговое руководство. Размещение часов WPF в Win32

Чтобы разместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внутри приложений Win32, используйте <xref:System.Windows.Interop.HwndSource>, который предоставляет HWND, содержащий содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Сначала создайте <xref:System.Windows.Interop.HwndSource>, предоставив ему параметры, аналогичные CreateWindow. Затем вы указываете <xref:System.Windows.Interop.HwndSource> о требуемом содержимом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Наконец, вы получаете HWND из <xref:System.Windows.Interop.HwndSource>. В этом пошаговом руководстве показано, как создать смешанный [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложении Win32, которое повторно реализует диалоговое окно **свойств даты и времени** операционной системы.

## <a name="prerequisites"></a>Prerequisites

См. раздел [взаимодействие WPF и Win32](wpf-and-win32-interoperation.md).

## <a name="how-to-use-this-tutorial"></a>Применение данного учебника

Основное внимание в этом учебнике уделяется важным шагам в процессе создания приложения взаимодействия. Руководство основано на примере, [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051), но этот пример является отражением конечного продукта. В этом учебнике описываются действия, которые необходимо выполнить, как если бы вы начали работу с существующим проектом Win32, возможно, с уже существующим проектом, и вы добавили размещенную [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложение. Вы можете сравнить конечный продукт с [примером взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Пошаговое руководство по WPF внутри Win32 (HwndSource)

На следующем рисунке показан конечный продукт, который должен получиться в результате выполнения инструкций из этого учебника:

![Снимок экрана, показывающий диалоговое окно "Свойства даты и времени".](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

Это диалоговое окно можно создать повторно, создав C++ проект Win32 в Visual Studio и используя редактор диалоговых окон, чтобы создать следующее:

![Диалоговое окно "Свойства даты и времени создания повторно"](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

(Не нужно использовать Visual Studio для использования <xref:System.Windows.Interop.HwndSource>, и вам не нужно использовать C++ для написания программ Win32, но это довольно типичный способ сделать это, и само по себе может стать ступенчатыйным описанием учебника).

Чтобы добавить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы в диалоговое окно, необходимо выполнить пять конкретных шагов.

1. Включите в проекте Win32 вызов управляемого кода ( **/CLR**), изменив параметры проекта в Visual Studio.

2. Создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> в отдельной библиотеке DLL.

3. Поставьте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> в <xref:System.Windows.Interop.HwndSource>.

4. Получите HWND для этого <xref:System.Windows.Controls.Page> используя свойство <xref:System.Windows.Interop.HwndSource.Handle%2A>.

5. Использование Win32 для определения места размещения HWND в большом приложении Win32

## <a name="clr"></a>/clr

Первым шагом является преобразование этого неуправляемого проекта Win32 в тот, который может вызывать управляемый код. Используйте параметр компилятора/CLR, который свяжется с необходимыми библиотеками DLL, которые необходимо использовать, и настройте метод Main для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Чтобы включить использование управляемого кода внутри C++ проекта, щелкните правой кнопкой мыши проект win32clock и выберите пункт **свойства**. На странице свойств **Общие** (по умолчанию) измените поддержку среды clr на `/clr`.

Затем добавьте ссылки на библиотеки DLL, необходимые для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll и UIAutomationTypes. dll. (Следующие инструкции предполагают, что операционная система установлена на диске C:.)

1. Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** и внутри этого диалогового окна:

2. Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** .

3. Щелкните **Добавить новую ссылку**, выберите вкладку Обзор, введите C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll и нажмите кнопку ОК.

4. Повторите то же самое для PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.

5. Повторите то же самое для WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.

6. Повторите то же самое для UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.

7. Повторите то же самое для UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.

8. Щелкните **Добавить новую ссылку**, выберите System. dll и нажмите кнопку **ОК**.

9. Нажмите кнопку **ОК** , чтобы закрыть страницы свойств win32clock для добавления ссылок.

 Наконец, добавьте `STAThreadAttribute` в метод `_tWinMain` для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

Этот атрибут указывает среде CLR, что при инициализации объектной модели компонента (COM) она должна использовать модель однопотокового подразделения (STA), которая необходима для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).

## <a name="create-a-windows-presentation-framework-page"></a>Создание страницы WPF

Затем создается библиотека DLL, которая определяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>. Зачастую проще всего создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> как автономное приложение, а также написать и отладить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ную часть. После этого можно превратить этот проект в библиотеку DLL, щелкнув проект правой кнопкой мыши, выбрав **Свойства**, перейдя к приложению и изменив тип выходных данных на библиотеку классов Windows.

Затем проект [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] DLL можно объединить с проектом Win32 (одно решение, содержащее два проекта) — щелкните решение правой кнопкой мыши и выберите **Адд\ексистинг Project (проект**).

Чтобы использовать эту [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] библиотеку DLL из проекта Win32, необходимо добавить ссылку:

1. Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** .

2. Щелкните **Добавить новую ссылку**.

3. Перейдите на вкладку **проекты** . Выберите впфклокк и нажмите кнопку ОК.

4. Нажмите кнопку **ОК** , чтобы закрыть страницы свойств win32clock для добавления ссылок.

## <a name="hwndsource"></a>HwndSource

Затем используйте <xref:System.Windows.Interop.HwndSource>, чтобы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> выглядеть как HWND. Добавьте этот блок кода в файл C++:

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;

    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
        HwndSource^ source = gcnew HwndSource(
            0, // class style
            WS_VISIBLE | WS_CHILD, // style
            0, // exstyle
            x, y, width, height,
            "hi", // NAME
            IntPtr(parent)        // parent window
            );

        UIElement^ page = gcnew WPFClock::Clock();
        source->RootVisual = page;
        return (HWND) source->Handle.ToPointer();
    }
}
}
```

 это большой фрагмент кода, который требует определенных пояснений. Первая часть представляет собой различные операторы, поэтому полностью квалифицировать все вызовы не нужно:

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 Затем вы определяете функцию, которая создает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ное содержимое, помещает <xref:System.Windows.Interop.HwndSource> вокруг него и возвращает HWND:

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

Сначала создайте <xref:System.Windows.Interop.HwndSource>, параметры которого похожи на CreateWindow:

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

Затем создайте класс содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], вызвав его конструктор:

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

Затем вы подключаете страницу к <xref:System.Windows.Interop.HwndSource>:

```cpp
source->RootVisual = page;
```

 В последней строке возвращается HWND для <xref:System.Windows.Interop.HwndSource>:

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a>Размещение класса HWND

Теперь, когда у вас есть HWND, содержащий часы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], необходимо разместить HWND в диалоговом окне Win32. Если вы знаете, куда разместить HWND, то нужно просто передать этот размер и расположение в определенную ранее функцию `GetHwnd`. Однако для определения диалогового окна вы использовали файл ресурсов, поэтому вы не совсем уверены, где размещаются HWND. Вы можете использовать редактор диалоговых окон Visual Studio для размещения статического элемента управления Win32 в том месте, где нужно добавить часы ("вставить часы здесь"), и использовать его для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов.

При обработке WM_INITDIALOG используется `GetDlgItem` для получения HWND для прототипа STATIC:

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

Затем вы вычисляете размер и позицию этого заполнителя STATIC, чтобы можно было поместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы в это место:

Прямоугольник RECT;

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

Затем местозаполнитель STATIC скрывается:

```cpp
ShowWindow(placeholder, SW_HIDE);
```

Создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND часов в этом расположении:

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

Чтобы сделать этот учебник интересным и создать реальный [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы, на этом этапе необходимо создать элемент управления часами [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Это делается, в основном, с помощью разметки, с использованием нескольких обработчиков событий в коде программной части. Поскольку в этом учебнике рассматривается взаимодействие, а не проектирование элементов управления, полный код для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов предоставляется здесь в виде блока кода без дискретных инструкций по его созданию или по каждой части. Вы можете экспериментировать с этим кодом, чтобы изменить внешний вид и функциональность элемента управления.

Ниже приводится пример разметки:

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

И сопутствующий код программной части:

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

Результат выглядит следующим образом:

![Диалоговое окно «Свойства даты и времени последнего результата»](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

Чтобы сравнить конечный результат с кодом, созданным на этом снимке экрана, см. [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Interop.HwndSource>
- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
- [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051)
