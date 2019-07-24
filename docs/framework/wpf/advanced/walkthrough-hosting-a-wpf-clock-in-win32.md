---
title: Пошаговое руководство. Размещение часов WPF в Win32
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 98e48060bbb82764e1e541797c666ca33f247c39
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400475"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>Пошаговое руководство. Размещение часов WPF в Win32

Чтобы разместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внутренние [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложения, используйте <xref:System.Windows.Interop.HwndSource>, который предоставляет HWND, содержащий ваше [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое. Сначала создайте <xref:System.Windows.Interop.HwndSource>, предоставив ему параметры, аналогичные CreateWindow. Затем вы узнаете <xref:System.Windows.Interop.HwndSource> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] о содержимом, которое вы хотите поместить в него. Наконец, вы получаете HWND из <xref:System.Windows.Interop.HwndSource>. В этом пошаговом руководстве показано, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] как [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] создать смешанное приложение, которое повторно реализует диалоговое окно **свойств даты и времени** операционной системы.

## <a name="prerequisites"></a>Предварительные требования

См. раздел [взаимодействие WPF и Win32](wpf-and-win32-interoperation.md).

## <a name="how-to-use-this-tutorial"></a>Как использовать этот учебник

Основное внимание в этом учебнике уделяется важным шагам в процессе создания приложения взаимодействия. Руководство основано на примере, [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051), но этот пример является отражением конечного продукта. В этом руководстве описаны действия, которые необходимо выполнить, как если бы [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] вы начали работу с существующим проектом, возможно, с уже существующим проектом, и вы добавили приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , размещенное в приложении. Вы можете сравнить конечный продукт с [примером взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Пошаговое руководство по WPF внутри Win32 (HwndSource)

На следующем рисунке показан конечный продукт, который должен получиться в результате выполнения инструкций из этого учебника:

![Снимок экрана, показывающий диалоговое окно "Свойства даты и времени".](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

Это диалоговое окно можно создать повторно, создав C++ проект Win32 в Visual Studio и используя редактор диалоговых окон, чтобы создать следующее:

![Диалоговое окно "Свойства даты и времени создания повторно"](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

(Использовать [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] для использования <xref:System.Windows.Interop.HwndSource>не требуется, и вам не нужно использовать C++ для написания [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] программ, но это довольно типичный способ сделать это, и само по себе оно хорошо послужит в ступенчатый руководстве).

Чтобы добавить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы в диалоговое окно, необходимо выполнить пять определенных подшагов.

1. Разрешить проекту вызывать управляемый код (/CLR), изменяя параметры проекта [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]в. [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]

2. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Создайте<xref:System.Windows.Controls.Page> в отдельной библиотеке DLL.

3. Вставьте его [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> в .<xref:System.Windows.Interop.HwndSource>

4. Получите HWND для этого <xref:System.Windows.Controls.Page> <xref:System.Windows.Interop.HwndSource.Handle%2A> с помощью свойства.

5. Используйте [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] , чтобы решить, куда поместить HWND в более крупном [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложении.

## <a name="clr"></a>/clr

Первым шагом является преобразование этого неуправляемого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекта в другой, который может вызывать управляемый код. Используйте параметр компилятора/CLR, который свяжется с необходимыми библиотеками DLL, которые необходимо использовать, и настройте метод Main для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Чтобы включить использование управляемого кода в C++ проекте, выполните следующие действия. Щелкните правой кнопкой мыши проект win32clock и выберите пункт **Свойства**. На странице свойств **Общие** (по умолчанию) измените поддержку среды CLR на `/clr`.

Затем добавьте ссылки на библиотеки DLL, необходимые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]для: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll и UIAutomationTypes. dll. (Следующие инструкции предполагают, что операционная система установлена на диске C:.)

1. Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** и внутри этого диалогового окна:

2. Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** .

3. Щелкните **Добавить новую ссылку**, выберите вкладку Обзор, введите C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll и нажмите кнопку ОК.

4. Повторите для PresentationFramework. dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.

5. Повторите для WindowsBase. dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.

6. Повторите для UIAutomationTypes. dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.

7. Повторите для UIAutomationProvider. dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.

8. Щелкните **Добавить новую ссылку**, выберите System. dll и нажмите кнопку **ОК**.

9. Нажмите кнопку **ОК** , чтобы закрыть страницы свойств win32clock для добавления ссылок.

 Наконец, добавьте `STAThreadAttribute` `_tWinMain` в метод для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

Этот атрибут указывает среде CLR, что при инициализации [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]она должна использовать модель однопотокового подразделения (STA), которая необходима для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).

## <a name="create-a-windows-presentation-framework-page"></a>Создание страницы WPF

Затем создается библиотека DLL, которая определяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Controls.Page> Зачастую проще создать приложение в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> качестве автономного приложения, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] а также написать и отладить часть таким образом. После этого можно превратить этот проект в библиотеку DLL, щелкнув проект правой кнопкой мыши, выбрав **Свойства**, перейдя к приложению и изменив тип выходных данных на библиотеку классов Windows.

Затем проект [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] DLL можно объединить с проектом (одно решение, содержащее два проекта) — щелкните решение правой кнопкой мыши и выберите **адд\ексистинг Project (проект**). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]

Чтобы использовать эту [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] библиотеку DLL [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] из проекта, необходимо добавить ссылку:

1. Щелкните правой кнопкой мыши проект win32clock и выберите **ссылки...** .

2. Щелкните **Добавить новую ссылку**.

3. Щелкните вкладку **Проекты**. Выберите WPFClock, нажмите кнопку "ОК".

4. Нажмите кнопку **ОК** , чтобы закрыть страницы свойств win32clock для добавления ссылок.

## <a name="hwndsource"></a>HwndSource

Затем используйте <xref:System.Windows.Interop.HwndSource> , чтобы сделать его [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> похожим на HWND. Добавьте этот блок кода в файл C++:

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

 Затем вы определяете функцию, которая создает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое, <xref:System.Windows.Interop.HwndSource> помещает вокруг нее и возвращает HWND:

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

Сначала создайте объект <xref:System.Windows.Interop.HwndSource>, параметры которого похожи на CreateWindow:

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

Затем создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] класс содержимого, вызвав его конструктор:

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

Теперь, когда у вас есть HWND, содержащий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы, необходимо разместить HWND [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] внутри диалогового окна. Если вы знаете, куда разместить HWND, то нужно просто передать этот размер и расположение в `GetHwnd` определенную ранее функцию. Однако для определения диалогового окна вы использовали файл ресурсов, поэтому вы не совсем уверены, где размещаются HWND. Можно использовать [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] редактор диалоговых окон, чтобы [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] поместить статический элемент управления в место, где нужно добавить часы ("вставить часы здесь"), и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использовать его для позиционирования часов.

При обработке WM_INITDIALOG используется `GetDlgItem` для получения HWND для прототипа static:

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

Затем вы вычисляете размер и позицию этого заполнителя static, чтобы можно было поместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы в это место:

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

И создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND часов в этом расположении:

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

Чтобы сделать этот учебник интересным и получить реальные [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часы, на этом этапе необходимо [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создать элемент управления часами. Это делается, в основном, с помощью разметки, с использованием нескольких обработчиков событий в коде программной части. Так как в этом учебнике рассматривается взаимодействие, а не структура элемента управления, полный код [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для часов предоставляется здесь в виде блока кода без отдельных инструкций по его созданию или по каждой части. Вы можете экспериментировать с этим кодом, чтобы изменить внешний вид и функциональность элемента управления.

Ниже приводится пример разметки:

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

И сопутствующий код программной части:

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

Результат выглядит следующим образом:

![Диалоговое окно «Свойства даты и времени последнего результата»](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

Чтобы сравнить конечный результат с кодом, созданным на этом снимке экрана, см. [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Interop.HwndSource>
- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
- [Пример взаимодействия с часами Win32](https://go.microsoft.com/fwlink/?LinkID=160051)
