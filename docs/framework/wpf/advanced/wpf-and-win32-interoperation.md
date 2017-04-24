---
title: "Взаимодействие WPF и Win32 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "размещение содержимого WPF в окне Win32"
  - "HWND - взаимодействие [WPF]"
  - "взаимодействие [WPF], Win32"
  - "код Win32, взаимодействие с WPF"
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Взаимодействие WPF и Win32
В данном разделе приводится общее описание метода обеспечения взаимодействия [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и кода [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Клиент [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений.  Однако если имеется сложный код [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], возможно, более эффективным будет повторное использование части этого кода.  
  
   
  
<a name="basics"></a>   
## Основы взаимодействия WPF и Win32  
 Существуют два основные метода взаимодействия между [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и кодом [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
-   Размещение содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окне [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  С помощью этого способа можно использовать дополнительные графические возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в структуре стандартных окон и приложений [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
-   Размещение окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в содержимом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  С помощью этого способа можно использовать существующий пользовательский элемент управления [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в контексте другого содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и передавать данные через границы.  
  
 Каждый из этих способов детально представлен в этом разделе.  Дополнительные примеры кода размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] см. в разделе [Пошаговое руководство. Размещение содержимого WPF в Win32](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md) \("Пошаговое руководство. Размещение страницы Windows Presentation Foundation в приложении Win32"\).  Дополнительные примеры кода размещения [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Пошаговое руководство. Размещение элемента управления Win32 в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md) \("Пошаговое руководство. Размещение страницы Windows Presentation Foundation в приложении Win32"\).  
  
<a name="projects"></a>   
## Проекты взаимодействия WPF  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являются управляемым кодом, но большинство существующих программ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] записываются в неуправляемом приложении [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)].  Невозможно вызвать [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] из подлинной неуправляемой программы.  Однако с помощью параметра `/clr` с компилятором [!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)] можно создать смешанную управляемую\-неуправляемую программу, где могут равномерно смешиваться управляемые и неуправляемые вызовы [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)].  
  
 Существует одна сложность на уровне проекта, которая заключается в том, что не нельзя скомпилировать файлы [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] в проекте [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)].  Имеется несколько методов разделения проектов для решения данной проблемы.  
  
-   Создайте библиотеку DLL [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)], содержащую все страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в виде скомпилированной сборки, а затем включите в исполняемый файл [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] в качестве ссылки.  
  
-   Создайте исполняемый файл [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] для содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и используйте его ссылку на [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] с содержимым [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
-   Используйте <xref:System.Windows.Markup.XamlReader.Load%2A> для загрузки любого объекта [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] во время выполнения вместо компиляции [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
-   Не используйте [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] вообще, и записывайте все приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в коде, создавая дерево элементов из <xref:System.Windows.Application>.  
  
 Используйте любой, наиболее подходящий способ.  
  
> [!NOTE]
>  Если не использовать [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)], то можно заметить некоторые "новые" ключевые слова в качестве `gcnew` и `nullptr` в примерах кода взаимодействия. Эти ключевые слова заменяют более старый синтаксис двойной\- подчеркивания \(`__gc`\) и обеспечивают более естественный синтаксис для управляемого кода в [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)].  Дополнительные сведения о возможностях управляемого кода [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] см. в статьях [Расширения компонентов для платформ среды выполнения](../Topic/Component%20Extensions%20for%20Runtime%20Platforms.md) \("Языковые возможности в области настройки среды CLR"\) и [Hello, C \+ \+\/ CLI](http://go.microsoft.com/fwlink/?LinkId=98739) \("Знакомство с C \+\+\/ CLI"\).  
  
<a name="hwnds"></a>   
## Как WPF использует Hwnds  
 Чтобы расширить "взаимодействие HWND" с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], необходимо понимать, как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует HWND.  Для любого HWND нельзя смешивать отрисовку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с отрисовкой [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] или отрисовкой [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] \/ [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)].  Это имеет ряд последствий.  Главным образом, для смешивания этих моделей отрисовки необходимо создать решение взаимодействия и использовать разработанные сегменты взаимодействия для каждой модели рендеринга, которая выбрана для использования.  Также получаемое при отрисовке изображение создает ограничение "airspace" для решения взаимодействия, которое можно применить.  Концепция "airspace" объясняется более подробно в разделе [Общие сведения об областях применения технологий](../../../../docs/framework/wpf/advanced/technology-regions-overview.md).  
  
 Все элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на экране в конечном счете поддерживаются дескриптором окна HWND.  При создании [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объект <xref:System.Windows.Window>, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создает HWND верхнего уровня и использует <xref:System.Windows.Interop.HwndSource> для размещения окна <xref:System.Windows.Window> и его содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внутри HWND.  Остальная часть содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложении также использует этот единственный дескриптор HWND.  Исключением являются меню, поля с раскрывающимся списком и другие всплывающие окна.  Эти элементы создают свое собственное окно верхнего уровня, поэтому меню [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может выйти за край HWND окна, которое его содержит.  При использовании <xref:System.Windows.Interop.HwndHost> для размещения HWND внутри [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] информирует [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] о том, как разместить новый дочерний HWND относительно HWND <xref:System.Windows.Window> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Связанный c HWND концепт является прозрачным внутри и между каждым HWND.  Это также рассматривается в разделе [Общие сведения об областях применения технологий](../../../../docs/framework/wpf/advanced/technology-regions-overview.md).  
  
<a name="hosting_a_wpf_page"></a>   
## Размещение содержимого WPF в окне Microsoft Win32  
 Ключом к размещению [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окне [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] является класс <xref:System.Windows.Interop.HwndSource>.  Этот класс переносит [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое в окно [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] таким образом, что содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может быть включено в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] в качестве дочернего окна.  Следующий подход объединяет [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в одном приложении.  
  
1.  Реализуйте содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(содержимое корневого элемента\) в виде управляемого класса.  Как правило, класс наследуется из одного из классов, который может содержать несколько дочерних элементов и\/или использоваться в качестве корневого элемента, например <xref:System.Windows.Controls.DockPanel> или <xref:System.Windows.Controls.Page>.  В последующих шагах этот класс называется классом содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и экземпляры класса называются объектами содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
2.  Реализуйте приложение [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] с приложением [!INCLUDE[TLA2#tla_cppcli](../../../../includes/tla2sharptla-cppcli-md.md)].  При запуске существующего неуправляемого приложения [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)], как правило, можно активировать вызов управляемого кода путем изменения параметров проекта с целью включения флага компилятора `/clr` \(полное описание объектов, необходимых для поддержки компиляции `/clr` в данном разделе не приводится\).  
  
3.  Установите потоковую модель в однопотоковое подразделение \(Single Threaded Apartment — STA\).  Данная потоковая модель используется [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
4.  Обработайте уведомления WM\_CREATE в процедуре окна.  
  
5.  В обработчике \(или функции, которую вызывает обработчик\) выполните следующие действия.  
  
    1.  Создайте новый объект <xref:System.Windows.Interop.HwndSource> с родительским HWND окна в качестве его параметра `parent`.  
  
    2.  Создайте экземпляр класса содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3.  Назначьте ссылку на объект содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объекту <xref:System.Windows.Interop.HwndSource> свойства <xref:System.Windows.Interop.HwndSource.RootVisual%2A>.  
  
    4.  Объект <xref:System.Windows.Interop.HwndSource> свойства <xref:System.Windows.Interop.HwndSource.Handle%2A> содержит дескриптор окна \(HWND\).  Для получения HWND, который можно использовать в неуправляемой части приложения, преобразуйте `Handle.ToPointer()` в HWND.  
  
6.  Реализуйте управляемый класс, содержащий статическое поле, которое хранит ссылку на объект содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Этот класс не только позволяет получить ссылку на объект содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] из кода [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], но и, что еще более важно, защищает <xref:System.Windows.Interop.HwndSource> от случайного удаления сборщиком мусора.  
  
7.  Получите уведомления из объекта содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] путем присоединения обработчика к одному или нескольким событиям объекта содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
8.  Связывайте с объектом содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью ссылки, что хранили в статическом поле, чтобы задать свойства, методы и т д.  
  
> [!NOTE]
>  Это можно сделать некоторые или все определение класса содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для шага одно из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] по умолчанию разделяемый класс класса содержимого, если при выполнении отдельную сборку и затем ссылаться на него. Хотя обычно включить объект <xref:System.Windows.Application> как часть компилироваться в сборку, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не перемещается с помощью то <xref:System.Windows.Application> как часть взаимодействия нужно просто использовать один или несколько классов корня для файлов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] сосланных к приложению и ссылаться на них разделяемые классы.  Оставшаяся часть процедуры по существу аналогична описанной выше.  
>   
>  Каждое из этих действий будет показано в коде в разделе [Пошаговое руководство. Размещение содержимого WPF в Win32](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md).  
  
<a name="hosting_an_hwnd"></a>   
## Размещение окна Microsoft Win32 в WPF  
 Ключом к размещению окна [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] внутри другого содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является класс <xref:System.Windows.Interop.HwndHost>.  Класс облекает окно в оболочку элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], который можно добавить в дерево элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Кроме того, <xref:System.Windows.Interop.HwndHost> поддерживает объекты [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], которые позволяют выполнять такие задачи, как обработка сообщений для размещенного окна.  Основная процедура:  
  
1.  Создайте дерево элемента для приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(посредством кода или разметки\).  Найдите соответствующую и допустимую точку в дереве элемента, где реализация <xref:System.Windows.Interop.HwndHost> может быть добавлена в качестве дочернего элемента.  В оставшихся шагах этих действий этот элемент называется элементом резервирования.  
  
2.  Создайте класс производный от <xref:System.Windows.Interop.HwndHost> для создания объекта, который хранит содержимое [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
3.  В размещаемом классе переопределите метод <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> объекта <xref:System.Windows.Interop.HwndHost>.  Возвратите HWND размещенного окна.  Вероятно, вам может потребоваться заключение существующих элементов управления в оболочку дочернего окна возвращаемого окна; заключение элементов управления в оболочку окна размещения представляет собой простой способ получения уведомлений от элементов управления для содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Этот способ позволяет избежать некоторых проблем [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], касающихся обработки сообщений на границе размещаемых элементов управления.  
  
4.  Переопределите методы <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> и <xref:System.Windows.Interop.HwndHost.WndProc%2A> объекта <xref:System.Windows.Interop.HwndHost>.  Цель этого — обработать очистку и удаление ссылок в размещаемом содержимом, особенно если созданы ссылки на неуправляемые объекты.  
  
5.  В файле кода программной части создайте экземпляр элемента управления, размещающего класс, и сделайте его дочерним элемента резервирования.  Обычно используется обработчик событий, такой как <xref:System.Windows.FrameworkElement.Loaded>, или конструктор разделяемого класса.  Но можно также добавить содержимое взаимодействия с помощью поведения среды выполнения.  
  
6.  Обработка сообщений выбранного окна, таких как уведомления элементов управления.  Существуют два подхода.  Оба предоставляют идентичный доступ к потоку сообщений, поэтому выбор во многом определяется удобством программирования.  
  
    -   Реализуйте обработку сообщений для всех сообщений \(не только сообщений о завершении работы\) в переопределении метода <xref:System.Windows.Interop.HwndHost.WndProc%2A> объекта <xref:System.Windows.Interop.HwndHost>.  
  
    -   Разместите обработку сообщения элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] посредством обработки события <xref:System.Windows.Interop.HwndHost.MessageHook>.  Это событие вызывается для каждого сообщения, которое отправляется в главную процедуру окна размещенного окна.  
  
    -   Нельзя обрабатывать сообщения из окон, которые не участвуют в процессе, с помощью метода <xref:System.Windows.Interop.HwndHost.WndProc%2A>.  
  
7.  Свяжитесь с размещенным окном с помощью запуска платформы для вызова неуправляемых функций `SendMessage`.  
  
 Следующие действия создают приложение, которое работает с вводом мыши.  Можно добавить поддержку перехода с помощью клавиши табуляции для размещенного, реализацией интерфейса <xref:System.Windows.Interop.IKeyboardInputSink>.  
  
 Каждое из этих действий будет показано в коде в разделе [Пошаговое руководство. Размещение элемента управления Win32 в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md).  
  
### Hwnds внутри WPF  
 Можно представить <xref:System.Windows.Interop.HwndHost> как специальный элемент управления.  \(С технической точки зрения, <xref:System.Windows.Interop.HwndHost> представляет собой класс, производный от класса <xref:System.Windows.FrameworkElement>, а не от класса <xref:System.Windows.Controls.Control>, но его можно считать элементом управления применительно к соответствующему взаимодействию.\) <xref:System.Windows.Interop.HwndHost> выделяет базовый характер [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] размещенного содержимого таким образом, что остальная часть [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] считает размещенное содержимое другим объектом, подобным элементу управления, который должен отображать и обрабатывать входные данные.  Как правило, <xref:System.Windows.Interop.HwndHost> ведет себя подобно любому другому элементу [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>, хотя в зависимости от ограничений в поддержке базовых дескрипторов HWND в данном случае могут существовать некоторые существенные различия применительно к выводу данных \(рисование и графика\) и вводу данных \(мышь и клавиатура\).  
  
#### Важные различия в режиме вывода  
  
-   Объект <xref:System.Windows.FrameworkElement>, который является базовым классом <xref:System.Windows.Interop.HwndHost>, имеет несколько свойств, которые подразумевают изменение пользовательского интерфейса.  Они включают свойства, такие как <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=fullName>, которые меняют расположение элементов внутри этого элемента как родительского.  Однако большая часть этих свойств не сопоставляется с возможными эквивалентами [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], даже если такие эквиваленты могут существовать.  Слишком многие из этих свойств и их значений слишком специфичны для технологии отрисовки, чтобы быть практически применимыми.  Поэтому свойства параметров, например <xref:System.Windows.FrameworkElement.FlowDirection%2A> для объекта <xref:System.Windows.Interop.HwndHost>, в данном случае не оказывают никакого влияния.  
  
-   Объект <xref:System.Windows.Interop.HwndHost> не могут быть повернут, масштабированы, наклонен или, в противном случае, он будет подвергнут преобразованию.  
  
-   <xref:System.Windows.Interop.HwndHost> не поддерживает свойство <xref:System.Windows.UIElement.Opacity%2A> \(альфа\-смешение\).  Если содержимое внутри <xref:System.Windows.Interop.HwndHost> выполняет операции <xref:System.Drawing>, включающие сведения об альфа\-составляющей, это не является нарушением, но <xref:System.Windows.Interop.HwndHost>, так как единое целое, поддерживает только Opacity \= 1.0 \(100 %\).  
  
-   <xref:System.Windows.Interop.HwndHost> будет отображаться в верхней части других элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в окне верхнего уровня.  Однако созданное меню <xref:System.Windows.Controls.ToolTip> или <xref:System.Windows.Controls.ContextMenu> является отдельным окном верхнего уровня и поэтому будет работать правильно с объектом <xref:System.Windows.Interop.HwndHost>.  
  
-   <xref:System.Windows.Interop.HwndHost> не поддерживает кадрирование области его родительского объекта <xref:System.Windows.UIElement>.  Эта является потенциальной проблемой при попытке поместить класс <xref:System.Windows.Interop.HwndHost> внутри области прокрутки или <xref:System.Windows.Controls.Canvas>.  
  
#### Важные различия в режиме ввода  
  
-   В общем случае, когда устройства ввода находятся внутри размещенной области [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] объекта <xref:System.Windows.Interop.HwndHost>, события ввода поступают непосредственно в приложение [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
-   В то время как указатель мыши находится над объектом <xref:System.Windows.Interop.HwndHost>, приложение не получает событий мыши [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и значением свойства <xref:System.Windows.UIElement.IsMouseOver%2A> приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] будет `false`.  
  
-   В то время как <xref:System.Windows.Interop.HwndHost> имеет фокус клавиатуры, приложение не получает событий клавиатуры [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и значением свойства <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] будет `false`.  
  
-   Когда фокус находится внутри <xref:System.Windows.Interop.HwndHost> и переходит в другой элемент управления внутри <xref:System.Windows.Interop.HwndHost>, приложение не получает событий <xref:System.Windows.UIElement.GotFocus> или <xref:System.Windows.UIElement.LostFocus> приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Связанные свойства пера и события являются аналогами и не предоставляют отчет, когда перо находится над объектом <xref:System.Windows.Interop.HwndHost>.  
  
<a name="tabbing_mnemonics_accelerators"></a>   
## Переходы, назначенные клавиши и сочетания клавиш  
 Интерфейсы <xref:System.Windows.Interop.IKeyboardInputSink> и <xref:System.Windows.Interop.IKeyboardInputSite> позволяют создавать непрерывное взаимодействие с клавиатурой для смешанных приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]:  
  
-   Переход между компонентами [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Назначенные клавиши и сочетания клавиш, которые работают, когда фокус находится внутри компонента Win32 или WPF.  
  
 Классы <xref:System.Windows.Interop.HwndHost> и <xref:System.Windows.Interop.HwndSource> обеспечивают реализацию <xref:System.Windows.Interop.IKeyboardInputSink>, но они могут не обрабатывать все входные сообщения, необходимые для дополнительных скриптов.  Переопределите соответствующие методы, чтобы получить нужное поведение клавиатуры.  
  
 Интерфейсы только обеспечивают поддержку событий переходов между областями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Внутри области [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] поведение переключения полностью контролируется реализованной логикой [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] для переходов, если таковые имеются.  
  
## См. также  
 <xref:System.Windows.Interop.HwndHost>   
 <xref:System.Windows.Interop.HwndSource>   
 <xref:System.Windows.Interop>   
 [Пошаговое руководство. Размещение элемента управления Win32 в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)   
 [Пошаговое руководство. Размещение содержимого WPF в Win32](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)