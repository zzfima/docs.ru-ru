---
title: "Устранение неполадок смешанных приложений | Microsoft Docs"
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
  - "гибридные приложения [взаимодействие с WPF]"
  - "взаимодействие [WPF], Windows Forms"
  - "циклы обработки сообщений [WPF]"
  - "перекрывающиеся элементы управления"
  - "Windows Forms [WPF], взаимодействие с"
  - "Windows Forms, взаимодействие с WPF"
ms.assetid: f440c23f-fa5d-4d5a-852f-ba61150e6405
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Устранение неполадок смешанных приложений
<a name="introduction"></a> В этом разделе перечислены некоторые общие проблемы, которые могут возникать при создании смешанных приложений, одновременно использующих технологии [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
   
  
<a name="overlapping_controls"></a>   
## Перекрывающиеся элементы управления  
 Элементы управления могут не перекрываться должным образом.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] использует отдельный HWND для каждого элемента управления.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует один HWND для всего содержимого на странице.  Это отличие в реализации вызывает неожиданные перекрывающиеся поведения.  
  
 Элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], размещенный в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], всегда появляется в верхней части содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], размещенное в элементе управления <xref:System.Windows.Forms.Integration.ElementHost>, появляется в z\-порядке элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.  Возможно перекрытие элементов управления <xref:System.Windows.Forms.Integration.ElementHost>, но размещенное содержимое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не объединяется и не взаимодействует.  
  
<a name="child_property"></a>   
## Child Property  
 Классы <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> могут размещать только один дочерний элемент управления или элемент.  Для размещения более одного элемента управления или элемента, необходимо использовать контейнер в качестве дочернего содержимого.  Например, можно добавить элементы управления флажком и кнопкой [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] к элементу управления <xref:System.Windows.Forms.Panel?displayProperty=fullName>, а затем назначить панель свойству <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Однако нельзя добавить элементы управления кнопкой и флажком отдельно от того же элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="scaling"></a>   
## Масштабирование  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] имеют различные модели масштабирования.  Некоторые преобразования масштаба [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являются показательными для элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], а некоторые — нет.  Например, масштабирование элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] к 0 будет работать, но если попытаться масштабировать тот же элемент управления обратно на ненулевое значение, размер элемента управления останется равным 0.  Дополнительные сведения см. в разделе [Вопросы, связанные с макетом элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>   
## Адаптер  
 Путаница может быть при работе с классами <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost>, так как они содержат скрытый контейнер.  Оба класса <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> имеют скрытые контейнеры, с именем *адаптер*, которые они используют для размещения содержимого.  Для элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> адаптер извлекается из класса <xref:System.Windows.Forms.ContainerControl?displayProperty=fullName>.  Для элемента управления <xref:System.Windows.Forms.Integration.ElementHost> адаптер извлекается из элемента <xref:System.Windows.Controls.DockPanel>.  При появлении ссылок на адаптер в других разделах взаимодействия, этот контейнер становится контейнером, о котором шла речь.  
  
<a name="nesting"></a>   
## Вложение  
 Не поддерживается вложение элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> в элемент управления <xref:System.Windows.Forms.Integration.ElementHost>.  Также не поддерживается вложение элемента <xref:System.Windows.Forms.Integration.ElementHost> в элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="focus"></a>   
## Фокус  
 Фокус работает по\-разному в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], что означает, что в смешанном приложении могут возникать проблемы с фокусом.  Например, если имеется фокус внутри элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> и нужно свернуть или восстановить страницу либо показать модальное диалоговое окно, фокус внутри элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> может быть потерян.  Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> по\-прежнему имеет фокус, но элемент управления внутри него может не иметь.  
  
 Фокус также влияет и на проверку данных.  Проверка работает в элементе <xref:System.Windows.Forms.Integration.WindowsFormsHost>, но не работает при выходе за пределы элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> или между двумя различными элементами <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="property_mapping"></a>   
## Сопоставление свойств  
 Некоторые сопоставления свойств требуют всесторонней интерпретации для того, чтобы связать отличающиеся реализации между технологиями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Сопоставления свойств позволяют коду реагировать на изменения в шрифтах, цветах и других свойствах.  В общем случае сопоставление свойств работает посредством перехвата событий *Property*Changed или вызовов On*Property*Changed, и установкой свойств либо на дочерний элемент либо на его адаптер.  Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## Связанные с макетом свойства в размещенном содержимом  
 При назначении свойства <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=fullName> или <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=fullName>, некоторые связанные с макетом свойства в размещенном содержимом устанавливается автоматически.  Изменение этих свойств содержимого может привести к неожиданным поведениям макета.  
  
 Размещенное содержимое присоединяется для заполнения родителя <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost>.  Чтобы включить это поведение заполнения, некоторые свойства устанавливаются при установке дочернего свойства.  В следующей таблице перечислены какие свойства содержимого задаются классами <xref:System.Windows.Forms.Integration.ElementHost> и <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
|Host Class|Свойства содержимого|  
|----------------|--------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 Не устанавливайте эти свойства непосредственно на размещенном содержимом.  Дополнительные сведения см. в разделе [Вопросы, связанные с макетом элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>   
## Приложения навигации  
 Приложения навигации могут не поддерживать состояние пользователя.  Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> восстанавливает свои элементы управления в случае его использования в приложении навигации.  Восстановление дочерних элементов управления происходит, когда пользователь выходит за переделы страницы, размещающей элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>, а затем возвращается на нее.  Любое содержимое, введенное пользователем, будет потеряно.  
  
<a name="message_loop_interoperation"></a>   
## Взаимодействие с циклом обработки сообщений  
 При работе с циклом обработки сообщений [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], сообщения могут обрабатываться не так, как ожидается.  Метод <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> вызывается конструктором <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Этот метод добавляет фильтр сообщений к циклу обработки сообщений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Этот фильтр вызывает метод <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=fullName> в случае, если <xref:System.Windows.Forms.Control?displayProperty=fullName> являлся целью сообщения, и переводит либо отправляет сообщение.  
  
 Если отобразить <xref:System.Windows.Window> в цикле обработки сообщения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] с <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>, то вы не сможете что\-либо печатать до тех пор, пока не вызовете метод <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>.  Метод <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> принимает объект <xref:System.Windows.Window> и добавляет интерфейс <xref:System.Windows.Forms.IMessageFilter?displayProperty=fullName>, который перенаправляет связанные с ключом сообщения в цикл обработки сообщений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Дополнительные сведения см. в разделе [Windows Forms и архитектура ввода взаимодействия WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>   
## Непрозрачность и иерархическое представление  
 Класс <xref:System.Windows.Interop.HwndHost> не поддерживает иерархическое представление.  Это означает, что установка свойства <xref:System.Windows.UIElement.Opacity%2A> в элементе <xref:System.Windows.Forms.Integration.WindowsFormsHost> не дает результата, и не произойдет смешение с другими окнами [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], свойству <xref:System.Windows.Window.AllowsTransparency%2A> которых присвоено значение `true`.  
  
<a name="dispose"></a>   
## Dispose  
 Неудаленные классы вполне могут дать утечку ресурсов.  В смешанных приложениях убедитесь, что удалены классы <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost>, в противном случае можно потерять ресурсы.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] удаляет элементы управления <xref:System.Windows.Forms.Integration.ElementHost>, если закрывается его немодальный родительский элемент <xref:System.Windows.Forms.Form>. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] удаляет элементы <xref:System.Windows.Forms.Integration.WindowsFormsHost> при завершении работы приложения.  Можно отобразить элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> в <xref:System.Windows.Window> в цикле обработки сообщений [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  В этом случае ваш код может не получить уведомление о том, что приложение завершает работу.  
  
<a name="enabling_visual_styles"></a>   
## Включение визуальных стилей  
 Визуальные стили [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] в элементе управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] могут быть недоступны.  Метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName> вызывается в шаблоне для приложения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Хотя этот метод не вызова по умолчанию при использовании [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] чтобы создать проект, появится визуальные стили [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] для элементов управления, если версия 6.0 доступен Comctl32.dll. Необходимо вызвать метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> до маркеров созданы в потоке.  Дополнительные сведения см. в разделе [Практическое руководство. Включение визуальных стилей в гибридном приложении](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>   
## Лицензированные элементы управления  
 Лицензированные элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], отображающие в окне сообщения информацию о лицензировании, могут вызвать непредвиденное поведение для смешанного приложения.  Некоторые лицензированные элементы управления отображают диалоговое окно в ответ на создание обработчика.  Например, лицензированный элемент управления может информировать пользователя о том, что нужна лицензия, или о том, что пользователю осталось три пробных запуска элемента управления.  
  
 Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> получается из класса <xref:System.Windows.Interop.HwndHost>, а обработчик дочернего элемента управления создается внутри метода <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>.  Класс <xref:System.Windows.Interop.HwndHost> не позволяет сообщениям обрабатываться в методе <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>, но отображение диалогового окна вызывает сообщения для отправки.  Чтобы включить этот скрипт лицензирования, вызовите метод <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=fullName> на элемент управления перед тем, как назначить его дочерним элементом <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="wpf_designer"></a>   
## конструктор WPF  
 Можно разработать содержимое WPF посредством [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].  В следующих разделах перечислены некоторые общие проблемы, которые могут возникнуть при создании смешанных приложений с помощью [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
### Во время разработки игнорируется BackColorTransparent  
 Во время разработки свойство <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> может не работать должным образом.  
  
 Если элемент управления WPF не находится на видимом родителе, исполняющая среда WPF игнорирует значение <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>.  Причина того, что <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> может быть проигнорирован, заключается в том, что объект <xref:System.Windows.Forms.Integration.ElementHost> создается в отдельном <xref:System.AppDomain>.  Однако, при запуске приложения <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> не работает должным образом.  
  
### При удалении папки obj появляется список ошибок времени разработки.  
 Если удалена папка obj, то появляется список ошибок времени разработки.  
  
 При разработке с использованием <xref:System.Windows.Forms.Integration.ElementHost> конструктор Windows Forms используют созданные файлы в папке Debug или Release внутри папки проекта obj.  При удалении этих файлов появляется список ошибок времени разработки.  Для устранения этой проблемы следует перестроить проект.  Дополнительные сведения см. в разделе [Ошибки во время разработки в конструкторе Windows Forms Designer](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>   
## ElementHost и IME  
 Элементы управления WPF, в данный момент размещенные в <xref:System.Windows.Forms.Integration.ElementHost>, не поддерживают свойство <xref:System.Windows.Forms.Control.ImeMode%2A>.  Изменение на <xref:System.Windows.Forms.Control.ImeMode%2A> будет проигнорировано размещенными элементами управления.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Взаимодействие в конструкторе WPF](http://msdn.microsoft.com/ru-ru/2cb7c1ca-2a75-463b-8801-fba81e2b7042)   
 [Windows Forms и архитектура ввода взаимодействия WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md)   
 [Практическое руководство. Включение визуальных стилей в гибридном приложении](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)   
 [Вопросы, связанные с макетом элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)   
 [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [Ошибки во время разработки в конструкторе Windows Forms Designer](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)   
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)