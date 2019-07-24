---
title: Пошаговое руководство. Размещение содержимого WPF в Win32
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: 02f0831b46b8087c48b86e83a4b20f94bf3b79d0
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401580"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>Пошаговое руководство. Размещение содержимого WPF в Win32
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако если вы существенно потратились на код [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], то добавление функциональности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в ваше приложение может быть более эффективно, чем переписывание исходного кода. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет простой механизм размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в окне.  
  
 В этом учебнике описывается, как написать пример приложения, [в котором размещается содержимое WPF, в примере окна Win32](https://go.microsoft.com/fwlink/?LinkID=160004), [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в котором содержимое размещается [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окне. Вы можете расширить этот пример для размещения любого окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Поскольку этот пример включает смешанный управляемый и неуправляемый код, приложение создается на [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)].  

<a name="requirements"></a>   
## <a name="requirements"></a>Требования  
 В этом учебнике предполагается, что вы знакомы с основами программирования в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Базовые сведения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] о программировании см. в разделе [Начало работы](../getting-started/index.md). Для ознакомления с [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] программированием необходимо ссылаться на любую из многочисленных книг по теме в определенных *окнах программирования* с помощью Чарльз Петцольд.  
  
 Поскольку пример, прилагаемый к этому учебнику, [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]реализован в, в этом учебнике предполагается знание [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] использования для [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]программирования API, а также понимание управляемого кода. Знакомство с [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] желательно, но не обязательно.  
  
> [!NOTE]
>  Этот учебник включает ряд примеров кода из связанного образца приложения. Однако для удобства чтения он не содержит полный пример кода. Полный пример кода см. в разделе [Размещение содержимого WPF в примере окна Win32](https://go.microsoft.com/fwlink/?LinkID=160004).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Основная процедура  
 В этом разделе описывается базовая процедура, используемая для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в окне. В остальных разделах подробно описывается каждый шаг.  
  
 Ключом к размещению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в окне является <xref:System.Windows.Interop.HwndSource> класс. Этот класс служит оболочкой [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] для содержимого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в окне, позволяя включать его в качестве дочернего окна. Следующий подход объединяет [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в одном приложении.  
  
1. Реализуйте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое как управляемый класс.  
  
2. Реализуйте приложение [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] с помощью [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]. Если вы начинаете с существующего приложения и неуправляемого кода [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], то обычно можете позволить приложению вызывать управляемый код, изменив параметры проекта, чтобы включить флаг компилятора `/clr`.  
  
3. Установите в качестве потоковой модели однопотоковое подразделение (STA).  
  
4. Обработайте уведомление [WM_CREATE](/windows/desktop/winmsg/wm-create)в процедуре окна и выполните следующие действия.  
  
    1. Создайте новый объект <xref:System.Windows.Interop.HwndSource> с родительским окном в качестве его параметра `parent`.  
  
    2. Создайте экземпляр вашего класса содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3. Присвойте ссылку на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объект <xref:System.Windows.Interop.HwndSource.RootVisual%2A> содержимого свойству <xref:System.Windows.Interop.HwndSource>объекта.  
  
    4. Получите HWND для содержимого. Свойство <xref:System.Windows.Interop.HwndSource.Handle%2A> объекта <xref:System.Windows.Interop.HwndSource> содержит дескриптор окна (HWND). Чтобы получить HWND, который можно использовать в неуправляемой части приложения, приведите `Handle.ToPointer()` к HWND.  
  
5. Реализуйте управляемый класс, содержащий статическое поле для хранения ссылки на ваше содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот класс позволяет получить ссылку на содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] из вашего кода [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
6. Назначьте содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] этому статическому полю.  
  
7. Получение уведомлений из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого путем присоединения обработчика к одному или нескольким [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] событиям.  
  
8. Взаимодействуйте с содержимым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью ссылки, которую вы сохранили в статическом поле, для задания свойств и т. д.  
  
> [!NOTE]
>  Можно также использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализации содержимого. Однако его необходимо компилировать отдельно как [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)] и ссылаться на эту [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] из своего приложения [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Оставшаяся часть процедуры аналогична описанной выше.

<a name="implementing_the_application"></a>
## <a name="implementing-the-host-application"></a>Реализация ведущего приложения
 В этом разделе описывается размещение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого в базовом [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] приложении. Само содержимое реализуется в [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] как управляемый класс. Большей частью это просто программирование [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Ключевые аспекты реализации содержимого обсуждаются в разделе [Реализация содержимого WPF](#implementing_the_wpf_page).

<a name="autoNestedSectionsOUTLINE1"></a>
- [Базовое приложение](#the_basic_application)

- [Размещение содержимого WPF](#hosting_the_wpf_page)

- [Хранение ссылки на содержимое WPF](#holding_a_reference)

- [Взаимодействие с содержимым WPF](#communicating_with_the_page)

<a name="the_basic_application"></a>
### <a name="the-basic-application"></a>Базовое приложение
 Начальной точкой для ведущего приложения было создание шаблона Visual Studio 2005.

1. Откройте Visual Studio 2005 и выберите в меню **файл** пункт **создать проект** .

2. Выберите **Win32** из списка [!INCLUDE[TLA2#tla_visualcpp](../../../../includes/tla2sharptla-visualcpp-md.md)] типов проектов. Если язык по умолчанию не [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)]указан, эти типы проектов будут находиться в разделе **другие языки**.

3. Выберите шаблон **проекта Win32** , назначьте имя проекту и нажмите кнопку **ОК** , чтобы запустить **Мастер приложений Win32**.

4. Примите параметры мастера по умолчанию и нажмите кнопку **Готово** , чтобы запустить проект.

 Этот шаблон создает базовое приложение [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], включая:

- точку входа для приложения;

- окно со связанной процедурой окна (WndProc);

- Меню с заголовками **файлов** и **справки** . В меню **файл** есть элемент **Exit** , который закрывает приложение. Меню **Справка** содержит элемент **About** , который запускает простое диалоговое окно.

 Прежде чем приступить к написанию кода [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для размещения содержимого, необходимо внести два изменения в базовый шаблон.

 Сначала следует скомпилировать проект как управляемый код. По умолчанию проект компилируется как неуправляемый код. Однако поскольку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализуется в управляемом коде, проект должен быть скомпилирован соответствующим образом.

1. Щелкните правой кнопкой мыши имя проекта в **Обозреватель решений** и выберите в контекстном меню пункт **свойства** , чтобы открыть диалоговое окно **страницы свойств** .

2. Выберите **Свойства конфигурации** в представлении в виде дерева в левой области.

3. Выберите поддержку **среды CLR** из списка **значений по умолчанию для проекта** на правой панели.

4. В раскрывающемся списке выберите вариант **Поддержка CLR (Common Language Runtime)** .

> [!NOTE]
>  Этот флаг компилятора позволяет использовать управляемый код в приложении, но ваш неуправляемый код будет продолжать компилироваться как раньше.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует потоковую модель однопотокового подразделения (STA). Чтобы правильно работать с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] кодом содержимого, необходимо задать потоковую модель приложения в STA, применив атрибут к точке входа.

 [!code-cpp[Win32HostingWPFPage#WinMain](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]

<a name="hosting_the_wpf_page"></a>
### <a name="hosting-the-wpf-content"></a>Размещение содержимого WPF
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Содержимое представляет собой простое приложение для записи адреса. Оно состоит из нескольких элементов управления <xref:System.Windows.Controls.TextBox> для получения имени пользователя, адреса и т. д. Также есть два <xref:System.Windows.Controls.Button> элемента управления: **ОК** и **Отмена**. Когда пользователь нажимает кнопку **ОК**, обработчик <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий кнопки собирает данные из <xref:System.Windows.Controls.TextBox> элементов управления, назначает их соответствующим свойствам и создает пользовательское событие `OnButtonClicked`. Когда пользователь нажимает кнопку **Отмена**, обработчик просто вызывает `OnButtonClicked`. Объект аргумента события для `OnButtonClicked` содержит логическое поле, которое указывает, какая кнопка была нажата.

 Код для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого реализуется в обработчике уведомления [WM_CREATE](/windows/desktop/winmsg/wm-create) в главном окне.

 [!code-cpp[Win32HostingWPFPage#WMCreate](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]

 Метод принимает сведения о размере и положении, а также маркер родительского окна и возвращает маркер окна размещенного [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого. `GetHwnd`

> [!NOTE]
>  Нельзя использовать директиву `#using` для пространства имен `System::Windows::Interop`. Иначе будет создан конфликт имен между структурой <xref:System.Windows.Interop.MSG> в этом пространстве имен и структурой MSG, объявленной в winuser.h. Вместо этого необходимо использовать полные имена для доступа к содержимому этого пространства имен.

 [!code-cpp[Win32HostingWPFPage#GetHwnd](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]

 Вы не можете разместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое непосредственно в окне приложения. Вместо этого сначала создайте объект <xref:System.Windows.Interop.HwndSource>, который должен включать в себя содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот объект, по сути, является окном, предназначенным [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для размещения содержимого. Вы размещаете <xref:System.Windows.Interop.HwndSource> объект в родительском окне, создав его в качестве дочернего [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] для окна, которое является частью приложения. Параметры конструктора <xref:System.Windows.Interop.HwndSource> содержат в основном те же сведения, которые будут передаваться в CreateWindow при создании дочернего окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].

 Затем создайте экземпляр [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объекта Content. В этом случае содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализуется как отдельный класс `WPFPage`, использующий [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]. Можно также реализовать содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Однако для этого необходимо настроить отдельный проект и построить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое в [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]виде. Вы можете добавить ссылку на эту [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] в свой проект и использовать эту ссылку для создания экземпляра содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Содержимое отображается в дочернем окне путем назначения ссылки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на содержимое <xref:System.Windows.Interop.HwndSource.RootVisual%2A> свойству объекта <xref:System.Windows.Interop.HwndSource>.

 Следующая строка кода присоединяет обработчик событий `WPFButtonClicked` к событию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого `OnButtonClicked`. Этот обработчик вызывается, когда пользователь нажимает кнопку **ОК** или **Отмена** . Дополнительные сведения об этом обработчике событий см. в разделе [communicating_with_the_WPF Content](#communicating_with_the_page) .

 В последней строке кода показан возврат дескриптора окна (HWND), который связан с объектом <xref:System.Windows.Interop.HwndSource>. Вы можете использовать этот дескриптор из своего кода [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] для отправки сообщений в размещенное окно, хотя в этом примере так не делается. Объект <xref:System.Windows.Interop.HwndSource> инициирует событие каждый раз при получении сообщения. Для обработки сообщений вызовите метод <xref:System.Windows.Interop.HwndSource.AddHook%2A>, чтобы присоединить обработчик сообщений, а затем обрабатывать сообщения в этом обработчике.

<a name="holding_a_reference"></a>
### <a name="holding-a-reference-to-the-wpf-content"></a>Хранение ссылки на содержимое WPF
 Для многих приложений потребуется взаимодействовать с содержимым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позднее. Например, может возникнуть необходимость изменить свойства содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] или разместить в объекте <xref:System.Windows.Interop.HwndSource> другое содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Для этого потребуется ссылка на объект <xref:System.Windows.Interop.HwndSource> или содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Объект <xref:System.Windows.Interop.HwndSource> и связанное с ним содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] остаются в памяти до уничтожения дескриптора окна. Однако переменная, которая назначается объекту <xref:System.Windows.Interop.HwndSource>, выйдет из области действия сразу после возврата из процедуры окна. Обычный способ решения этой проблемы с приложениями [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] заключается в использовании статической или глобальной переменной. К сожалению, нельзя назначать управляемый объект таким типам переменных. Вы можете назначить дескриптор окна, связанный с объектом <xref:System.Windows.Interop.HwndSource>, глобальной или статической переменной, но которая не предоставляет доступ к самому объекту.

 Самым простым решением этой проблемы является реализация управляемого класса, который содержит набор статических полей для хранения ссылок на любые управляемые объекты, к которым требуется доступ. В данном примере используется класс `WPFPageHost` для хранения ссылки на содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], а также начальные значения его свойств, которые могут быть изменены пользователем позднее. Это определяется в заголовке.

 [!code-cpp[Win32HostingWPFPage#WPFPageHost](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]

 В последней части `GetHwnd` функция присваивает значения этим полям для последующего использования, пока `myPage` остается в области.

<a name="communicating_with_the_page"></a>
### <a name="communicating-with-the-wpf-content"></a>Взаимодействие с содержимым WPF
 Существует два типа взаимодействия с содержимым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Приложение получает информацию из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого, когда пользователь нажимает кнопки **ОК** или **Отмена** . Приложение также имеет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], в котором пользователь может изменять изменять различные свойства содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такие как цвет фона или размер шрифта по умолчанию.

 Как упоминалось выше, когда пользователь нажимает одну из кнопок, содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вызывает событие `OnButtonClicked`. Приложение присоединяет обработчик к этому событию, чтобы получать эти уведомления. Если была нажата кнопка **ОК** , обработчик получает сведения о пользователе из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого и отображает его в наборе статических элементов управления.

 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]

 Обработчик получает объект аргумента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] пользовательского события из содержимого `MyPageEventArgs`. `IsOK` Свойство объекта устанавливается в `true` значение, если была нажата кнопка « **ОК** », и `false` если была нажата кнопка « **Отмена** ».

 Если была нажата кнопка **ОК** , обработчик получает ссылку на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое из класса контейнера. Затем он собирает сведения о пользователе, которые хранятся в соответствующих свойствах содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и использует статические элементы управления для отображения этих сведений в родительском окне. Поскольку данные содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] хранятся в виде управляемых строк, они должны быть маршалированы для использования элементом управления [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Если была нажата кнопка **Отмена** , обработчик удаляет данные из статических элементов управления.

 Приложение [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] предоставляет набор переключателей, с помощью которых пользователь может изменять цвет фона для содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и некоторые свойства, связанные со шрифтами. Следующий пример представляет выдержку из процедуры окна приложения (WndProc), содержащую обработку его сообщения, которая устанавливает разные свойства в различных сообщениях, включая цвет фона. Остальные примеры похожи и не приводятся. Подробные сведения и контекст см. в полном примере.

 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]

 Чтобы задать цвет фона, получите ссылку на содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (`hostedPage`) из `WPFPageHost` и установите в свойстве цвета фона соответствующий цвет. В примере используется три варианта цвета: исходный цвет, светло-зеленый и светло-оранжевый. Исходный цвет фона хранится в виде статического поля в классе `WPFPageHost`. Чтобы задать другие два цвета, создайте новый объект <xref:System.Windows.Media.SolidColorBrush> и передайте в конструктор значение статического цвета из объекта <xref:System.Windows.Media.Colors>.

<a name="implementing_the_wpf_page"></a>
## <a name="implementing-the-wpf-page"></a>Реализация страницы WPF
 Вы можете размещать и использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое без каких бы то ни было знаний о фактической реализации. Если содержимое было упаковано в отдельном [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]виде, оно могло быть встроено в любой язык среды CLR. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ниже приведено краткое пошаговое описание реализации [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)], которая используется в данном примере. Этот подраздел состоит из следующих подразделов.

<a name="autoNestedSectionsOUTLINE2"></a>
- [Макет](#page_layout)

- [Возврат данных в главное окно](#returning_data_to_window)

- [Установка свойств WPF](#set_page_properties)

<a name="page_layout"></a>
### <a name="layout"></a>Макет
 Элементы содержимого состоят из пяти <xref:System.Windows.Controls.TextBox> элементов управления со связанными <xref:System.Windows.Controls.Label> элементами управления: [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Имя, адрес, город, штат и ZIP-файл. Есть также два <xref:System.Windows.Controls.Button> элемента управления: **ОК** и **Отмена** .

 Содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализовано в классе `WPFPage`. Макет обрабатывается с помощью элемента макета <xref:System.Windows.Controls.Grid>. Этот класс наследует от <xref:System.Windows.Controls.Grid>, который фактически делает его корневым элементом содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 Конструктор содержимого принимает требуемую ширину и высоту и <xref:System.Windows.Controls.Grid> соответствующим образом изменяет размеры. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Затем он определяет базовый <xref:System.Windows.Controls.ColumnDefinition> макет, создавая набор объектов и <xref:System.Windows.Controls.RowDefinition> <xref:System.Windows.Controls.Grid> и добавляя их в базу <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> объекта и <xref:System.Windows.Controls.Grid.RowDefinitions%2A> коллекции соответственно. Это задает сетку из пяти строк и семи столбцов с размерами, определяемыми содержимым ячеек.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]

 Затем конструктор добавляет элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в объект <xref:System.Windows.Controls.Grid>. Первый элемент — это текст заголовка, который является элементом управления <xref:System.Windows.Controls.Label>, выравниваемым по центру в первой строке сетки.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]

 Следующая строка содержит элемент управления <xref:System.Windows.Controls.Label> «Имя» и связанный с ним элемент управления <xref:System.Windows.Controls.TextBox>. Так как тот же код используется для каждой пары «метка/текстовое поле», он помещается в пару закрытых методов и используется для всех пяти пар «метка/текстовое поле». Эти методы создают соответствующий элемент управления и вызывают класс <xref:System.Windows.Controls.Grid> статического метода <xref:System.Windows.Controls.Grid.SetColumn%2A> и методы <xref:System.Windows.Controls.Grid.SetRow%2A> для размещения элементов управления в соответствующую ячейку. После создания элемента управления в примере вызывается метод <xref:System.Windows.Controls.UIElementCollection.Add%2A> в свойстве <xref:System.Windows.Controls.Panel.Children%2A> объекта <xref:System.Windows.Controls.Grid> для добавления элемента управления в сетку. Для добавления оставшихся пар «метка/текстовое поле» используется аналогичный код. Подробности см. в примере кода.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]

 Реализация этих двух методов выглядит следующим образом:

 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]

 Наконец, в примере добавляются кнопки **ОК** и **Отмена** и прикрепляется обработчик событий к их <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событиям.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]

<a name="returning_data_to_window"></a>
### <a name="returning-the-data-to-the-host-window"></a>Возврат данных в главное окно
 При нажатии одной из кнопок вызывается ее событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. Главное окно может просто присоединять обработчики к этим событиям и получать данные напрямую из элементов управления <xref:System.Windows.Controls.TextBox>. В примере используется несколько менее прямой подход. Он обрабатывает объект <xref:System.Windows.Controls.Primitives.ButtonBase.Click> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внутри содержимого, а затем вызывает пользовательское [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] событие `OnButtonClicked`для уведомления содержимого. Это позволяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимому выполнять некоторые проверки параметров перед уведомлением узла. Обработчик получает текст из элементов управления <xref:System.Windows.Controls.TextBox> и назначает его общим свойствам, из которых узел может получать сведения.

 Объявление события в WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]

 Обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> в WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]

<a name="set_page_properties"></a>
### <a name="setting-the-wpf-properties"></a>Установка свойств WPF
 Узел позволяет пользователю изменять несколько [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойств содержимого. [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Со стороны [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] это просто изменение свойств. Реализация в классе содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] несколько более сложная, поскольку нет одного глобального свойства, которое управляет шрифтами для всех элементов управления. Вместо этого для каждого элемента управления изменяется соответствующее свойство в методах доступа set этого свойства. В следующем примере показан код для `DefaultFontFamily` свойства. Задание свойства вызывает закрытый метод, который в свою очередь устанавливает свойства <xref:System.Windows.Controls.Control.FontFamily%2A> для различных элементов управления.

 Из WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]

 Из WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]

## <a name="see-also"></a>См. также

- <xref:System.Windows.Interop.HwndSource>
- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
