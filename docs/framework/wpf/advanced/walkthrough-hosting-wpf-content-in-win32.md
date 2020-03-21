---
title: Размещение контента WPF в Win32
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: 8a5d556abf49c9c1f49e7853e752ebc5248d1101
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186071"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>Пошаговое руководство. Размещение содержимого WPF в Win32
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако, если у вас есть значительные инвестиции в код [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Win32, возможно, было бы более эффективно добавлять функциональность в приложение, а не переписывать исходный код. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]обеспечивает простой механизм [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для размещения контента в окне Win32.  
  
 В этом учебнике описывается, как написать образец приложения, хостинг [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [WPF Содержание в Win32 Окно Образец](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32HostingWPFPage), который размещает содержание в окне Win32. Вы можете расширить этот образец, чтобы разместить любое окно Win32. Поскольку это включает в себя смешивание управляемого и неуправляемого кода, приложение написано в C-CLI.  

<a name="requirements"></a>
## <a name="requirements"></a>Требования  
 Этот учебник предполагает базовое знакомство с программированием win32 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и Win32. Для базового [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] введения в программирование, см. [Getting Started](../getting-started/index.md) Для введения в программирование Win32, вы должны ссылаться на любой из многочисленных книг по этому вопросу, в *частности, программирование Windows* Чарльз Петцольд.  
  
 Поскольку образец, который сопровождает этот учебник, реализован в СЗ /CLI, этот учебник предполагает знакомство с использованием C's для программирования API Windows плюс понимание управляемого программирования кода. Знакомство с КЗ/CLI полезно, но не является существенным.  
  
> [!NOTE]
> Этот учебник включает ряд примеров кода из связанного образца приложения. Однако для удобства чтения он не содержит полный пример кода. Полный пример кода [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/Win32HostingWPFPage)  
  
<a name="basic_procedure"></a>
## <a name="the-basic-procedure"></a>Основная процедура  
 В этом разделе излагается основная [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] процедура, используемая для размещения содержимого в окне Win32. В остальных разделах подробно описывается каждый шаг.  
  
 Ключом к [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] хостингу контента в <xref:System.Windows.Interop.HwndSource> окне Win32 является класс. Этот класс заворачивает содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окно Win32, позволяя его включать в ваше [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] окно в качестве ребенка. Следующий подход сочетает в себе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Win32 и в одном приложении.  
  
1. Реализация [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого в виде управляемого класса.  
  
2. Реализуем приложение для Windows с помощью приложения для Windows с помощью приложения Для C-CLI. Если вы начинаете с существующего приложения и неуправляемого кода СЗ, вы обычно можете включить `/clr` управляемый код, изменив настройки проекта, чтобы включить флаг компилятора.  
  
3. Установите в качестве потоковой модели однопотоковое подразделение (STA).  
  
4. Обработать [уведомление WM_CREATE](/windows/desktop/winmsg/wm-create)в процедуре окна и сделать следующее:  
  
    1. Создайте новый объект <xref:System.Windows.Interop.HwndSource> с родительским окном в качестве его параметра `parent`.  
  
    2. Создайте экземпляр вашего класса содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3. Присвоить ссылку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на объект <xref:System.Windows.Interop.HwndSource.RootVisual%2A> содержимого <xref:System.Windows.Interop.HwndSource>в собственность .  
  
    4. Получите HWND для содержимого. Свойство <xref:System.Windows.Interop.HwndSource.Handle%2A> объекта <xref:System.Windows.Interop.HwndSource> содержит дескриптор окна (HWND). Чтобы получить HWND, который можно использовать в неуправляемой части приложения, приведите `Handle.ToPointer()` к HWND.  
  
5. Реализуйте управляемый класс, содержащий статическое поле для хранения ссылки на ваше содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот класс позволяет получить ссылку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на содержимое из кода Win32.  
  
6. Назначьте содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] этому статическому полю.  
  
7. Получайте уведомления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] от содержимого, прикрепляя обработчика к одному или более [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] событиям.  
  
8. Взаимодействуйте с содержимым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью ссылки, которую вы сохранили в статическом поле, для задания свойств и т. д.  
  
> [!NOTE]
> Вы также [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] можете использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для реализации содержимого. Тем не менее, вам придется компилировать его отдельно как динамические ссылки библиотеки (DLL) и ссылки, что DLL из вашего приложения Win32. Оставшаяся часть процедуры аналогична описанной выше.

<a name="implementing_the_application"></a>
## <a name="implementing-the-host-application"></a>Реализация ведущего приложения
 В этом разделе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] описывается, как размещать содержимое в базовом приложении Win32. Само содержание реализовано в си-КЗ/CLI в качестве управляемого класса. Большей частью это просто программирование [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Ключевые аспекты реализации контента обсуждаются при [реализации контента WPF.](#implementing_the_wpf_page)

- [Базовое приложение](#the_basic_application)

- [Размещение содержимого WPF](#hosting_the_wpf_page)

- [Хранение ссылки на содержимое WPF](#holding_a_reference)

- [Взаимодействие с содержимым WPF](#communicating_with_the_page)

<a name="the_basic_application"></a>
### <a name="the-basic-application"></a>Базовое приложение
 Отправной точкой для принимающего приложения было создание шаблона Visual Studio 2005.

1. Открыть Visual Studio 2005, и выбрать **новый проект** из меню **файла.**

2. Выберите **Win32** из списка типов проектов Visual C. Если ваш язык по умолчанию не является C, вы найдете эти типы проектов в **других языках.**

3. Выберите шаблон **проекта Win32,** присвоите имя проекту и **нажмите OK,** чтобы запустить **Win32 Application Wizard.**

4. Примите параметры по умолчанию мастера и нажмите **"Закончить",** чтобы начать проект.

 Шаблон создает базовое приложение Win32, в том числе:

- точку входа для приложения;

- окно со связанной процедурой окна (WndProc);

- Меню с заголовками **файл** а также **справки.** В меню **«Файл»** есть элемент **Exit,** который закрывает приложение. Меню **справки** имеет элемент **About,** который запускает простой диалоговой ящик.

 Перед тем, как начать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] писать код для размещения содержимого, необходимо внести два изменения в основной шаблон.

 Сначала следует скомпилировать проект как управляемый код. По умолчанию проект компилируется как неуправляемый код. Однако поскольку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализуется в управляемом коде, проект должен быть скомпилирован соответствующим образом.

1. Нажмите правой кнопкой мыши название проекта в **Solution Explorer** и выберите **свойства** из контекстного меню для запуска диалогового окна Страниц **ы свойств.**

2. Выберите **свойства конфигурации** из представления дерева в левом стеле.

3. Выберите поддержку **общего времени выполнения языка** из списка по **умолчанию проекта** в правильном стеле.

4. Выберите **общую поддержку выполнения языка (/clr)** из окна списка выпадающих.

> [!NOTE]
> Этот флаг компилятора позволяет использовать управляемый код в приложении, но ваш неуправляемый код будет продолжать компилироваться как раньше.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует потоковую модель однопотокового подразделения (STA). Для правильной работы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с кодом содержимого необходимо настроить модель потока приложения в STA, применяя атрибут к точке входа.

 [!code-cpp[Win32HostingWPFPage#WinMain](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]

<a name="hosting_the_wpf_page"></a>
### <a name="hosting-the-wpf-content"></a>Размещение содержимого WPF
 Содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] представляет собой простое приложение для входа адреса. Оно состоит из нескольких элементов управления <xref:System.Windows.Controls.TextBox> для получения имени пользователя, адреса и т. д. Есть также <xref:System.Windows.Controls.Button> два элемента управления, **OK** и **Отменить**. Когда пользователь нажимает **OK,** обработчик <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий кнопки собирает данные из <xref:System.Windows.Controls.TextBox> элементов управления, `OnButtonClicked`присваивает их соответствующим свойствам и поднимает пользовательское событие. Когда пользователь нажимает **Отмена,** обработчик просто поднимает `OnButtonClicked`. Объект аргумента события для `OnButtonClicked` содержит логическое поле, которое указывает, какая кнопка была нажата.

 Код для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого реализован в обработчике [для уведомления WM_CREATE](/windows/desktop/winmsg/wm-create) на окне хоста.

 [!code-cpp[Win32HostingWPFPage#WMCreate](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]

 Метод `GetHwnd` принимает информацию о размере и положении плюс ручку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] родительского окна и возвращает ручку окна размещенного содержимого.

> [!NOTE]
> Нельзя использовать директиву `#using` для пространства имен `System::Windows::Interop`. Иначе будет создан конфликт имен между структурой <xref:System.Windows.Interop.MSG> в этом пространстве имен и структурой MSG, объявленной в winuser.h. Вместо этого необходимо использовать полные имена для доступа к содержимому этого пространства имен.

 [!code-cpp[Win32HostingWPFPage#GetHwnd](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]

 Содержимое не [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может размещаться непосредственно в окне приложения. Вместо этого сначала создайте объект <xref:System.Windows.Interop.HwndSource>, который должен включать в себя содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот объект в основном окно, которое предназначено для размещения содержимого. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Вы размещаете <xref:System.Windows.Interop.HwndSource> объект в родительском окне, создавая его в качестве ребенка окна Win32, которое является частью вашего приложения. Параметры <xref:System.Windows.Interop.HwndSource> конструктора содержат почти ту же информацию, которую вы передайте CreateWindow при создании окна ребенка Win32.

 Затем вы создаете [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] экземпляр объекта содержимого. В этом случае [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое реализуется в `WPFPage`отдельном классе, используя СЗ/CLI. Можно также реализовать содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Однако для этого необходимо создать отдельный проект [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и создать контент в виде DLL. Вы можете добавить ссылку на этот DLL в свой проект [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и использовать эту ссылку для создания экземпляра содержимого.

 Содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отображается в окне ребенка, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] назначая <xref:System.Windows.Interop.HwndSource.RootVisual%2A> ссылку <xref:System.Windows.Interop.HwndSource>на содержимое свойства .

 Следующая строка кода присоединяет обработчик событий `WPFButtonClicked` к событию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого `OnButtonClicked`. Этот обработчик вызывается, когда пользователь нажимает кнопку **OK** или **Cancel.** Для дальнейшего обсуждения обработчика событий смотрите [communicating_with_the_WPF содержимое.](#communicating_with_the_page)

 В последней строке кода показан возврат дескриптора окна (HWND), который связан с объектом <xref:System.Windows.Interop.HwndSource>. Эту ручку из кода Win32 можно использовать для отправки сообщений в размещенное окно, хотя образец этого не делает. Объект <xref:System.Windows.Interop.HwndSource> инициирует событие каждый раз при получении сообщения. Для обработки сообщений вызовите метод <xref:System.Windows.Interop.HwndSource.AddHook%2A>, чтобы присоединить обработчик сообщений, а затем обрабатывать сообщения в этом обработчике.

<a name="holding_a_reference"></a>
### <a name="holding-a-reference-to-the-wpf-content"></a>Хранение ссылки на содержимое WPF
 Для многих приложений потребуется взаимодействовать с содержимым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позднее. Например, может возникнуть необходимость изменить свойства содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] или разместить в объекте <xref:System.Windows.Interop.HwndSource> другое содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Для этого потребуется ссылка на объект <xref:System.Windows.Interop.HwndSource> или содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Объект <xref:System.Windows.Interop.HwndSource> и связанное с ним содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] остаются в памяти до уничтожения дескриптора окна. Однако переменная, которая назначается объекту <xref:System.Windows.Interop.HwndSource>, выйдет из области действия сразу после возврата из процедуры окна. Обычный способ решения этой проблемы с помощью приложений Win32 заключается в использовании статического или глобальной переменной. К сожалению, нельзя назначать управляемый объект таким типам переменных. Вы можете назначить дескриптор окна, связанный с объектом <xref:System.Windows.Interop.HwndSource>, глобальной или статической переменной, но которая не предоставляет доступ к самому объекту.

 Самым простым решением этой проблемы является реализация управляемого класса, который содержит набор статических полей для хранения ссылок на любые управляемые объекты, к которым требуется доступ. В данном примере используется класс `WPFPageHost` для хранения ссылки на содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], а также начальные значения его свойств, которые могут быть изменены пользователем позднее. Это определяется в заголовке.

 [!code-cpp[Win32HostingWPFPage#WPFPageHost](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]

 В последней части `GetHwnd` функция присваивает значения этим полям для последующего использования, пока `myPage` остается в области.

<a name="communicating_with_the_page"></a>
### <a name="communicating-with-the-wpf-content"></a>Взаимодействие с содержимым WPF
 Существует два типа взаимодействия с содержимым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Приложение получает информацию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] из содержимого, когда пользователь нажимает **кнопки OK** или **Cancel.** Приложение также имеет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], в котором пользователь может изменять изменять различные свойства содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такие как цвет фона или размер шрифта по умолчанию.

 Как упоминалось выше, когда пользователь нажимает одну из кнопок, содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вызывает событие `OnButtonClicked`. Приложение присоединяет обработчик к этому событию, чтобы получать эти уведомления. Если кнопка **OK** была нажата, обработчик получает информацию о пользователе из содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и отображает ее в наборе статических элементов управления.

 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]

 Обработчик получает объект аргумента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] пользовательского события из содержимого `MyPageEventArgs`. Свойство `IsOK` объекта устанавливается `true` в случае нажатия кнопки `false` **ОК** и нажатия кнопки **«Отмена».**

 Если кнопка **OK** была нажата, обработчик получает ссылку на содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] из класса контейнеров. Затем он собирает сведения о пользователе, которые хранятся в соответствующих свойствах содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и использует статические элементы управления для отображения этих сведений в родительском окне. Поскольку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] данные о содержимом в виде управляемой строки должны быть сфальсифицированы для использования элементом управления Win32. Если кнопка **«Отмена»** была нажата, обработчик очищает данные от статических элементов управления.

 Приложение [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] предоставляет набор переключателей, с помощью которых пользователь может изменять цвет фона для содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и некоторые свойства, связанные со шрифтами. Следующий пример представляет выдержку из процедуры окна приложения (WndProc), содержащую обработку его сообщения, которая устанавливает разные свойства в различных сообщениях, включая цвет фона. Остальные примеры похожи и не приводятся. Подробные сведения и контекст см. в полном примере.

 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]

 Чтобы задать цвет фона, получите ссылку на содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (`hostedPage`) из `WPFPageHost` и установите в свойстве цвета фона соответствующий цвет. В примере используется три варианта цвета: исходный цвет, светло-зеленый и светло-оранжевый. Исходный цвет фона хранится в виде статического поля в классе `WPFPageHost`. Чтобы задать другие два цвета, создайте новый объект <xref:System.Windows.Media.SolidColorBrush> и передайте в конструктор значение статического цвета из объекта <xref:System.Windows.Media.Colors>.

<a name="implementing_the_wpf_page"></a>
## <a name="implementing-the-wpf-page"></a>Реализация страницы WPF
 Вы можете размещать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и использовать содержимое без какого-либо знания фактической реализации. Если [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] бы содержимое было упаковано в отдельный DLL, оно могло бы быть построено на любом общем языке выполнения языка (CLR). Ниже приводится краткое резюме реализации программы «СЗ/КЛИ», которая используется в выборке. Этот подраздел состоит из следующих подразделов.

- [Макет](#page_layout)

- [Возврат данных в главное окно](#returning_data_to_window)

- [Установка свойств WPF](#set_page_properties)

<a name="page_layout"></a>
### <a name="layout"></a>Макет
 Элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержании <xref:System.Windows.Controls.TextBox> состоят из <xref:System.Windows.Controls.Label> пяти элементов управления, с соответствующими элементами управления: Имя, Адрес, Город, Государство и Зип. Есть также <xref:System.Windows.Controls.Button> два элемента управления, **OK** и **Отменить**

 Содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализовано в классе `WPFPage`. Макет обрабатывается с помощью элемента макета <xref:System.Windows.Controls.Grid>. Этот класс наследует от <xref:System.Windows.Controls.Grid>, который фактически делает его корневым элементом содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 Конструктор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого <xref:System.Windows.Controls.Grid> занимает необходимую ширину и высоту и размеры соответственно. Затем он определяет базовую компоновку, создавая набор <xref:System.Windows.Controls.Grid> объектов <xref:System.Windows.Controls.Grid.RowDefinitions%2A> <xref:System.Windows.Controls.ColumnDefinition> <xref:System.Windows.Controls.RowDefinition> и добавляя их в базу <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> объектов и коллекции, соответственно. Это задает сетку из пяти строк и семи столбцов с размерами, определяемыми содержимым ячеек.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]

 Затем конструктор добавляет элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в объект <xref:System.Windows.Controls.Grid>. Первый элемент — это текст заголовка, который является элементом управления <xref:System.Windows.Controls.Label>, выравниваемым по центру в первой строке сетки.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]

 Следующая строка содержит элемент управления <xref:System.Windows.Controls.Label> «Имя» и связанный с ним элемент управления <xref:System.Windows.Controls.TextBox>. Так как тот же код используется для каждой пары «метка/текстовое поле», он помещается в пару закрытых методов и используется для всех пяти пар «метка/текстовое поле». Эти методы создают соответствующий элемент управления и вызывают класс <xref:System.Windows.Controls.Grid> статического метода <xref:System.Windows.Controls.Grid.SetColumn%2A> и методы <xref:System.Windows.Controls.Grid.SetRow%2A> для размещения элементов управления в соответствующую ячейку. После создания элемента управления в примере вызывается метод <xref:System.Windows.Controls.UIElementCollection.Add%2A> в свойстве <xref:System.Windows.Controls.Panel.Children%2A> объекта <xref:System.Windows.Controls.Grid> для добавления элемента управления в сетку. Для добавления оставшихся пар «метка/текстовое поле» используется аналогичный код. Подробности см. в примере кода.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]

 Реализация этих двух методов выглядит следующим образом:

 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]

 Наконец, образец добавляет кнопки **OK** и **Cancel** и <xref:System.Windows.Controls.Primitives.ButtonBase.Click> прикрепляет обработчик событий к их событиям.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]

<a name="returning_data_to_window"></a>
### <a name="returning-the-data-to-the-host-window"></a>Возврат данных в главное окно
 При нажатии одной из кнопок вызывается ее событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. Главное окно может просто присоединять обработчики к этим событиям и получать данные напрямую из элементов управления <xref:System.Windows.Controls.TextBox>. В примере используется несколько менее прямой подход. Он обрабатывает <xref:System.Windows.Controls.Primitives.ButtonBase.Click> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое, а затем поднимает `OnButtonClicked`пользовательское событие, чтобы уведомить о содержании. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Это позволяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимому сделать некоторую проверку параметров, прежде чем уведомить унификацию узла. Обработчик получает текст из элементов управления <xref:System.Windows.Controls.TextBox> и назначает его общим свойствам, из которых узел может получать сведения.

 Объявление события в WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]

 Обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> в WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]

<a name="set_page_properties"></a>
### <a name="setting-the-wpf-properties"></a>Установка свойств WPF
 Хост Win32 позволяет пользователю изменить несколько [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойств содержимого. Со стороны Win32, это просто вопрос изменения свойств. Реализация в классе содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] несколько более сложная, поскольку нет одного глобального свойства, которое управляет шрифтами для всех элементов управления. Вместо этого для каждого элемента управления изменяется соответствующее свойство в методах доступа set этого свойства. В следующем примере показан `DefaultFontFamily` код свойства. Задание свойства вызывает закрытый метод, который в свою очередь устанавливает свойства <xref:System.Windows.Controls.Control.FontFamily%2A> для различных элементов управления.

 Из WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]

 Из WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Interop.HwndSource>
- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
