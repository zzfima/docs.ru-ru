---
title: Взаимодействие WPF и Win32
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 7b7c3ed8f9833094ce1e836c11f84132ae84def2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735230"
---
# <a name="wpf-and-win32-interoperation"></a>Взаимодействие WPF и Win32

В этом разделе приводятся общие сведения о способах взаимодействия [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и кода Win32. Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако при наличии значительных вложений в код Win32 может быть более эффективным повторно использовать часть этого кода.

<a name="basics"></a>

## <a name="wpf-and-win32-interoperation-basics"></a>Основы взаимодействия WPF и Win32

Существует два основных способа взаимодействия между [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и кодом Win32.

- Размещение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого в окне Win32. С помощью этого метода можно использовать расширенные графические возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в рамках платформы стандартного окна Win32 и приложения.

- Размещение окна Win32 в содержимом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. С помощью этого метода можно использовать существующий пользовательский элемент управления Win32 в контексте другого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого и передавать данные через границы.

Каждый из этих способов детально представлен в этом разделе. Более наглядное описание кода размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в Win32 см. в разделе [Пошаговое руководство. размещение содержимого WPF в Win32](walkthrough-hosting-wpf-content-in-win32.md). Более наглядный пример размещения Win32 в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]см. в разделе [Пошаговое руководство. размещение элемента управления Win32 в WPF](walkthrough-hosting-a-win32-control-in-wpf.md).

<a name="projects"></a>

## <a name="wpf-interoperation-projects"></a>Проекты взаимодействия WPF

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API — это управляемый код, но большинство существующих программ Win32 записываются в C++неуправляемом виде.  Нельзя вызывать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API из неуправляемой программы. Однако с помощью параметра `/clr` с компилятором Microsoft Visual C++ можно создать смешанную управляемую неуправляемую программу, в которой можно легко смешивать управляемые и неуправляемые вызовы API.

Одна из осложнений на уровне проекта заключается в том, что нельзя компилировать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] C++ файлы в проект.  Имеется несколько методов разделения проектов для решения данной проблемы.

- Создайте C# библиотеку DLL, содержащую все [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы в виде скомпилированной сборки, а затем включите в C++ ИСПОЛНЯЕМЫЙ файл эту библиотеку DLL в качестве ссылки.

- Создайте C# исполняемый файл для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого и сослаться на C++ библиотеку DLL, содержащую содержимое Win32.

- Используйте <xref:System.Windows.Markup.XamlReader.Load%2A> для загрузки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] во время выполнения вместо компиляции [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

- Не используйте [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] вообще и запишите все [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в коде, создав дерево элементов из <xref:System.Windows.Application>.

Используйте любой наиболее подходящий способ.

> [!NOTE]
> Если вы раньше не работали C++с/CLI, вы можете заметить некоторые «новые» ключевые слова, такие как `gcnew` и `nullptr` в примерах кода взаимодействия. Эти ключевые слова заменяют старый синтаксис двойной подчеркивания (`__gc`) и предоставляют более естественный синтаксис для управляемого кода в C++.  Дополнительные сведения о функциях C++, управляемых с помощью/CLI, см. в разделе [расширения компонентов для платформ среды выполнения](/cpp/windows/component-extensions-for-runtime-platforms).

<a name="hwnds"></a>

## <a name="how-wpf-uses-hwnds"></a>Как в WPF используются дескрипторы HWND

Для эффективного использования взаимодействия HWND в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] необходимо понимать, как в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используются дескрипторы HWND. Для любого HWND нельзя сочетать отрисовку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с отрисовкой DirectX или визуализацией GDI/GDI+. Это имеет ряд последствий. В первую очередь для смешивания этих моделей отрисовки необходимо создать решение взаимодействия и использовать специальные сегменты взаимодействия для каждой модели отрисовки, которая выбрана для использования. Кроме того, получаемое при отрисовке изображение создает ограничение airspace для решения взаимодействия, которое можно применить. Концепция airspace более подробно рассматривается в разделе [Общие сведения об областях применения технологий](technology-regions-overview.md).

Все элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на экране в конечном счете поддерживаются дескриптором окна HWND. При создании <xref:System.Windows.Window>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создает HWND верхнего уровня и использует <xref:System.Windows.Interop.HwndSource> для размещения <xref:System.Windows.Window> и его [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого внутри HWND.  Остальная часть содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложении также использует этот единственный дескриптор HWND. Исключением являются меню, поля с раскрывающимся списком и другие всплывающие окна. Эти элементы создают свое собственное окно верхнего уровня, поэтому меню [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может выйти за край HWND окна, которое его содержит. При использовании <xref:System.Windows.Interop.HwndHost> для размещения HWND внутри [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] информирует Win32 о том, как разместить новый дочерний HWND относительно [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND.

С HWND связано понятие прозрачности внутри и между каждым дескриптором HWND. Оно также рассматривается в разделе [Общие сведения об областях применения технологий](technology-regions-overview.md).

<a name="hosting_a_wpf_page"></a>

## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>Размещение содержимого WPF в окне Microsoft Win32

Ключом к размещению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окне Win32 является класс <xref:System.Windows.Interop.HwndSource>. Этот класс служит оболочкой для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого в окне Win32, чтобы содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно было включить в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] в качестве дочернего окна. Следующий подход сочетает в себе Win32 и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в одном приложении.

1. Реализуйте содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (содержимое корневого элемента) в виде управляемого класса. Как правило, класс наследует от одного из классов, которые могут содержать несколько дочерних элементов и/или использоваться в качестве корневого элемента, например <xref:System.Windows.Controls.DockPanel> или <xref:System.Windows.Controls.Page>. В последующих шагах этот класс называется классом содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], а его экземпляры называются объектами содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

2. Реализация приложения Windows с помощью C++/CLI. Если вы начинаете с существующего неуправляемого C++ приложения, вы обычно можете включить его для вызова управляемого кода, изменив параметры проекта так, чтобы они включали флаг `/clr` компилятора (полная область действия, которая может потребоваться для поддержки `/clr` компиляции, не описывается в этом разделе).

3. Установите в качестве потоковой модели однопотоковое подразделение (STA). Эта потоковая модель используется [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

4. Обработайте уведомления WM_CREATE в процедуре окна.

5. В обработчике (или функции, которую вызывает обработчик) выполните указанные ниже действия.

    1. Создайте новый объект <xref:System.Windows.Interop.HwndSource> с HWND родительского окна в качестве параметра `parent`.

    2. Создайте экземпляр вашего класса содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

    3. Присвойте ссылку на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объект содержимого <xref:System.Windows.Interop.HwndSource>ному свойству объекта <xref:System.Windows.Interop.HwndSource.RootVisual%2A>.

    4. Свойство <xref:System.Windows.Interop.HwndSource.Handle%2A> объекта <xref:System.Windows.Interop.HwndSource> содержит дескриптор окна (HWND). Чтобы получить HWND, который можно использовать в неуправляемой части приложения, приведите `Handle.ToPointer()` к HWND.

6. Реализуйте управляемый класс, содержащий статическое поле, которое хранит ссылку на объект содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот класс позволяет получить ссылку на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объект содержимого из кода Win32, но, что более важно, это предотвратит случайную сборку мусора для <xref:System.Windows.Interop.HwndSource>.

7. Получите уведомления от объекта содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], присоединив обработчик к одному или нескольким событиям объекта содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

8. Для взаимодействия с объектом содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используйте ссылку, которую сохранили в статическом поле, чтобы задать свойства, методы вызова и т. д.

> [!NOTE]
> Определить класс содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для шага 1 можно частично или полностью в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] с помощью разделяемого класса по умолчанию класса содержимого. Для этого нужно создать отдельную сборку и сослаться на нее. Несмотря на то, что обычно включается объект <xref:System.Windows.Application> в процессе компиляции [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в сборку, вы не используете этот <xref:System.Windows.Application> как часть взаимодействия, вы просто используете один или несколько корневых классов для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлов, на которые ссылается приложение, и ссылающиеся на их разделяемые классы. Оставшаяся часть процедуры практически аналогична описанной выше.
>
> Каждое из этих действий будет показано в коде в разделе [Пошаговое руководство. Размещение содержимого WPF в Win32](walkthrough-hosting-wpf-content-in-win32.md).

<a name="hosting_an_hwnd"></a>

## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>Размещение окна Microsoft Win32 в WPF

Ключом к размещению окна Win32 в другом содержимом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является класс <xref:System.Windows.Interop.HwndHost>. Он заключает окно в элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], который можно добавить в дерево элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Interop.HwndHost> также поддерживает интерфейсы API, позволяющие выполнять такие задачи, как обработка сообщений для размещенного окна. Ниже описываются основные действия.

1. Создайте дерево элементов для приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (посредством кода или разметки). Найдите соответствующую и допустимую точку в дереве элементов, где можно добавить <xref:System.Windows.Interop.HwndHost> реализацию в качестве дочернего элемента. В оставшихся действиях процедуры этот элемент называется элементом резервирования.

2. Создайте класс, производный от <xref:System.Windows.Interop.HwndHost>, чтобы создать объект, содержащий содержимое Win32.

3. В данном классе узла Переопределите метод <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>. Возвратите HWND размещенного окна. Вероятно, вам может потребоваться заключить существующие элементы управления в дочернее окно возвращаемого окна. Заключение элементов управления в основное окно представляет собой простой способ получения уведомлений от элементов управления для содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот метод помогает устранить некоторые проблемы Win32, связанные с обработкой сообщений на границе размещаемого элемента управления.

4. Переопределите <xref:System.Windows.Interop.HwndHost> методы <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> и <xref:System.Windows.Interop.HwndHost.WndProc%2A>. Цель этого — выполнить очистку и удалить ссылки на размещаемое содержимое, особенно если созданы ссылки на неуправляемые объекты.

5. В файле кода программной части создайте экземпляр класса, размещающего элемент управления, и сделайте его дочерним классом элемента резервирования. Обычно используется обработчик событий, например <xref:System.Windows.FrameworkElement.Loaded>, или конструктор разделяемого класса. Но можно также добавить содержимое взаимодействия с помощью поведения среды выполнения.

6. Обработайте сообщения выбранного окна, такие как уведомления элементов управления. Существуют два подхода. Оба предоставляют идентичный доступ к потоку сообщений, поэтому выбор во многом определяется удобством программирования.

    - Реализуйте обработку сообщений для всех сообщений (не только сообщений о завершении работы) в переопределении метода <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.WndProc%2A>.

    - Элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] размещения обрабатывает сообщения, обрабатывая событие <xref:System.Windows.Interop.HwndHost.MessageHook>. Это событие вызывается для каждого сообщения, которое отправляется в главную процедуру размещенного окна.

    - Нельзя обрабатывать сообщения из окон, которые не обрабатываются с помощью <xref:System.Windows.Interop.HwndHost.WndProc%2A>.

7. Для взаимодействия с размещенным окном используйте вызов неуправляемого кода с целью вызова неуправляемой функции `SendMessage`.

Следующие действия создают приложение, которое работает с вводом мыши. Можно добавить поддержку табуляции для размещенного окна, реализовав интерфейс <xref:System.Windows.Interop.IKeyboardInputSink>.

Каждое из этих действий будет показано в коде в разделе [Пошаговое руководство. Размещение элемента управления Win32 в WPF](walkthrough-hosting-a-win32-control-in-wpf.md).

### <a name="hwnds-inside-wpf"></a>Дескрипторы HWND внутри WPF

<xref:System.Windows.Interop.HwndHost> можно представить как Специальный элемент управления. (Технически, <xref:System.Windows.Interop.HwndHost> является <xref:System.Windows.FrameworkElement> производным классом, а не <xref:System.Windows.Controls.Control> производным классом, но его можно рассматривать как элемент управления для взаимодействия.) <xref:System.Windows.Interop.HwndHost> абстрагирует базовую природу Win32 размещенного содержимого таким образом, что оставшаяся часть [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] считает размещенное содержимое другим объектом, подобным элементу управления, который должен обрабатывать и обрабатывать входные данные. <xref:System.Windows.Interop.HwndHost> обычно ведет себя так же, как и любой другой [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>, хотя существует ряд важных различий между выходными данными (рисование и график) и вводом (мышь и клавиатура) на основе ограничений, которые могут поддерживаться базовыми дескрипторами HWND.

#### <a name="notable-differences-in-output-behavior"></a>Важные различия в режиме вывода

- <xref:System.Windows.FrameworkElement>, который является базовым классом <xref:System.Windows.Interop.HwndHost>, имеет довольно много свойств, которые подразумевают изменения в пользовательском интерфейсе. К ним относятся такие свойства, как <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>, которые изменяют макет элементов внутри этого элемента как родительский. Однако большинство этих свойств не сопоставлены с возможными эквивалентами Win32, даже если такие эквиваленты могут существовать. Многие из этих свойств и их значений слишком специфичны для технологии отрисовки, чтобы сопоставление было целесообразным. Поэтому установка свойств, например <xref:System.Windows.FrameworkElement.FlowDirection%2A> в <xref:System.Windows.Interop.HwndHost>, не оказывает никакого влияния.

- <xref:System.Windows.Interop.HwndHost> нельзя поворачивать, масштабировать, расклонять или иным образом затронуть преобразованием.

- <xref:System.Windows.Interop.HwndHost> не поддерживает свойство <xref:System.Windows.UIElement.Opacity%2A> (альфа-смешение). Если содержимое в <xref:System.Windows.Interop.HwndHost> выполняет <xref:System.Drawing> операции, которые включают альфа-информацию, это не нарушение, но <xref:System.Windows.Interop.HwndHost> в целом поддерживает только Opacity = 1,0 (100%).

- <xref:System.Windows.Interop.HwndHost> будут отображаться поверх других [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов в том же окне верхнего уровня. Однако меню, созданное <xref:System.Windows.Controls.ToolTip> или <xref:System.Windows.Controls.ContextMenu>, является отдельным окном верхнего уровня, поэтому оно будет работать правильно с <xref:System.Windows.Interop.HwndHost>.

- <xref:System.Windows.Interop.HwndHost> не учитывается область обрезки родительского <xref:System.Windows.UIElement>. Это может быть проблемой, если попытаться разместить класс <xref:System.Windows.Interop.HwndHost> в области прокрутки или <xref:System.Windows.Controls.Canvas>.

#### <a name="notable-differences-in-input-behavior"></a>Важные различия в режиме ввода

- Как правило, хотя входные устройства находятся в <xref:System.Windows.Interop.HwndHost>, размещенном в регионе Win32, события ввода переходят непосредственно в Win32.

- Когда мышь находится над <xref:System.Windows.Interop.HwndHost>, приложение не получает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] событий мыши, а значение свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.IsMouseOver%2A> будет `false`.

- Несмотря на то, что <xref:System.Windows.Interop.HwndHost> имеет фокус клавиатуры, приложение не будет получать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] события клавиатуры и значение свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> будет `false`.

- Когда фокус находится внутри <xref:System.Windows.Interop.HwndHost> и изменения в другом элементе управления в <xref:System.Windows.Interop.HwndHost>, приложение не будет получать события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.GotFocus> или <xref:System.Windows.UIElement.LostFocus>.

- Связанные свойства и события пера являются аналогом и не сообщают о том, что перо превышено <xref:System.Windows.Interop.HwndHost>.

<a name="tabbing_mnemonics_accelerators"></a>

## <a name="tabbing-mnemonics-and-accelerators"></a>Переходы, назначенные клавиши и сочетания клавиш

Интерфейсы <xref:System.Windows.Interop.IKeyboardInputSink> и <xref:System.Windows.Interop.IKeyboardInputSite> позволяют создавать удобные возможности клавиатуры для смешанных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и приложений Win32:

- Переход между компонентами Win32 и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]

- Назначенные клавиши и сочетания клавиш, которые работают, когда фокус находится внутри компонента Win32 или WPF.

Классы <xref:System.Windows.Interop.HwndHost> и <xref:System.Windows.Interop.HwndSource> предоставляют реализации <xref:System.Windows.Interop.IKeyboardInputSink>, но они могут не поддерживать все входные сообщения, необходимые для более сложных сценариев. Переопределите соответствующие методы, чтобы получить нужное поведение клавиатуры.

Интерфейсы поддерживают только то, что происходит при переходе между областями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и Win32. В пределах области Win32 поведение табуляции полностью управляется логикой, реализованной в Win32, для табуляции, если таковая имеется.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [Пошаговое руководство. Размещение элемента управления Win32 в WPF](walkthrough-hosting-a-win32-control-in-wpf.md)
- [Пошаговое руководство. Размещение содержимого WPF в Win32](walkthrough-hosting-wpf-content-in-win32.md)
