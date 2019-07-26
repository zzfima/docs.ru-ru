---
title: Взаимодействие WPF и Win32
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: a942d72f27d394d31a52fd02ecaa158add4d2e0f
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484636"
---
# <a name="wpf-and-win32-interoperation"></a>Взаимодействие WPF и Win32
В этом разделе приводится общее описание метода обеспечения взаимодействия [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и кода [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако если имеется сложный код [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], возможно, более эффективным будет повторное использование части этого кода.  

<a name="basics"></a>   
## <a name="wpf-and-win32-interoperation-basics"></a>Основы взаимодействия WPF и Win32  
 Существуют два основных метода взаимодействия между [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и кодом [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
- Размещение содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окне [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. С помощью этого способа можно использовать дополнительные графические возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в структуре стандартных окон и приложений [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
- Размещение окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в содержимом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. С помощью этого способа можно использовать существующий пользовательский элемент управления [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в контексте другого содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и передавать данные через границы.  
  
 Каждый из этих способов детально представлен в этом разделе. Более наглядную иллюстрацию размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в см. в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]разделе [пошаговое руководство. Размещение содержимого WPF в Win32](walkthrough-hosting-wpf-content-in-win32.md). Более наглядную иллюстрацию размещения [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в см. в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]разделе [пошаговое руководство. Размещение элемента управления Win32 в WPF](walkthrough-hosting-a-win32-control-in-wpf.md).  
  
<a name="projects"></a>   
## <a name="wpf-interoperation-projects"></a>Проекты взаимодействия WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]API — это управляемый код, но [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] большинство существующих программ пишутся в неуправляемом виде. C++  Вы не можете [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вызывать API из неуправляемой программы. Однако с помощью `/clr` параметра [!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)] в компиляторе можно создать смешанную управляемую неуправляемую программу, в которой можно легко смешивать управляемые и неуправляемые вызовы API.  
  
 Одна сложность на уровне проекта заключается в том, что вы [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] не можете компилировать C++ файлы в проект.  Имеется несколько методов разделения проектов для решения данной проблемы.  
  
- Создайте C# библиотеку DLL, содержащую все [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы в виде скомпилированной сборки, а затем включите в C++ исполняемый файл [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] эту ссылку.  
  
- Создайте C# исполняемый файл для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого и сослаться на [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] объект C++ [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] , содержащий содержимое.  
  
- Используйте <xref:System.Windows.Markup.XamlReader.Load%2A> для загрузки любых [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] данных во время выполнения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]вместо компиляции.  
  
- Не используйте [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] вообще и записывайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] весь код в коде, создавая дерево элементов из <xref:System.Windows.Application>.  
  
 Используйте любой наиболее подходящий способ.  
  
> [!NOTE]
>  Если вы раньше не работали C++с/CLI, вы можете заметить некоторые «новые» ключевые слова, `gcnew` например `nullptr` и, в примерах кода взаимодействия. Эти ключевые слова заменяют старый синтаксис двойного подчеркивания`__gc`() и предоставляют более естественный синтаксис для управляемого кода C++в.  Дополнительные сведения о функциях C++, управляемых с помощью/CLI, см. в разделе [расширения компонентов для платформ среды выполнения](/cpp/windows/component-extensions-for-runtime-platforms) и [Hello, C++/CLI](https://go.microsoft.com/fwlink/?LinkId=98739).  
  
<a name="hwnds"></a>   
## <a name="how-wpf-uses-hwnds"></a>Как в WPF используются дескрипторы HWND  
 Для эффективного использования взаимодействия HWND в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] необходимо понимать, как в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используются дескрипторы HWND. Для любого HWND нельзя смешивать отрисовку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с отрисовкой [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] или отрисовкой [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] / [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)]. Это имеет ряд последствий. В первую очередь для смешивания этих моделей отрисовки необходимо создать решение взаимодействия и использовать специальные сегменты взаимодействия для каждой модели отрисовки, которая выбрана для использования. Кроме того, получаемое при отрисовке изображение создает ограничение airspace для решения взаимодействия, которое можно применить. Концепция airspace более подробно рассматривается в разделе [Общие сведения об областях применения технологий](technology-regions-overview.md).  
  
 Все элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на экране в конечном счете поддерживаются дескриптором окна HWND. При [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создании <xref:System.Windows.Window> создаетHWND<xref:System.Windows.Interop.HwndSource>верхнего уровня и использует, чтобы разместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] иегосодержимоевHWND.<xref:System.Windows.Window> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  Остальная часть содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложении также использует этот единственный дескриптор HWND. Исключением являются меню, поля с раскрывающимся списком и другие всплывающие окна. Эти элементы создают свое собственное окно верхнего уровня, поэтому меню [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может выйти за край HWND окна, которое его содержит. При использовании <xref:System.Windows.Interop.HwndHost> для размещения HWND внутри [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]сообщает [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] о том, как разместить новый дочерний HWND относительно [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND.  
  
 С HWND связано понятие прозрачности внутри и между каждым дескриптором HWND. Оно также рассматривается в разделе [Общие сведения об областях применения технологий](technology-regions-overview.md).  
  
<a name="hosting_a_wpf_page"></a>   
## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>Размещение содержимого WPF в окне Microsoft Win32  
 Ключом к размещению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в окне является <xref:System.Windows.Interop.HwndSource> класс. Этот класс заключает содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окно [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] таким образом, что содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может быть включено в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] в качестве дочернего окна. Следующий подход объединяет [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в одном приложении.  
  
1. Реализуйте содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (содержимое корневого элемента) в виде управляемого класса. Как правило, класс наследует от одного из классов, которые могут содержать несколько дочерних элементов и/или использоваться в качестве корневого элемента, например <xref:System.Windows.Controls.DockPanel> или <xref:System.Windows.Controls.Page>. В последующих шагах этот класс называется классом содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], а его экземпляры называются объектами содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
2. Реализация приложения Windows с помощью C++/CLI. Если вы начинаете с существующего неуправляемого C++ приложения, вы обычно можете включить его для вызова управляемого кода, изменив параметры проекта, включив в `/clr` него флаг компилятора (полная область действия, которая может потребоваться для поддержки `/clr` компиляция не описывается в этом разделе).  
  
3. Установите в качестве потоковой модели однопотоковое подразделение (STA). Эта потоковая модель используется [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
4. Обработайте уведомления WM_CREATE в процедуре окна.  
  
5. В обработчике (или функции, которую вызывает обработчик) выполните указанные ниже действия.  
  
    1. Создайте новый <xref:System.Windows.Interop.HwndSource> объект с HWND родительского окна `parent` в качестве параметра.  
  
    2. Создайте экземпляр вашего класса содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3. Присвойте ссылку на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объект <xref:System.Windows.Interop.HwndSource> содержимого свойству Object <xref:System.Windows.Interop.HwndSource.RootVisual%2A> .  
  
    4. Свойство <xref:System.Windows.Interop.HwndSource> Object<xref:System.Windows.Interop.HwndSource.Handle%2A> содержит дескриптор окна (HWND). Чтобы получить HWND, который можно использовать в неуправляемой части приложения, приведите `Handle.ToPointer()` к HWND.  
  
6. Реализуйте управляемый класс, содержащий статическое поле, которое хранит ссылку на объект содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот класс позволяет получить ссылку на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объект содержимого [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] из кода, но, что <xref:System.Windows.Interop.HwndSource> более важно, он не позволяет случайно собрать мусор.  
  
7. Получите уведомления от объекта содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], присоединив обработчик к одному или нескольким событиям объекта содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
8. Для взаимодействия с объектом содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используйте ссылку, которую сохранили в статическом поле, чтобы задать свойства, методы вызова и т. д.  
  
> [!NOTE]
>  Определить класс содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для шага 1 можно частично или полностью в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] с помощью разделяемого класса по умолчанию класса содержимого. Для этого нужно создать отдельную сборку и сослаться на нее. <xref:System.Windows.Application> Хотя в процессе компиляции [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в сборку вы обычно включаете объект, вы <xref:System.Windows.Application> не используете его в качестве части взаимодействия. Вы просто используете один или несколько корневых классов для файлов, на [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] которые ссылаются в приложении и ссылаться на разделяемые классы. Оставшаяся часть процедуры практически аналогична описанной выше.  
>   
>  Каждое из этих действий проиллюстрировано с помощью кода в разделе [пошаговое руководство. Размещение содержимого WPF в Win32](walkthrough-hosting-wpf-content-in-win32.md).  
  
<a name="hosting_an_hwnd"></a>   
## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>Размещение окна Microsoft Win32 в WPF  
 Ключом к размещению [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна в другом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимом является <xref:System.Windows.Interop.HwndHost> класс. Он заключает окно в элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], который можно добавить в дерево элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Interop.HwndHost>также поддерживает интерфейсы API, позволяющие выполнять такие задачи, как обработка сообщений для размещенного окна. Ниже описываются основные действия.  
  
1. Создайте дерево элементов для приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (посредством кода или разметки). Найдите соответствующую и допустимую точку в дереве элементов, где <xref:System.Windows.Interop.HwndHost> реализацию можно добавить в качестве дочернего элемента. В оставшихся действиях процедуры этот элемент называется элементом резервирования.  
  
2. Создайте класс, <xref:System.Windows.Interop.HwndHost> производный от, чтобы создать объект [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] , содержащий содержимое.  
  
3. В этом классе узла Переопределите <xref:System.Windows.Interop.HwndHost> метод. <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> Возвратите HWND размещенного окна. Вероятно, вам может потребоваться заключить существующие элементы управления в дочернее окно возвращаемого окна. Заключение элементов управления в основное окно представляет собой простой способ получения уведомлений от элементов управления для содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот способ позволяет избежать некоторых проблем [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], касающихся обработки сообщений на границе размещаемых элементов управления.  
  
4. Переопределите <xref:System.Windows.Interop.HwndHost> методы <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> и <xref:System.Windows.Interop.HwndHost.WndProc%2A>. Цель этого — выполнить очистку и удалить ссылки на размещаемое содержимое, особенно если созданы ссылки на неуправляемые объекты.  
  
5. В файле кода программной части создайте экземпляр класса, размещающего элемент управления, и сделайте его дочерним классом элемента резервирования. Обычно используется обработчик событий <xref:System.Windows.FrameworkElement.Loaded>, например, или конструктор разделяемого класса. Но можно также добавить содержимое взаимодействия с помощью поведения среды выполнения.  
  
6. Обработайте сообщения выбранного окна, такие как уведомления элементов управления. Существуют два подхода. Оба предоставляют идентичный доступ к потоку сообщений, поэтому выбор во многом определяется удобством программирования.  
  
    - Реализуйте обработку сообщений для всех сообщений (не только сообщений о завершении работы) в <xref:System.Windows.Interop.HwndHost> переопределении метода <xref:System.Windows.Interop.HwndHost.WndProc%2A>.  
  
    - Элемент размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обрабатывает сообщения, <xref:System.Windows.Interop.HwndHost.MessageHook> обрабатывая событие. Это событие вызывается для каждого сообщения, которое отправляется в главную процедуру размещенного окна.  
  
    - Нельзя обрабатывать сообщения из окон, которые не обрабатываются с <xref:System.Windows.Interop.HwndHost.WndProc%2A>помощью.  
  
7. Для взаимодействия с размещенным окном используйте вызов неуправляемого кода с целью вызова неуправляемой функции `SendMessage`.  
  
 Следующие действия создают приложение, которое работает с вводом мыши. Можно добавить поддержку табуляции для размещенного окна, реализовав <xref:System.Windows.Interop.IKeyboardInputSink> интерфейс.  
  
 Каждое из этих действий проиллюстрировано с помощью кода в разделе [пошаговое руководство. Размещение элемента управления Win32 в WPF](walkthrough-hosting-a-win32-control-in-wpf.md).  
  
### <a name="hwnds-inside-wpf"></a>Дескрипторы HWND внутри WPF  
 Можно представить <xref:System.Windows.Interop.HwndHost> как Специальный элемент управления. (Технически, <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.FrameworkElement> является<xref:System.Windows.Controls.Control> производным классом, а не производным классом, но его можно рассматривать как элемент управления для взаимодействия.) абстрагирует базовую [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] природу размещенного содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] таким образом, что оставшаяся часть считает размещенное содержимое другим объектом, подобным элементу управления, который должен визуализировать и обрабатывать входные данные. <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost>обычно ведет себя так же, как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и любые другие <xref:System.Windows.FrameworkElement>, хотя существует ряд важных различий между выводом (рисование и график) и вводом (мышь и клавиатура) на основе ограничений, которые могут поддерживаться базовыми дескрипторами HWND.  
  
#### <a name="notable-differences-in-output-behavior"></a>Важные различия в режиме вывода  
  
- <xref:System.Windows.FrameworkElement>, который является <xref:System.Windows.Interop.HwndHost> базовым классом, имеет довольно много свойств, которые подразумевают изменения в пользовательском интерфейсе. К ним относятся такие свойства <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>, как, которые изменяют макет элементов внутри этого элемента как родительский. Однако большая часть этих свойств не сопоставляется с возможными эквивалентами [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], даже если такие эквиваленты могут существовать. Многие из этих свойств и их значений слишком специфичны для технологии отрисовки, чтобы сопоставление было целесообразным. Поэтому установка свойств, например <xref:System.Windows.FrameworkElement.FlowDirection%2A> On <xref:System.Windows.Interop.HwndHost> , не оказывает никакого влияния.  
  
- <xref:System.Windows.Interop.HwndHost>нельзя поворачивать, масштабировать, расклонять или иным образом затронуть преобразование.  
  
- <xref:System.Windows.Interop.HwndHost>не поддерживает <xref:System.Windows.UIElement.Opacity%2A> свойство (альфа-смешение). Если содержимое внутри <xref:System.Windows.Interop.HwndHost> операций выполняет <xref:System.Drawing> операции, которые включают в себя альфа-информацию, то это не является нарушением, но в <xref:System.Windows.Interop.HwndHost> целом поддерживает только Opacity = 1,0 (100%).  
  
- <xref:System.Windows.Interop.HwndHost>будет отображаться поверх других [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов в том же окне верхнего уровня. Тем не менее <xref:System.Windows.Controls.ToolTip> , <xref:System.Windows.Controls.ContextMenu> или созданное меню является отдельным окном верхнего уровня, поэтому оно будет работать правильно <xref:System.Windows.Interop.HwndHost>с.  
  
- <xref:System.Windows.Interop.HwndHost>не учитывается область обрезки родительского <xref:System.Windows.UIElement>элемента. Это может быть проблемой, если попытаться разместить <xref:System.Windows.Interop.HwndHost> класс внутри области прокрутки или. <xref:System.Windows.Controls.Canvas>  
  
#### <a name="notable-differences-in-input-behavior"></a>Важные различия в режиме ввода  
  
- Как правило, хотя входные устройства находятся в пределах <xref:System.Windows.Interop.HwndHost> размещенного [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] региона, входные события переходят непосредственно в. [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]  
  
- Пока мышь находится над <xref:System.Windows.Interop.HwndHost>, приложение не получает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] события мыши, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] а значение свойства <xref:System.Windows.UIElement.IsMouseOver%2A> будет `false`равно.  
  
- Несмотря на <xref:System.Windows.Interop.HwndHost> то, что имеет фокус клавиатуры, приложение не [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] будет получать события клавиатуры, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и значение свойства <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> будет `false`равно.  
  
- Когда фокус находится внутри элемента <xref:System.Windows.Interop.HwndHost> и изменяется на другой элемент управления <xref:System.Windows.Interop.HwndHost>в, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение не будет получать события <xref:System.Windows.UIElement.GotFocus> или <xref:System.Windows.UIElement.LostFocus>.  
  
- Связанные свойства и события пера являются аналогом и не сообщают информацию во время работы пера <xref:System.Windows.Interop.HwndHost>.  
  
<a name="tabbing_mnemonics_accelerators"></a>   
## <a name="tabbing-mnemonics-and-accelerators"></a>Переходы, назначенные клавиши и сочетания клавиш  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Интерфейсы и позволяют<xref:System.Windows.Interop.IKeyboardInputSite> создавать удобные возможности клавиатуры для смешанных и приложений: <xref:System.Windows.Interop.IKeyboardInputSink>  
  
- Переход между компонентами [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
- Назначенные клавиши и сочетания клавиш, которые работают, когда фокус находится внутри компонента Win32 или WPF.  
  
 Классы <xref:System.Windows.Interop.HwndHost> и <xref:System.Windows.Interop.HwndSource> предоставляют реализации<xref:System.Windows.Interop.IKeyboardInputSink>, но они могут не поддерживать все входные сообщения, необходимые для более сложных сценариев. Переопределите соответствующие методы, чтобы получить нужное поведение клавиатуры.  
  
 Интерфейсы обеспечивают поддержку только для событий перехода между областями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Внутри области [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] поведение перехода полностью контролируется логикой перехода, реализованной в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], если таковая имеется.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [Пошаговое руководство: Размещение элемента управления Win32 в WPF](walkthrough-hosting-a-win32-control-in-wpf.md)
- [Пошаговое руководство: Размещение содержимого WPF в Win32](walkthrough-hosting-wpf-content-in-win32.md)
