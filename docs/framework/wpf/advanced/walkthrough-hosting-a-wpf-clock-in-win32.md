---
title: "Пошаговое руководство. Размещение часов WPF в Win32"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55e5aa633e3d788ac8acaa09684c92b8608e7cfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>Пошаговое руководство. Размещение часов WPF в Win32
Для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внутри [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложения, используют <xref:System.Windows.Interop.HwndSource>, который предоставляет HWND, содержащий вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого. Сначала создайте <xref:System.Windows.Interop.HwndSource>, задав для него параметры аналогично CreateWindow.  Указать <xref:System.Windows.Interop.HwndSource> о [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого, которое требуется поместить.  Наконец, получается HWND из <xref:System.Windows.Interop.HwndSource>. В этом пошаговом руководстве описывается создание смешанного [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внутри [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложение, заново реализует операционной системы **свойства даты и времени** диалогового окна.  
  
## <a name="prerequisites"></a>Предварительные требования  
 В разделе [WPF и взаимодействие Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## <a name="how-to-use-this-tutorial"></a>Как использовать этот учебник  
 Основное внимание в этом учебнике уделяется важным шагам в процессе создания приложения взаимодействия. Образец, поддерживаемый учебника [пример взаимодействие часов Win32](http://go.microsoft.com/fwlink/?LinkID=160051), но в этом образце конечного продукта, отражающего свет. Этот учебник приведены шаги, как если бы вы начали с существующим [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] собственный проект, возможно ранее существующим проектом и добавили размещенных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложение. Вы можете сравнить конечного продукта с [пример взаимодействие часов Win32](http://go.microsoft.com/fwlink/?LinkID=160051).  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Пошаговое руководство по WPF внутри Win32 (HwndSource)  
 На следующем рисунке показан конечный продукт, который должен получиться в результате выполнения инструкций из этого учебника:  
  
 ![Диалоговое окно "Свойства даты и времени"](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")  
  
 Этот диалог можно создать заново, создав C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекта в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]и использование редактора диалоговых окон для создания следующих:  
  
 ![Диалоговое окно "Свойства даты и времени"](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")  
  
 (Необходимо использовать [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] использовать <xref:System.Windows.Interop.HwndSource>, и вам не нужно использовать C++ для записи [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] программы, но это весьма распространенный способ сделать это и легко решается также поэтапно предоставляется в руководстве).  
  
 Необходимо выполнить пять отдельных этапов, чтобы поместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов в диалоговом окне:  
  
1.  Включить вашей [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекта для вызова управляемого кода (**/CLR**), изменив параметры проекта в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].  
  
2.  Создание [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> в отдельной библиотеке DLL.  
  
3.  Поместите этот [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> внутри <xref:System.Windows.Interop.HwndSource>.  
  
4.  Получите HWND для, <xref:System.Windows.Controls.Page> с помощью <xref:System.Windows.Interop.HwndSource.Handle%2A> свойство.  
  
5.  Используйте [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] , чтобы указать место размещения HWND в большем [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложения  
  
## <a name="clr"></a>/clr  
 Первым шагом является преобразование этого неуправляемого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проект, в который можно вызывать управляемый код.  Используйте параметр компилятора/CLR, который свяжет необходимые библиотеки DLL и настройте метод Main для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Чтобы включить использование управляемого кода в проекте C++: щелкните правой кнопкой мыши на проекте win32clock и выберите **свойства**.  На **Общие** поддержки среды CLR, чтобы изменить страницу свойств (по умолчанию), `/clr`.  
  
 Добавьте ссылки на библиотеки DLL, необходимые для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll и UIAutomationTypes.dll. (Следующие инструкции предполагают, что операционная система установлена на диске C:.)  
  
1.  Щелкните правой кнопкой мыши на проекте win32clock и выберите **ссылки...** , а внутри этого диалогового окна:  
  
2.  Щелкните правой кнопкой мыши на проекте win32clock и выберите **ссылки...** .  
  
3.  Нажмите кнопку **добавить новую ссылку**, щелкните вкладку "Обзор", введите C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll и нажмите кнопку ОК.  
  
4.  Повторите то же самое для PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.  
  
5.  Повторите то же самое для WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.  
  
6.  Повторите то же самое для UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.  
  
7.  Повторите то же самое для UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.  
  
8.  Нажмите кнопку **добавить новую ссылку**, выберите System.dll и нажмите кнопку **ОК**.  
  
9. Нажмите кнопку **ОК** для выхода из страницы свойств win32clock для добавления ссылок.  
  
 Наконец, добавьте `STAThreadAttribute` для `_tWinMain` метод для использования с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 Этот атрибут сообщает [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] , при инициализации [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], следует использовать модель однопотокового подразделения (STA), который необходим для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).  
  
## <a name="create-a-windows-presentation-framework-page"></a>Создание страницы WPF  
 Создайте библиотеку DLL, которая определяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>. Часто бывает проще всего создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> как автономное приложение и записи и отладки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часть таким образом.  После этого проект можно преобразовать в библиотеку DLL, щелкнув правой кнопкой мыши проект, щелкнув **свойства**, перейдя в приложение и изменив тип выходных данных на библиотеку классов Windows.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Проект библиотеки dll, затем может быть объединен с [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекта (одно решение, которое содержит два проекта) ― щелкните правой кнопкой мыши решение, выберите **добавить существующий проект**.  
  
 Чтобы использовать эту [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проекта, необходимо добавить ссылку:  
  
1.  Щелкните правой кнопкой мыши на проекте win32clock и выберите **ссылки...** .  
  
2.  Нажмите кнопку **добавить новую ссылку**.  
  
3.  Щелкните вкладку **Проекты**.  Выберите WPFClock, нажмите кнопку "ОК".  
  
4.  Нажмите кнопку **ОК** для выхода из страницы свойств win32clock для добавления ссылок.  
  
## <a name="hwndsource"></a>HwndSource  
 Далее используется <xref:System.Windows.Interop.HwndSource> вносить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> выглядел как HWND.  Добавьте этот блок кода в файл C++:  
  
```  
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
  
 это большой фрагмент кода, который требует определенных пояснений.  Первая часть представляет собой различные операторы, поэтому полностью квалифицировать все вызовы не нужно:  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 Затем определяется функция, которая создает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого помещает <xref:System.Windows.Interop.HwndSource> вокруг и возвращает HWND:  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 Сначала создайте <xref:System.Windows.Interop.HwndSource>, чьи параметры аналогичны параметрам CreateWindow:  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 После этого создается [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] класс содержимого, вызывая его конструктор:  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 Затем страница соединяется <xref:System.Windows.Interop.HwndSource>:  
  
```  
source->RootVisual = page;  
```  
  
 И в последней строке возвращается HWND для <xref:System.Windows.Interop.HwndSource>:  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a>Размещение класса HWND  
 Теперь, когда имеется HWND, содержащий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов, необходимо поместить этот HWND в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] диалогового окна.  Если известно, где размещается HWND, было бы просто передать его размер и расположение для `GetHwnd` функцию, определенную ранее.  Однако для определения диалогового окна вы использовали файл ресурсов, поэтому вы не совсем уверены, где размещаются HWND.  Можно использовать [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] редактор диалоговых окон для размещения [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] элемента управления "STATIC" место пойти часы («вставьте часы здесь») и использовать его для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов.  
  
 Место обработки WM_INITDIALOG использовать `GetDlgItem` для получения HWND для местозаполнителя STATIC:  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 Затем вычисляется размер и положение местозаполнителя STATIC, чтобы можно было поместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов в этом месте:  
  
 Прямоугольник RECT;  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 Затем местозаполнитель STATIC скрывается:  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 И создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND в этом расположении часов:  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 Чтобы сделать это руководство интересным и создать настоящие [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов, вам нужно будет создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления часов на этом этапе. Это делается, в основном, с помощью разметки, с использованием нескольких обработчиков событий в коде программной части. Поскольку это руководство о взаимодействии, а не о разработке элементов управления, полный код для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] часов предоставляется здесь как блок кода, без отдельных указаний по его построению и означает каждая часть. Вы можете экспериментировать с этим кодом, чтобы изменить внешний вид и функциональность элемента управления.  
  
 Ниже приводится пример разметки:  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 И сопутствующий код программной части:  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 Результат выглядит следующим образом:  
  
 ![Диалоговое окно "Свойства даты и времени"](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")  
  
 Чтобы сравнить конечный результат в код, который создал данный снимок, см. [пример взаимодействие часов Win32](http://go.microsoft.com/fwlink/?LinkID=160051).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Interop.HwndSource>  
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Пример взаимодействия с часами Win32](http://go.microsoft.com/fwlink/?LinkID=160051)
