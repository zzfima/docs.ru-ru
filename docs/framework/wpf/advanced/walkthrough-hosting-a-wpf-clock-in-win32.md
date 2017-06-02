---
title: "Пошаговое руководство. Размещение часов WPF в Win32 | Microsoft Docs"
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
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Пошаговое руководство. Размещение часов WPF в Win32
Для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложениях [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] используется <xref:System.Windows.Interop.HwndSource>, предоставляющий HWND, который включает в себя содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Сначала создается <xref:System.Windows.Interop.HwndSource> путем задания его параметров аналогично созданию окна.  Затем <xref:System.Windows.Interop.HwndSource> о [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сообщается о содержимом, которое требуется поместить.  Наконец, получается HWND из <xref:System.Windows.Interop.HwndSource>.  В данном пошаговом руководстве описывается создание смешанного [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложении [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], который заново реализует диалог **Свойства даты и времени** операционной системы.  
  
## Обязательные компоненты  
 См. раздел [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## Использование этого руководства  
 Это руководство сосредоточено на важных шагах создания приложения взаимодействия.  Руководство содержит пример, [Пример Win32 Clock Interoperation](http://go.microsoft.com/fwlink/?LinkID=160051), который является отражением конечного продукта.  В руководстве документируются этапы, как если бы вы начали с собственным существующим [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] проектом, или возможно с ранее существующим проектом, и добавили размещенный [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложение.  Конечный продукт можно сравнить с [примером Win32 Clock Interoperation](http://go.microsoft.com/fwlink/?LinkID=160051).  
  
## Пример Windows Presentation Framework в Win32 \(HwndSource\)  
 На приведенном ниже рисунке показан предполагаемый конечный продукт этого руководства:  
  
 ![Диалоговое окно “Дата и свойства времени”](../../../../docs/framework/wpf/advanced/media/interoparch06.png "InteropArch06")  
  
 Этот диалог можно создать заново, создав проект [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] C\+\+ в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] и с помощью редактора окон создав следующее:  
  
 ![Диалоговое окно “Дата и свойства времени”](../../../../docs/framework/wpf/advanced/media/interoparch07.png "InteropArch07")  
  
 \(Нет необходимости применять [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] для использования <xref:System.Windows.Interop.HwndSource>, и не нужно использовать C\+\+ для написания программ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], но это довольно обычный способ, который поэтапно предоставляется в руководстве\).  
  
 Чтобы поместить часы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в диалог, необходимо выполнить пять отдельных этапов:  
  
1.  Включите для вашего проекта [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] возможность вызова управляемого кода \(**\/clr**\), изменив параметры проекта в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].  
  
2.  Создайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> в отдельной библиотеке DLL.  
  
3.  Поместите этот [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> в <xref:System.Windows.Interop.HwndSource>.  
  
4.  Получите HWND для этого <xref:System.Windows.Controls.Page> с помощью свойства <xref:System.Windows.Interop.HwndSource.Handle%2A>.  
  
5.  Используйте [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], чтобы решить, где поместить HWND в большем [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложении  
  
## \/clr  
 Первым шагом является преобразование этого неуправляемого проекта [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в проект, который может вызывать управляемый код.  Используйте параметр компилятора \/clr, который свяжет необходимые библиотеки DLL, и настройте метод Main для использования в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Чтобы включить использование управляемого кода в проекте C\+\+, щелкните правой кнопкой мыши на проекте win32clock и выберите **Свойства**.  На странице свойств **Общие** \(по умолчанию\) измените поддержку CLR на `/clr`.  
  
 Затем добавьте ссылки на библиотеки DLL, необходимые для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll и UIAutomationTypes.dll.  \(Следующие инструкции предполагают, что операционная система установлена на диске C:\)  
  
1.  Щелкните правой кнопкой мыши на проекте win32clock и выберите **Ссылки...**; затем в этом диалоговом окне:  
  
2.  Щелкните правой кнопкой мыши на проекте win32clock и выберите **Ссылки...**.  
  
3.  Нажмите кнопку **Добавить новую ссылку**, перейдите на вкладку "Обзор", введите "C:\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\PresentationCore.dll" и нажмите кнопку "ОК".  
  
4.  Повторите те же действия для PresentationFramework.dll: C:\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\PresentationFramework.dll.  
  
5.  Повторите те же действия для WindowsBase.dll: C:\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\ WindowsBase.dll.  
  
6.  Повторите те же действия для UIAutomationTypes.dll: C:\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\UIAutomationTypes.dll.  
  
7.  Повторите те же действия для UIAutomationProvider.dll: C:\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\UIAutomationProvider.dll.  
  
8.  Нажмите кнопку **Добавить новую ссылку**, выберите файл System.dll и нажмите кнопку **ОК**.  
  
9. Нажмите кнопку **ОК**, чтобы выйти из страницы свойств win32clock для добавления ссылок.  
  
 Наконец, добавьте `STAThreadAttribute` в метод `_tWinMain` для использования в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 Этот атрибут сообщает [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], что при инициализации [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)] следует использовать модель однопотокового подразделения \(STA\), которая необходима для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(и для [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\).  
  
## Создайте страницу Windows Presentation Framework  
 Далее, создайте библиотеку DLL, определяющую [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>.  Часто таким способом проще всего создать <xref:System.Windows.Controls.Page> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] как самостоятельное приложение, а затем написать и отладить часть [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  После этого проект можно преобразовать в DLL, щелкнув на нем правой кнопкой мыши, а затем щелкнув на кнопке **Свойства**, перейдя в приложение и изменив тип выходных данных на библиотеку классов Windows.  
  
 Проект DLL [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] затем может быть объединен с проектом [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] \(одно решение, которое содержит два проекта\) ― щелкните правой кнопкой мыши на решении и выберите **Добавить существующий проект**.  
  
 Чтобы использовать эту DLL\-библиотеку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] из проекта [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], необходимо добавить ссылку:  
  
1.  Щелкните правой кнопкой мыши на проекте win32clock и выберите **Ссылки...**.  
  
2.  Щелкните **Добавить новую ссылку**.  
  
3.  Перейдите на вкладку **Проекты**.  Выберите WPFClock, нажмите кнопку "ОК".  
  
4.  Нажмите кнопку **ОК**, чтобы выйти из страницы свойств win32clock для добавления ссылок.  
  
## HwndSource  
 Далее, воспользуйтесь <xref:System.Windows.Interop.HwndSource>, чтобы <xref:System.Windows.Controls.Page> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выглядел как HWND.  Добавьте этот блок кода в C\+\+ файл:  
  
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
  
 Это длинный фрагмент кода, к которому могут потребоваться некоторые объяснения.  Первая часть представляет собой различные операторы, поэтому не нужно полностью квалифицировать все вызовы:  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 Затем определяется функция, которая создает содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], помещает в него <xref:System.Windows.Interop.HwndSource> и возвращает HWND:  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 Сначала создается <xref:System.Windows.Interop.HwndSource>, чьи параметры аналогичны параметрам CreateWindow:  
  
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
  
 Затем создается класс содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] путем вызова его конструктора:  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 Затем страница соединяется с <xref:System.Windows.Interop.HwndSource>:  
  
```  
source->RootVisual = page;  
```  
  
 И в последней строке возвращается HWND для <xref:System.Windows.Interop.HwndSource>:  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## Размещение Hwnd  
 Теперь, когда создан HWND, содержащий часы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], необходимо поместить этот HWND в диалоговое окно [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Если бы было известно, где размещается HWND, то можно было бы просто передать его размер и расположение в функцию `GetHwnd`, определенную ранее.  Но поскольку для определения этого диалогового окна использовался файл ресурсов, точно не известно, где расположены HWND.  Можно воспользоваться редактором диалоговых окон [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] для размещения элемента управления STATIC [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], в котором должны пойти часы \("Вставьте часы здесь"\), и использовать его для размещения часов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Там, где выполняется обработка WM\_INITDIALOG, используется `GetDlgItem`, чтобы получить HWND для заместителя STATIC:  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 Затем вычисляется размер и положение этого местозаполнителя STATIC, чтобы можно было поместить часы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в этом месте:  
  
 RECT rectangle;  
  
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
  
 И создается HWND часов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в этом расположении:  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 Чтобы сделать это руководство интересным и создать настоящие часы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], необходимо создать элемент управления часов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в этой точке.  Это можно сделать в основном в разметке, со всего лишь несколькими обработчиками событий в коде.  Поскольку это руководство о взаимодействии, а не о разработке элементов управления, полный код для часов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляется здесь как блок кода, без отдельных указаний по его построению и без описания того, что означает каждая часть.  Вы можете поэкспериментировать с этим кодом для изменения внешнего вида и функциональных возможностей элемента управления.  
  
 Разметка:  
  
 [!code-xml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 Сопутствующий код:  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 Результат выглядит следующим образом:  
  
 ![Диалоговое окно “Дата и свойства времени”](../../../../docs/framework/wpf/advanced/media/interoparch08.png "InteropArch08")  
  
 Чтобы сравнить конечный результат с кодом, который создал данный снимок экрана, см. раздел [Пример Win32 Clock Interoperation](http://go.microsoft.com/fwlink/?LinkID=160051).  
  
## См. также  
 <xref:System.Windows.Interop.HwndSource>   
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051)