---
title: Пошаговое руководство. Размещение содержимого WPF в Win32
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: 429acf6e3b37f5532e031fdef999d252a3aae3cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549455"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>Пошаговое руководство. Размещение содержимого WPF в Win32
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако если вы существенно потратились на код [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], то добавление функциональности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в ваше приложение может быть более эффективно, чем переписывание исходного кода. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет простой механизм для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна.  
  
 Этот учебник описывает, как написать пример приложения [размещение содержимого WPF в окне Win32-пример](http://go.microsoft.com/fwlink/?LinkID=160004), что узлы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна. Вы можете расширить этот пример для размещения любого окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Поскольку этот пример включает смешанный управляемый и неуправляемый код, приложение создается на [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)].  
  
 
  
<a name="requirements"></a>   
## <a name="requirements"></a>Требования  
 В этом учебнике предполагается, что вы знакомы с основами программирования в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Основные сведения о [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] программирования, в разделе [Приступая к работе](../../../../docs/framework/wpf/getting-started/index.md). Основные сведения о [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] программирования, вы должны ссылаться на любые многочисленные книги по вопросам, в частности *программирования Windows* , Чарльз Петцольд.  
  
 Поскольку образец, сопровождающий это руководство реализован в [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)], это руководство предполагает знакомство с использованием [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] программу [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] плюс понимание программирования управляемого кода. Знакомство с [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] желательно, но не обязательно.  
  
> [!NOTE]
>  Этот учебник включает ряд примеров кода из связанного образца приложения. Однако для удобства чтения он не содержит полный пример кода. Полный образец кода в разделе [размещение WPF содержимого в окне Win32-пример](http://go.microsoft.com/fwlink/?LinkID=160004).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Основная процедура  
 В этом разделе описывается основная процедура используется для узла [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна. В остальных разделах подробно описывается каждый шаг.  
  
 Ключом к размещению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окно <xref:System.Windows.Interop.HwndSource> класса. Этот класс переносит [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окно, в котором он должен быть включен в ваш [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] как дочернего окна. Следующий подход объединяет [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в одном приложении.  
  
1.  Реализуйте вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое, так как управляемый класс.  
  
2.  Реализуйте приложение [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] с помощью [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]. Если вы начинаете с существующего приложения и неуправляемого кода [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], то обычно можете позволить приложению вызывать управляемый код, изменив параметры проекта, чтобы включить флаг компилятора `/clr`.  
  
3.  Установите в качестве потоковой модели однопотоковое подразделение (STA).  
  
4.  Обрабатывать [WM_CREATE](http://msdn.microsoft.com/library/ms632619.aspx)уведомления в процедуру окна и выполните следующие:  
  
    1.  Создайте новый объект <xref:System.Windows.Interop.HwndSource> с родительским окном в качестве его параметра `parent`.  
  
    2.  Создайте экземпляр вашего класса содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3.  Присвойте ссылку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объект содержимого <xref:System.Windows.Interop.HwndSource.RootVisual%2A> свойство <xref:System.Windows.Interop.HwndSource>.  
  
    4.  Получите HWND для содержимого. Свойство <xref:System.Windows.Interop.HwndSource.Handle%2A> объекта <xref:System.Windows.Interop.HwndSource> содержит дескриптор окна (HWND). Чтобы получить HWND, который можно использовать в неуправляемой части приложения, приведите `Handle.ToPointer()` к HWND.  
  
5.  Реализуйте управляемый класс, содержащий статическое поле для хранения ссылки на ваше содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот класс позволяет получить ссылку на содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] из вашего кода [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
6.  Назначьте содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] этому статическому полю.  
  
7.  Получение уведомлений от [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого путем присоединения обработчика для одного или нескольких [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] события.  
  
8.  Взаимодействуйте с содержимым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью ссылки, которую вы сохранили в статическом поле, для задания свойств и т. д.  
  
> [!NOTE]
>  Можно также использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для реализации вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого. Однако его необходимо компилировать отдельно как [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)] и ссылаться на эту [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] из своего приложения [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Оставшаяся часть процедуры аналогична описанной выше.  
  
<a name="implementing_the_application"></a>   
## <a name="implementing-the-host-application"></a>Реализация ведущего приложения  
 В этом разделе описываются способы узла [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого в основном [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложения. Само содержимое реализуется в [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] как управляемый класс. Большей частью это просто программирование [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Ключевые аспекты реализации содержимого обсуждаются в [реализация содержимого WPF](#implementing_the_wpf_page).  
  
<a name="autoNestedSectionsOUTLINE1"></a>   
-   [Базовое приложение](#the_basic_application)  
  
-   [Размещение содержимого WPF](#hosting_the_wpf_page)  
  
-   [Хранение ссылки на содержимое WPF](#holding_a_reference)  
  
-   [Взаимодействие с содержимым WPF](#communicating_with_the_page)  
  
<a name="the_basic_application"></a>   
### <a name="the-basic-application"></a>Базовое приложение  
 Отправной точкой для ведущего приложения было создание шаблона [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].  
  
1.  Откройте [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)]и выберите **новый проект** из **файл** меню.  
  
2.  Выберите **Win32** из списка [!INCLUDE[TLA2#tla_visualcpp](../../../../includes/tla2sharptla-visualcpp-md.md)] типов проектов. Если язык по умолчанию не [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)], вы найдете этих типов проектов в разделе **другие языки**.  
  
3.  Выберите **проект Win32** шаблона, назначить имя проекта и нажмите кнопку **ОК** для запуска **мастер приложений Win32**.  
  
4.  Примите параметры мастера по умолчанию и нажмите кнопку **Готово** для запуска проекта.  
  
 Этот шаблон создает базовое приложение [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], включая:  
  
-   точку входа для приложения;  
  
-   окно со связанной процедурой окна (WndProc);  
  
-   Меню с **файл** и **справки** заголовков. **Файл** меню содержит **выхода** элемента, который закрывает приложение. **Справки** меню содержит **о** элемент, который запускает простое диалоговое окно.  
  
 Перед началом написания кода для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого, необходимо внести два изменения в базовый шаблон.  
  
 Сначала следует скомпилировать проект как управляемый код. По умолчанию проект компилируется как неуправляемый код. Однако поскольку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализуется в управляемом коде, проект должен быть скомпилирован соответствующим образом.  
  
1.  Щелкните правой кнопкой мыши имя проекта в **обозревателе решений** и выберите **свойства** из контекстного меню для запуска **страницы свойств** диалоговое окно.  
  
2.  Выберите **свойства конфигурации** из представления дерева в левой области.  
  
3.  Выберите **общеязыковая среда выполнения** поддержки с **проекта по умолчанию** списка в правой области.  
  
4.  Выберите **Поддержка Common Language Runtime (/ clr)** из раскрывающегося списка.  
  
> [!NOTE]
>  Этот флаг компилятора позволяет использовать управляемый код в приложении, но ваш неуправляемый код будет продолжать компилироваться как раньше.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует потоковую модель однопотокового подразделения (STA). Для правильной работы с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого кода задается потоковую модель приложения в STA путем применения атрибута к точке входа.  
  
 [!code-cpp[Win32HostingWPFPage#WinMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]  
  
<a name="hosting_the_wpf_page"></a>   
### <a name="hosting-the-wpf-content"></a>Размещение содержимого WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Содержимое является простым приложением ввода адреса. Оно состоит из нескольких элементов управления <xref:System.Windows.Controls.TextBox> для получения имени пользователя, адреса и т. д. Существуют также два <xref:System.Windows.Controls.Button> элементов управления, **ОК** и **отменить**. Когда пользователь щелкает **ОК**, кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий собирает данные из <xref:System.Windows.Controls.TextBox> элементы управления, назначает его соответствующие свойства и вызывает пользовательское событие `OnButtonClicked`. Когда пользователь щелкает **отменить**, обработчик просто вызывает `OnButtonClicked`. Объект аргумента события для `OnButtonClicked` содержит логическое поле, которое указывает, какая кнопка была нажата.  
  
 Код для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое реализуется с помощью обработчика [WM_CREATE](http://msdn.microsoft.com/library/ms632619.aspx) уведомление на главного окна.  
  
 [!code-cpp[Win32HostingWPFPage#WMCreate](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]  
  
 `GetHwnd` Метод принимает размер и положение сведения, а также родительский дескриптор окна и возвращает дескриптор окна для размещенного [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого.  
  
> [!NOTE]
>  Нельзя использовать директиву `#using` для пространства имен `System::Windows::Interop`. Иначе будет создан конфликт имен между структурой <xref:System.Windows.Interop.MSG> в этом пространстве имен и структурой MSG, объявленной в winuser.h. Вместо этого необходимо использовать полные имена для доступа к содержимому этого пространства имен.  
  
 [!code-cpp[Win32HostingWPFPage#GetHwnd](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]  
  
 Невозможно разместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое непосредственно в вашем окне приложения. Вместо этого сначала создайте объект <xref:System.Windows.Interop.HwndSource>, который должен включать в себя содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот объект по сути является окно, предназначенное для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого. Размещать <xref:System.Windows.Interop.HwndSource> объекта в родительском окне, создав его в качестве дочернего элемента [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окно, которое является частью приложения. Параметры конструктора <xref:System.Windows.Interop.HwndSource> содержат в основном те же сведения, которые будут передаваться в CreateWindow при создании дочернего окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
 Затем создать экземпляр [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого объекта. В этом случае содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализуется как отдельный класс `WPFPage`, использующий [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]. Можно также реализовать содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Однако для этого необходимо настроить отдельный проект и построить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое, так как [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]. Вы можете добавить ссылку на эту [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] в свой проект и использовать эту ссылку для создания экземпляра содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Отобразить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого в ваше дочернее окно, назначив ссылку на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого <xref:System.Windows.Interop.HwndSource.RootVisual%2A> свойство <xref:System.Windows.Interop.HwndSource>.  
  
 Следующая строка кода присоединяет обработчик событий `WPFButtonClicked` к событию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого `OnButtonClicked`. Этот обработчик вызывается, когда пользователь щелкает **ОК** или **отменить** кнопки. В разделе [communicating_with_the_WPF содержимого](#communicating_with_the_page) более подробное описание этого обработчика событий.  
  
 В последней строке кода показан возврат дескриптора окна (HWND), который связан с объектом <xref:System.Windows.Interop.HwndSource>. Вы можете использовать этот дескриптор из своего кода [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] для отправки сообщений в размещенное окно, хотя в этом примере так не делается. Объект <xref:System.Windows.Interop.HwndSource> инициирует событие каждый раз при получении сообщения. Для обработки сообщений вызовите метод <xref:System.Windows.Interop.HwndSource.AddHook%2A>, чтобы присоединить обработчик сообщений, а затем обрабатывать сообщения в этом обработчике.  
  
<a name="holding_a_reference"></a>   
### <a name="holding-a-reference-to-the-wpf-content"></a>Хранение ссылки на содержимое WPF  
 Для многих приложений потребуется взаимодействовать с содержимым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позднее. Например, может возникнуть необходимость изменить свойства содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] или разместить в объекте <xref:System.Windows.Interop.HwndSource> другое содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Для этого потребуется ссылка на объект <xref:System.Windows.Interop.HwndSource> или содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Объект <xref:System.Windows.Interop.HwndSource> и связанное с ним содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] остаются в памяти до уничтожения дескриптора окна. Однако переменная, которая назначается объекту <xref:System.Windows.Interop.HwndSource>, выйдет из области действия сразу после возврата из процедуры окна. Обычный способ решения этой проблемы с приложениями [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] заключается в использовании статической или глобальной переменной. К сожалению, нельзя назначать управляемый объект таким типам переменных. Вы можете назначить дескриптор окна, связанный с объектом <xref:System.Windows.Interop.HwndSource>, глобальной или статической переменной, но которая не предоставляет доступ к самому объекту.  
  
 Самым простым решением этой проблемы является реализация управляемого класса, который содержит набор статических полей для хранения ссылок на любые управляемые объекты, к которым требуется доступ. В данном примере используется класс `WPFPageHost` для хранения ссылки на содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], а также начальные значения его свойств, которые могут быть изменены пользователем позднее. Это определяется в заголовке.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageHost](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]  
  
 В последней части `GetHwnd` функция присваивает значения этим полям для последующего использования, пока `myPage` остается в области.  
  
<a name="communicating_with_the_page"></a>   
### <a name="communicating-with-the-wpf-content"></a>Взаимодействие с содержимым WPF  
 Существует два типа взаимодействия с содержимым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Приложение получает информацию из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого, когда пользователь щелкает **ОК** или **отменить** кнопки. Приложение также имеет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], в котором пользователь может изменять изменять различные свойства содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такие как цвет фона или размер шрифта по умолчанию.  
  
 Как упоминалось выше, когда пользователь нажимает одну из кнопок, содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вызывает событие `OnButtonClicked`. Приложение присоединяет обработчик к этому событию, чтобы получать эти уведомления. Если **ОК** кнопка была нажата, обработчик получает сведения о пользователе из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого и отображает его в наборе статических элементов управления.  
  
 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]  
  
 Обработчик получает объект аргумента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] пользовательского события из содержимого `MyPageEventArgs`. Объект `IsOK` свойству `true` Если **ОК** была нажата кнопка, и `false` Если **отменить** была нажата кнопка.  
  
 Если **ОК** кнопка была нажата, обработчик получает ссылку на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого из класса контейнера. Затем он собирает сведения о пользователе, которые хранятся в соответствующих свойствах содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и использует статические элементы управления для отображения этих сведений в родительском окне. Поскольку данные содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] хранятся в виде управляемых строк, они должны быть маршалированы для использования элементом управления [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Если **отменить** кнопка была нажата, обработчик удаляет данные из статических элементов управления.  
  
 Приложение [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] предоставляет набор переключателей, с помощью которых пользователь может изменять цвет фона для содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и некоторые свойства, связанные со шрифтами. Следующий пример представляет выдержку из процедуры окна приложения (WndProc), содержащую обработку его сообщения, которая устанавливает разные свойства в различных сообщениях, включая цвет фона. Остальные примеры похожи и не приводятся. Подробные сведения и контекст см. в полном примере.  
  
 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]  
  
 Чтобы задать цвет фона, получите ссылку на содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (`hostedPage`) из `WPFPageHost` и установите в свойстве цвета фона соответствующий цвет. В примере используется три варианта цвета: исходный цвет, светло-зеленый и светло-оранжевый. Исходный цвет фона хранится в виде статического поля в классе `WPFPageHost`. Чтобы задать другие два цвета, создайте новый объект <xref:System.Windows.Media.SolidColorBrush> и передайте в конструктор значение статического цвета из объекта <xref:System.Windows.Media.Colors>.  
  
<a name="implementing_the_wpf_page"></a>   
## <a name="implementing-the-wpf-page"></a>Реализация страницы WPF  
 Вы можете размещать и использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого без знания о фактической реализации. Если [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое было упаковано в отдельном [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], он может быть встроено в любом [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] языка. Ниже приведено краткое пошаговое описание реализации [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)], которая используется в данном примере. Этот подраздел состоит из следующих подразделов.  
  
<a name="autoNestedSectionsOUTLINE2"></a>   
-   [Макет](#page_layout)  
  
-   [Возврат данных в главное окно](#returning_data_to_window)  
  
-   [Установка свойств WPF](#set_page_properties)  
  
<a name="page_layout"></a>   
### <a name="layout"></a>Макет  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Элементов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое состоят из пяти <xref:System.Windows.Controls.TextBox> элементы управления, с помощью связанных <xref:System.Windows.Controls.Label> элементов управления: имя, адрес, Город, состояние и Zip. Существуют также два <xref:System.Windows.Controls.Button> элементов управления, **ОК** и **Отмена**  
  
 Содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализовано в классе `WPFPage`. Макет обрабатывается с помощью элемента макета <xref:System.Windows.Controls.Grid>. Этот класс наследует от <xref:System.Windows.Controls.Grid>, который фактически делает его корневым элементом содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Содержимого конструктор принимает требуемые ширину и высоту и размеры <xref:System.Windows.Controls.Grid> соответствующим образом. Затем он определяет базовый макет, создавая набор <xref:System.Windows.Controls.ColumnDefinition> и <xref:System.Windows.Controls.RowDefinition> объектов и добавления их в <xref:System.Windows.Controls.Grid> базовый объект <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> и <xref:System.Windows.Controls.Grid.RowDefinitions%2A> коллекций, соответственно. Это задает сетку из пяти строк и семи столбцов с размерами, определяемыми содержимым ячеек.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]  
  
 Затем конструктор добавляет элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в объект <xref:System.Windows.Controls.Grid>. Первый элемент — это текст заголовка, который является элементом управления <xref:System.Windows.Controls.Label>, выравниваемым по центру в первой строке сетки.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]  
  
 Следующая строка содержит элемент управления <xref:System.Windows.Controls.Label> «Имя» и связанный с ним элемент управления <xref:System.Windows.Controls.TextBox>. Так как тот же код используется для каждой пары «метка/текстовое поле», он помещается в пару закрытых методов и используется для всех пяти пар «метка/текстовое поле». Эти методы создают соответствующий элемент управления и вызывают класс <xref:System.Windows.Controls.Grid> статического метода <xref:System.Windows.Controls.Grid.SetColumn%2A> и методы <xref:System.Windows.Controls.Grid.SetRow%2A> для размещения элементов управления в соответствующую ячейку. После создания элемента управления в примере вызывается метод <xref:System.Windows.Controls.UIElementCollection.Add%2A> в свойстве <xref:System.Windows.Controls.Panel.Children%2A> объекта <xref:System.Windows.Controls.Grid> для добавления элемента управления в сетку. Для добавления оставшихся пар «метка/текстовое поле» используется аналогичный код. Подробности см. в примере кода.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]  
  
 Реализация этих двух методов выглядит следующим образом:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]  
  
 Наконец, в этом примере добавляется **ОК** и **отменить** кнопок и присоединяет обработчик событий к их <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]  
  
<a name="returning_data_to_window"></a>   
### <a name="returning-the-data-to-the-host-window"></a>Возврат данных в главное окно  
 При нажатии одной из кнопок вызывается ее событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. Главное окно может просто присоединять обработчики к этим событиям и получать данные напрямую из элементов управления <xref:System.Windows.Controls.TextBox>. В примере используется несколько менее прямой подход. Он обрабатывает <xref:System.Windows.Controls.Primitives.ButtonBase.Click> в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] контента, а затем вызывает пользовательское событие `OnButtonClicked`, чтобы уведомить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого. Это позволяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого сделать определенную проверку параметров перед уведомлением узла. Обработчик получает текст из элементов управления <xref:System.Windows.Controls.TextBox> и назначает его общим свойствам, из которых узел может получать сведения.  
  
 Объявление события в WPFPage.h:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]  
  
 Обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> в WPFPage.cpp:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]  
  
<a name="set_page_properties"></a>   
### <a name="setting-the-wpf-properties"></a>Установка свойств WPF  
 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Узел позволяет пользователю изменить несколько [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства содержимого. Со стороны [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] это просто изменение свойств. Реализация в классе содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] несколько более сложная, поскольку нет одного глобального свойства, которое управляет шрифтами для всех элементов управления. Вместо этого для каждого элемента управления изменяется соответствующее свойство в методах доступа set этого свойства. В следующем примере показано код `DefaultFontFamily` свойство. Задание свойства вызывает закрытый метод, который в свою очередь устанавливает свойства <xref:System.Windows.Controls.Control.FontFamily%2A> для различных элементов управления.  
  
 Из WPFPage.h:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]  
  
 Из WPFPage.cpp:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Interop.HwndSource>  
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
