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
ms.openlocfilehash: 7af110b9b00b080bf40bc9ee4b85aa293940bbc3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794266"
---
# <a name="troubleshooting-hybrid-applications"></a>Устранение неполадок смешанных приложений
<a name="introduction"></a>В этом разделе перечислены некоторые распространенные проблемы, которые могут возникнуть при создании гибридных приложений, использующих технологии [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и Windows Forms.  

<a name="overlapping_controls"></a>   
## <a name="overlapping-controls"></a>Перекрывающиеся элементы управления  
 Элементы управления могут не перекрываться должным образом. Windows Forms использует отдельный HWND для каждого элемента управления. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует один HWND для всего содержимого на странице. Это отличие в реализации вызывает неожиданные перекрывающиеся поведения.  
  
 Элемент управления Windows Forms, размещенный в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], всегда отображается поверх содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое, размещенное в элементе управления <xref:System.Windows.Forms.Integration.ElementHost>, отображается в z-порядке элемента управления <xref:System.Windows.Forms.Integration.ElementHost>. Возможно перекрытие <xref:System.Windows.Forms.Integration.ElementHost> элементов управления, но содержимое размещенного [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не сочетается и не взаимодействует.  
  
<a name="child_property"></a>   
## <a name="child-property"></a>Дочернее свойство  
 Классы <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> могут содержать только один дочерний элемент управления или элемент. Для размещения нескольких элементов управления или элементов необходимо использовать контейнер в качестве дочернего содержимого. Например, можно добавить Windows Forms кнопки и элементы управления "флажок" в элемент управления <xref:System.Windows.Forms.Panel?displayProperty=nameWithType>, а затем назначить панель свойству <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента управления. Однако элементы управления "Кнопка" и "флажок" нельзя добавлять отдельно в тот же элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="scaling"></a>   
## <a name="scaling"></a>Масштабирование  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и Windows Forms имеют различные модели масштабирования. Некоторые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] преобразования масштабирования имеют смысл для Windows Forms элементов управления, но другие — нет. Например, масштабирование элемента управления Windows Forms на 0 будет работать, но при попытке масштабировать тот же элемент управления назад к ненулевому значению размер элемента управления остается равным 0. Дополнительные сведения см. в разделе [Вопросы, связанные с макетом элемента WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>   
## <a name="adapter"></a>Адаптер  
 При работе с классами <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> может возникнуть путаница, так как они включают в себя скрытый контейнер. Классы <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> имеют скрытый контейнер, называемый *адаптером*, который используется для размещения содержимого. Для элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> адаптер является производным от класса <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType>. Для элемента управления <xref:System.Windows.Forms.Integration.ElementHost> адаптер является производным от элемента <xref:System.Windows.Controls.DockPanel>. При появлении ссылок на адаптер в других разделах взаимодействия, этот контейнер становится контейнером, о котором шла речь.  
  
<a name="nesting"></a>   
## <a name="nesting"></a>Вложение  
 Вложение элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> в элемент управления <xref:System.Windows.Forms.Integration.ElementHost> не поддерживается. Вложение элемента управления <xref:System.Windows.Forms.Integration.ElementHost> внутрь элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> также не поддерживается.  
  
<a name="focus"></a>   
## <a name="focus"></a>Фокус  
 Фокус работает по-разному в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и Windows Forms. Это означает, что в гибридном приложении могут возникнуть проблемы, связанные с фокусом. Например, если фокус находится внутри элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> и вы либо уменьшаете и восстанавливаете страницу, либо отображаете модальное диалоговое окно, фокус внутри элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> может быть утерян. Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> по-прежнему имеет фокус, но элемент управления внутри него может не иметь.  
  
 Фокус также влияет и на проверку данных. Проверка работает в элементе <xref:System.Windows.Forms.Integration.WindowsFormsHost>, но не работает при выходе из элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> или между двумя различными элементами <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="property_mapping"></a>   
## <a name="property-mapping"></a>Сопоставление свойств  
 Для некоторых сопоставлений свойств требуется расширенная интерпретация для моста несхожих реализаций между технологиями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и Windows Forms. Сопоставления свойств позволяют коду реагировать на изменения в шрифтах, цветах и других свойствах. В общем случае сопоставление свойств работает посредством прослушивания событий *Property*Changed или вызовов On*Property*Changed и установки свойств либо в дочернем элементе управления, либо в его адаптере. Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## <a name="layout-related-properties-on-hosted-content"></a>Связанные с макетом свойства в размещенном содержимом  
 При назначении свойства <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType> в размещенном содержимом автоматически устанавливаются несколько свойств, связанных с макетом. Изменение этих свойств содержимого может привести к неожиданным поведениям макета.  
  
 Размещенное содержимое закреплено для заполнения <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> родителя. Чтобы включить это поведение заполнения, некоторые свойства задаются при установке дочернего свойства. В следующей таблице перечислены свойства содержимого, заданные классами <xref:System.Windows.Forms.Integration.ElementHost> и <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
|Класс узла|Свойства содержимого|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 Не устанавливайте эти свойства непосредственно в размещенном содержимом. Дополнительные сведения см. в разделе [Вопросы, связанные с макетом элемента WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>   
## <a name="navigation-applications"></a>Приложения навигации  
 Приложения навигации могут не поддерживать состояние пользователя. Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> воссоздает свои элементы управления при использовании в приложении навигации. Повторное создание дочерних элементов управления происходит, когда пользователь выходит из страницы, на которой размещен элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>, а затем возвращается к нему. Любое содержимое, введенное пользователем, будут потеряно.  
  
<a name="message_loop_interoperation"></a>   
## <a name="message-loop-interoperation"></a>Взаимодействие с циклом обработки сообщений  
 При работе с Windows Forms циклами сообщений сообщения могут обрабатываться не так, как ожидалось. Метод <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> вызывается конструктором <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Этот метод добавляет фильтр сообщений к циклу обработки сообщений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот фильтр вызывает метод <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType>, если <xref:System.Windows.Forms.Control?displayProperty=nameWithType> является целью сообщения и переводит или отправляет сообщение.  
  
 Если в Windows Formsном цикле обработки сообщений отображается <xref:System.Windows.Window> с <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>, то нельзя ввести ничего, если не вызвать метод <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>. Метод <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> принимает <xref:System.Windows.Window> и добавляет <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>, который перенаправляет сообщения, связанные с ключами, в цикл сообщений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Дополнительные сведения см. в разделе [Windows Forms и архитектура ввода взаимодействия WPF](windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>   
## <a name="opacity-and-layering"></a>Непрозрачность и организация по уровням  
 Класс <xref:System.Windows.Interop.HwndHost> не поддерживает иерархическое размещение. Это означает, что установка свойства <xref:System.Windows.UIElement.Opacity%2A> в элементе <xref:System.Windows.Forms.Integration.WindowsFormsHost> не оказывает никакого влияния и смешение других окон [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], для которых <xref:System.Windows.Window.AllowsTransparency%2A> задано значение `true`, не выполняется.  
  
<a name="dispose"></a>   
## <a name="dispose"></a>Ликвидировать  
 Неудаленные классы вполне могут дать утечку ресурсов. В гибридных приложениях убедитесь, что классы <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> удалены, или вы можете утечку ресурсов. Windows Forms удаляет <xref:System.Windows.Forms.Integration.ElementHost> элементы управления при закрытии немодального <xref:System.Windows.Forms.Form> родительского элемента. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] удаляет элементы <xref:System.Windows.Forms.Integration.WindowsFormsHost> при завершении работы приложения. Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> можно отобразить в <xref:System.Windows.Window> в Windows Forms цикле обработки сообщений. В этом случае код может не получить уведомление о том, что приложение завершает работу.  
  
<a name="enabling_visual_styles"></a>   
## <a name="enabling-visual-styles"></a>Включение стилей оформления  
 Возможно, стили оформления Microsoft Windows XP в элементе управления Windows Forms не включены. Метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> вызывается в шаблоне для приложения Windows Forms. Хотя этот метод не вызывается по умолчанию, если вы используете Visual Studio для создания проекта, вы получаете визуальные стили Microsoft Windows XP для элементов управления, если доступна версия Comctl32. dll версии 6,0. Перед созданием дескрипторов в потоке необходимо вызвать метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>. Дополнительные сведения см. в разделе [Практическое руководство. Включение визуальных стилей в гибридном приложении](how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>   
## <a name="licensed-controls"></a>Лицензированные элементы управления  
 Лицензированные Windows Forms элементы управления, которые отображают сведения о лицензировании в окне сообщения, могут привести к непредвиденному поведению гибридного приложения. Некоторые лицензированные элементы управления отображают диалоговое окно в ответ на создание обработчика. Например, лицензированный элемент управления может информировать пользователя о том, что нужна лицензия, или о том, что у пользователя осталось три пробных запуска элемента управления.  
  
 Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> является производным от класса <xref:System.Windows.Interop.HwndHost>, а маркер дочернего элемента управления создается внутри метода <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>. Класс <xref:System.Windows.Interop.HwndHost> не разрешает обработку сообщений в методе <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>, но отображение диалогового окна приводит к отправке сообщений. Чтобы включить этот сценарий лицензирования, вызовите метод <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> для элемента управления перед тем, как назначить его дочернему элементу <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="wpf_designer"></a>   
## <a name="wpf-designer"></a>сред. Конструктор WPF  
 Вы можете спроектировать содержимое WPF с помощью конструктора WPF для Visual Studio. В следующих разделах перечислены некоторые распространенные проблемы, которые могут возникнуть при создании гибридных приложений с помощью конструктора WPF.  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>Во время разработки игнорируется BackColorTransparent  
 Свойство <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> может работать не так, как ожидалось во время разработки.  
  
 Если элемент управления WPF не находится на видимом родителе, среда выполнения WPF игнорирует значение <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>. Причина, по которой <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> может быть проигнорирована, заключается в том, что <xref:System.Windows.Forms.Integration.ElementHost> объект создается в отдельном <xref:System.AppDomain>. Однако при запуске приложения <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> работает должным образом.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>При удалении папки obj появляется список ошибок времени разработки  
 Если удаляется папка obj, появляется список ошибок времени разработки.  
  
 При проектировании с помощью <xref:System.Windows.Forms.Integration.ElementHost>конструктор Windows Forms использует созданные файлы в папке Debug или Release в папке obj проекта. При удалении этих файлов появляется список ошибок времени разработки. Для устранения этой проблемы следует перестроить проект. Дополнительные сведения см. в разделе [Ошибки во время разработки в конструкторе Windows Forms](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>   
## <a name="elementhost-and-ime"></a>ElementHost и IME  
 Элементы управления WPF, размещенные в <xref:System.Windows.Forms.Integration.ElementHost>, в настоящее время не поддерживают свойство <xref:System.Windows.Forms.Control.ImeMode%2A>. Изменения <xref:System.Windows.Forms.Control.ImeMode%2A> будут игнорироваться размещаемыми элементами управления.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Взаимодействие в конструкторе WPF](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Windows Forms и архитектура ввода взаимодействия WPF](windows-forms-and-wpf-interoperability-input-architecture.md)
- [Практическое руководство. Включение визуальных стилей в гибридном приложении](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [Вопросы, связанные с макетом элемента WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md)
- [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md)
- [Ошибки во время разработки в конструкторе Windows Forms](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [Миграция и взаимодействие систем](migration-and-interoperability.md)
