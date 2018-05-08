---
title: Устранение неполадок смешанных приложений
ms.date: 03/30/2017
helpviewer_keywords:
- overlapping controls [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid applications [WPF interoperability]
- message loops [WPF]
ms.assetid: f440c23f-fa5d-4d5a-852f-ba61150e6405
ms.openlocfilehash: 878761c030d4950e53ee24b76f7e29101584143a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-hybrid-applications"></a>Устранение неполадок смешанных приложений
<a name="introduction"></a> В этом разделе перечислены некоторые общие проблемы, которые могут возникать при создании смешанных приложений, одновременно использующих технологии [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  

  
<a name="overlapping_controls"></a>   
## <a name="overlapping-controls"></a>Перекрывающиеся элементы управления  
 Элементы управления могут не перекрываться должным образом. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] использует отдельный HWND для каждого элемента управления. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует один HWND для всего содержимого на странице. Это отличие в реализации вызывает неожиданные перекрывающиеся поведения.  
  
 Элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], размещенный в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], всегда появляется в верхней части содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое размещается в <xref:System.Windows.Forms.Integration.ElementHost> элемент управления в z порядок для <xref:System.Windows.Forms.Integration.ElementHost> элемента управления. Можно перекрывать <xref:System.Windows.Forms.Integration.ElementHost> элементы управления, но размещаемый [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое объединяется и не взаимодействует.  
  
<a name="child_property"></a>   
## <a name="child-property"></a>Дочернее свойство  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> И <xref:System.Windows.Forms.Integration.ElementHost> классов может содержать только один дочерний элемент управления или элемент. Для размещения нескольких элементов управления или элементов необходимо использовать контейнер в качестве дочернего содержимого. Например, можно добавить [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] кнопки, флажки и элементы управления для <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> управления, а затем назначить панель, которая <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> свойство. Однако нельзя добавлять элементы управления и флажков отдельно к тому же <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента управления.  
  
<a name="scaling"></a>   
## <a name="scaling"></a>Масштабирование  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] имеют разные модели масштабирования. Некоторые преобразования масштаба [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являются показательными для элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], а некоторые — нет. Например, масштабирование элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] к 0 будет работать, но если попытаться масштабировать тот же элемент управления обратно на ненулевое значение, то размер элемента управления останется равным 0. Дополнительные сведения см. в разделе [Вопросы, связанные с макетом элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>   
## <a name="adapter"></a>Адаптер  
 Путаница может быть при работе <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> классы, так как они содержат скрытый контейнер. Как <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> классы имеют скрытые контейнеры, с именем *адаптер*, которые они используют для размещения содержимого. Для <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент, адаптер является производным от <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType> класса. Для <xref:System.Windows.Forms.Integration.ElementHost> -элемент управления, наследует адаптер <xref:System.Windows.Controls.DockPanel> элемента. При появлении ссылок на адаптер в других разделах взаимодействия, этот контейнер становится контейнером, о котором шла речь.  
  
<a name="nesting"></a>   
## <a name="nesting"></a>Вложение  
 Вложение <xref:System.Windows.Forms.Integration.WindowsFormsHost> внутри <xref:System.Windows.Forms.Integration.ElementHost> элемент управления не поддерживается. Вложение <xref:System.Windows.Forms.Integration.ElementHost> управления внутри <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент также не поддерживается.  
  
<a name="focus"></a>   
## <a name="focus"></a>Фокус  
 Фокус работает по-разному в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], что означает, что в смешанном приложении могут возникать проблемы с фокусом. Например, если имеется фокус внутри <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент и вы можете либо свести к минимуму и восстановить страницу или отображает модальное диалоговое окно, фокус внутри <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента могут быть потеряны. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент по-прежнему имеет фокус, но не имеете права управления внутри него.  
  
 Фокус также влияет и на проверку данных. Проверка работает в <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент, но он не работает при выходе из <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент, или между двумя разными <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементов.  
  
<a name="property_mapping"></a>   
## <a name="property-mapping"></a>Сопоставление свойств  
 Некоторые сопоставления свойств требуют всесторонней интерпретации для того, чтобы связать отличающиеся реализации между технологиями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Сопоставления свойств позволяют коду реагировать на изменения в шрифтах, цветах и других свойствах. В общем случае сопоставление свойств работает посредством прослушивания событий *Property*Changed или вызовов On*Property*Changed и установки свойств либо в дочернем элементе управления, либо в его адаптере. Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## <a name="layout-related-properties-on-hosted-content"></a>Связанные с макетом свойства в размещенном содержимом  
 Когда <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType> присваивается, несколько свойств, относящихся к макету для размещенного содержимого устанавливаются автоматически. Изменение этих свойств содержимого может привести к неожиданным поведениям макета.  
  
 Размещенное содержимое присоединяется для заполнения <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> родительского. Чтобы включить это поведение заполнения, некоторые свойства задаются при установке дочернего свойства. В следующей таблице перечислены свойства содержимого, установленный с <xref:System.Windows.Forms.Integration.ElementHost> и <xref:System.Windows.Forms.Integration.WindowsFormsHost> классы.  
  
|Класс узла|Свойства содержимого|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 Не устанавливайте эти свойства непосредственно в размещенном содержимом. Дополнительные сведения см. в разделе [Вопросы, связанные с макетом элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>   
## <a name="navigation-applications"></a>Приложения навигации  
 Приложения навигации могут не поддерживать состояние пользователя. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент и повторно создает ее элементов управления при использовании в приложении навигации. Повторное создание дочерних элементов управления происходит, когда пользователь выходит из размещение страницы <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент и затем возвращается на нее. Любое содержимое, введенное пользователем, будут потеряно.  
  
<a name="message_loop_interoperation"></a>   
## <a name="message-loop-interoperation"></a>Взаимодействие с циклом обработки сообщений  
 При работе с циклом обработки сообщений [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сообщения могут обрабатываться не так, как ожидалось. <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> Метод вызывается методом <xref:System.Windows.Forms.Integration.WindowsFormsHost> конструктор. Этот метод добавляет фильтр сообщений к циклу обработки сообщений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот фильтр вызывает <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> метод Если <xref:System.Windows.Forms.Control?displayProperty=nameWithType> целевой сообщение и преобразует отправляет сообщение.  
  
 При отображении <xref:System.Windows.Window> в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] цикл обработки сообщений с <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>, ничего нельзя ввести только при вызове <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> метода. <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> Принимает <xref:System.Windows.Window> и добавляет <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>, который перенаправляет связанные с ключом сообщения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] цикл обработки сообщений. Дополнительные сведения см. в разделе [Windows Forms и архитектура ввода взаимодействия WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>   
## <a name="opacity-and-layering"></a>Непрозрачность и организация по уровням  
 <xref:System.Windows.Interop.HwndHost> Класс не поддерживает иерархическое представление. Это означает, что установка <xref:System.Windows.UIElement.Opacity%2A> свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент не действует, и не произойдет смешение с другими [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] windows, которые имеют <xref:System.Windows.Window.AllowsTransparency%2A> значение `true`.  
  
<a name="dispose"></a>   
## <a name="dispose"></a>Ликвидировать  
 Неудаленные классы вполне могут дать утечку ресурсов. Убедитесь, что в гибридных приложениях <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> удалены классы или может вызвать утечку ресурсов. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Удаляет <xref:System.Windows.Forms.Integration.ElementHost> управляет тем, когда его немодальный <xref:System.Windows.Forms.Form> родительских закрывается. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Удаляет <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементы, когда приложение завершает работу. Имеется возможность показывать <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент в <xref:System.Windows.Window> в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] цикл обработки сообщений. В этом случае код может не получить уведомление о том, что приложение завершает работу.  
  
<a name="enabling_visual_styles"></a>   
## <a name="enabling-visual-styles"></a>Включение стилей оформления  
 Визуальные стили [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] в элементе управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] могут быть недоступны. <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Метод вызывается в шаблоне для [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] приложения. Несмотря на то что этот метод не вызывается по умолчанию, если вы используете [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] для создания проекта, вы получите визуальные стили [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] для элементов управления, если доступен Comctl32.dll версии 6.0. Необходимо вызвать метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод перед созданием дескрипторов в потоке. Дополнительные сведения см. в разделе [Практическое руководство. Включение визуальных стилей в гибридном приложении](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>   
## <a name="licensed-controls"></a>Лицензированные элементы управления  
 Лицензированные элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], отображающие в окне сообщения информацию о лицензировании, могут вызвать непредвиденное поведение для смешанного приложения. Некоторые лицензированные элементы управления отображают диалоговое окно в ответ на создание обработчика. Например, лицензированный элемент управления может информировать пользователя о том, что нужна лицензия, или о том, что у пользователя осталось три пробных запуска элемента управления.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент является производным от <xref:System.Windows.Interop.HwndHost> класс и дочернего элемента управления создается внутри <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> метод. <xref:System.Windows.Interop.HwndHost> Класса не разрешает сообщения могут обрабатываться в <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> метода, но отображает диалоговое окно вызывает отправку сообщений. Чтобы включить этот скрипт лицензирования, вызовите <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> метод в элементе управления, прежде чем назначать его как <xref:System.Windows.Forms.Integration.WindowsFormsHost> дочерним элементом.  
  
<a name="wpf_designer"></a>   
## <a name="wpf-designer"></a>Конструктор WPF  
 Можно разработать содержимое WPF с помощью [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]. В следующих разделах перечислены некоторые общие проблемы, которые могут возникнуть при создании смешанных приложений с помощью [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>Во время разработки игнорируется BackColorTransparent  
 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> Свойство может не работать ожидаемым образом во время разработки.  
  
 Если элемент управления WPF не является видимым родительский, среда выполнения WPF игнорирует <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> значение. Причина, <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> может быть проигнорирован поскольку <xref:System.Windows.Forms.Integration.ElementHost> объект создается в отдельном <xref:System.AppDomain>. Тем не менее, при запуске приложения, <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> работает должным образом.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>При удалении папки obj появляется список ошибок времени разработки  
 Если удаляется папка obj, появляется список ошибок времени разработки.  
  
 При разработке с помощью <xref:System.Windows.Forms.Integration.ElementHost>, конструктор Windows Forms использует созданные файлы в папке Debug или Release в папку obj проекта. При удалении этих файлов появляется список ошибок времени разработки. Для устранения этой проблемы следует перестроить проект. Дополнительные сведения см. в разделе [Ошибки во время разработки в конструкторе Windows Forms](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>   
## <a name="elementhost-and-ime"></a>ElementHost и IME  
 Размещенные элементы управления WPF в <xref:System.Windows.Forms.Integration.ElementHost> в настоящее время не поддерживают <xref:System.Windows.Forms.Control.ImeMode%2A> свойство. Изменения <xref:System.Windows.Forms.Control.ImeMode%2A> размещенные элементы управления будут игнорироваться.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Взаимодействие в конструкторе WPF](http://msdn.microsoft.com/library/2cb7c1ca-2a75-463b-8801-fba81e2b7042)  
 [Windows Forms и архитектура ввода взаимодействия WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md)  
 [Практическое руководство. Включение визуальных стилей в гибридном приложении](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)  
 [Вопросы, связанные с макетом элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [Ошибки во время разработки в конструкторе Windows Forms](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
