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
ms.openlocfilehash: b85a607d2e44d6253359a81118f90e6ee05d2d3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187327"
---
# <a name="troubleshooting-hybrid-applications"></a>Устранение неполадок смешанных приложений
<a name="introduction"></a>В этой теме перечислены некоторые общие проблемы, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] которые могут возникнуть при авторизации гибридных приложений, которые используют как технологии Windows, так и windows Forms.  

<a name="overlapping_controls"></a>
## <a name="overlapping-controls"></a>Перекрывающиеся элементы управления  
 Элементы управления могут не перекрываться должным образом. Формы Windows используют отдельный HWND для каждого элемента управления. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует один HWND для всего содержимого на странице. Это отличие в реализации вызывает неожиданные перекрывающиеся поведения.  
  
 Элемент управления Windows [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Forms, размещенный [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в всегда появляется поверх содержимого.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]содержимое, <xref:System.Windows.Forms.Integration.ElementHost> размещенное в элементе <xref:System.Windows.Forms.Integration.ElementHost> управления, отображается в z-заказе элемента управления. Можно перекрывать <xref:System.Windows.Forms.Integration.ElementHost> элементы управления, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] но размещенный контент не комбинируети и не взаимодействуют.  
  
<a name="child_property"></a>
## <a name="child-property"></a>Дочернее свойство  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> Классы <xref:System.Windows.Forms.Integration.ElementHost> могут размещать только один элемент или элемент ребенка. Для размещения нескольких элементов управления или элементов необходимо использовать контейнер в качестве дочернего содержимого. Например, можно добавить кнопку Windows Forms <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> и проверить элементы управления, <xref:System.Windows.Forms.Integration.WindowsFormsHost> а <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> затем назначить панель свойству управления. Тем не менее, вы не можете добавить <xref:System.Windows.Forms.Integration.WindowsFormsHost> кнопку и контрольно-пропускной ящик управления отдельно к тому же управлению.  
  
<a name="scaling"></a>
## <a name="scaling"></a>Масштабирование  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]и Формы Windows имеют различные модели масштабирования. Некоторые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] преобразования масштабирования имеют значение для элементов управления Windows Forms, но другие — нет. Например, масштабирование элемента управления Windows Forms до 0 будет работать, но если вы попытаетесь масштабировать тот же элемент управления до ненулевого значения, размер элемента управления останется 0. Дополнительные сведения см. в разделе [Вопросы, связанные с макетом элемента WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>
## <a name="adapter"></a>Адаптер  
 Там может быть путаница при работе <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> классов, потому что они включают скрытый контейнер. Оба <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost> классы имеют скрытый контейнер, называемый *адаптер*, который они используют для размещения содержимого. Для <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента адаптер вытекает <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType> из класса. Для <xref:System.Windows.Forms.Integration.ElementHost> управления адаптер вытекает <xref:System.Windows.Controls.DockPanel> из элемента. При появлении ссылок на адаптер в других разделах взаимодействия, этот контейнер становится контейнером, о котором шла речь.  
  
<a name="nesting"></a>
## <a name="nesting"></a>Вложенные операторы  
 Вложение <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента <xref:System.Windows.Forms.Integration.ElementHost> внутри элемента не поддерживается. Вложение <xref:System.Windows.Forms.Integration.ElementHost> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> внутри элемента также не поддерживается.  
  
<a name="focus"></a>
## <a name="focus"></a>Focus  
 Фокус работает по-разному в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и Windows Forms, что означает, что проблемы фокуса могут возникнуть в гибридном приложении. Например, если у вас <xref:System.Windows.Forms.Integration.WindowsFormsHost> есть фокус внутри элемента, и вы либо свести к <xref:System.Windows.Forms.Integration.WindowsFormsHost> минимуму и восстановить страницу или показать модальный диалоговые окна, фокус внутри элемента может быть потерян. Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> по-прежнему имеет фокус, но элемент внутри него не может.  
  
 Фокус также влияет и на проверку данных. Проверка работает в <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементе, но она не работает, <xref:System.Windows.Forms.Integration.WindowsFormsHost> как вы вкладке из элемента, или между двумя различными <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементами.  
  
<a name="property_mapping"></a>
## <a name="property-mapping"></a>Сопоставление свойств  
 Некоторые отображения свойств требуют обширной интерпретации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для преодоления различных реализаций между технологиями Windows Forms. Сопоставления свойств позволяют коду реагировать на изменения в шрифтах, цветах и других свойствах. В общем случае сопоставление свойств работает посредством прослушивания событий *Property*Changed или вызовов On*Property*Changed и установки свойств либо в дочернем элементе управления, либо в его адаптере. Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>
## <a name="layout-related-properties-on-hosted-content"></a>Связанные с макетом свойства в размещенном содержимом  
 При <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> присвоении <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType> или свойстве несколько свойств, связанных с макетом, на размещенном содержимом устанавливаются автоматически. Изменение этих свойств содержимого может привести к неожиданным поведениям макета.  
  
 Ваше размещенное содержимое <xref:System.Windows.Forms.Integration.WindowsFormsHost> пристыковано для заполнения родительского и <xref:System.Windows.Forms.Integration.ElementHost> родительского содержимого. Чтобы включить это поведение заполнения, некоторые свойства задаются при установке дочернего свойства. В следующей таблице перечислены свойства <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost> содержимого, установленные классами и классами.  
  
|Класс узла|Свойства содержимого|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 Не устанавливайте эти свойства непосредственно в размещенном содержимом. Дополнительные сведения см. в разделе [Вопросы, связанные с макетом элемента WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>
## <a name="navigation-applications"></a>Приложения навигации  
 Приложения навигации могут не поддерживать состояние пользователя. Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> воссоздает элемент управления при использовании в навигационном приложении. Воссоздание элемента управления детьми происходит, когда <xref:System.Windows.Forms.Integration.WindowsFormsHost> пользователь перемещается подальше от страницы, размещающей элемент, а затем возвращается к нему. Любое содержимое, введенное пользователем, будут потеряно.  
  
<a name="message_loop_interoperation"></a>
## <a name="message-loop-interoperation"></a>Взаимодействие с циклом обработки сообщений  
 При работе с циклами сообщений Windows Forms сообщения могут обрабатываться не так, как ожидалось. Метод <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> называется <xref:System.Windows.Forms.Integration.WindowsFormsHost> конструктором. Этот метод добавляет фильтр сообщений к циклу обработки сообщений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Этот фильтр <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> вызывает метод, если <xref:System.Windows.Forms.Control?displayProperty=nameWithType> был целью сообщения, и переводит/отправляет сообщение.  
  
 Если вы <xref:System.Windows.Window> показываете цикл сообщения <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>Форм Windows с помощью, <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> вы не можете ввести что-либо, если вы называете метод. Метод <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> принимает <xref:System.Windows.Window> и <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>добавляет, который перенаправляет ключевые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сообщения в цикл сообщения. Дополнительные сведения см. в разделе [Windows Forms и архитектура ввода взаимодействия WPF](windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>
## <a name="opacity-and-layering"></a>Непрозрачность и организация по уровням  
 Класс <xref:System.Windows.Interop.HwndHost> не поддерживает наслоение. Это означает, <xref:System.Windows.UIElement.Opacity%2A> что установка <xref:System.Windows.Forms.Integration.WindowsFormsHost> свойства элемента не имеет никакого эффекта, и не будет происходить смешивание с другими [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] окнами, которые установили. <xref:System.Windows.Window.AllowsTransparency%2A> `true`  
  
<a name="dispose"></a>
## <a name="dispose"></a>Dispose  
 Неудаленные классы вполне могут дать утечку ресурсов. В гибридных приложениях убедитесь, что <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> классы удалены, или вы можете утечки ресурсов. Формы Windows <xref:System.Windows.Forms.Integration.ElementHost> утилизируют элементы <xref:System.Windows.Forms.Form> управления при закрытии родительского элемента. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]удаляет <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементы при выключении приложения. Можно показать <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент <xref:System.Windows.Window> в цикле сообщений Форм Windows. В этом случае код может не получить уведомление о том, что приложение завершает работу.  
  
<a name="enabling_visual_styles"></a>
## <a name="enabling-visual-styles"></a>Включение стилей оформления  
 Визуальные стили Microsoft Windows XP в элементе управления Windows Forms не могут быть включены. Метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> называется в шаблоне для приложения Windows Forms. Хотя этот метод не называется по умолчанию, если вы используете Visual Studio для создания проекта, вы получите Microsoft Windows XP визуальные стили для элементов управления, если версия 6.0 Comctl32.dll доступна. Необходимо вызвать <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод до создания ручек на потоке. Дополнительные сведения см. в разделе [Практическое руководство. Включение визуальных стилей в гибридном приложении](how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>
## <a name="licensed-controls"></a>Лицензированные элементы управления  
 Лицензированные элементы управления Windows Forms, которые отображают информацию о лицензировании в поле сообщений для пользователя, могут привести к неожиданному поведению гибридного приложения. Некоторые лицензированные элементы управления отображают диалоговое окно в ответ на создание обработчика. Например, лицензированный элемент управления может информировать пользователя о том, что нужна лицензия, или о том, что у пользователя осталось три пробных запуска элемента управления.  
  
 Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> происходит от <xref:System.Windows.Interop.HwndHost> класса, и ручка управления ребенком <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> создается внутри метода. Класс <xref:System.Windows.Interop.HwndHost> не позволяет обрабатывать сообщения в <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> методе, но отображение диалогового окна приводит к отправке сообщений. Чтобы включить этот сценарий <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> лицензирования, позвоните методу управления, прежде чем назначить его в качестве ребенка <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.  
  
<a name="wpf_designer"></a>
## <a name="wpf-designer"></a>Конструктор WPF  
 Вы можете создать свой контент WPF с помощью WPF Designer для visual Studio. В следующих разделах перечисляются некоторые общие проблемы, которые могут возникнуть при авторизации гибридных приложений с конструктором WPF.  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>Во время разработки игнорируется BackColorTransparent  
 Свойство <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> может работать не так, как ожидалось во время проектирования.  
  
 Если элемент управления WPF не находится на видимом родительском <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> элементе, время выполнения WPF игнорирует значение. Причина, <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> по которой может <xref:System.Windows.Forms.Integration.ElementHost> быть проигнорирована, <xref:System.AppDomain>заключается в том, что объект создается в отдельном . Однако при запуске <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> приложения работает как ожидалось.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>При удалении папки obj появляется список ошибок времени разработки  
 Если удаляется папка obj, появляется список ошибок времени разработки.  
  
 При проектировании <xref:System.Windows.Forms.Integration.ElementHost>с помощью — дизайнер форм Windows использует генерируемые файлы в папке Debug или Release в папке obj проекта. При удалении этих файлов появляется список ошибок времени разработки. Для устранения этой проблемы следует перестроить проект. Дополнительные сведения см. в разделе [Ошибки во время разработки в конструкторе Windows Forms](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>
## <a name="elementhost-and-ime"></a>ElementHost и IME  
 Контроль WPF, <xref:System.Windows.Forms.Integration.ElementHost> размещенный в <xref:System.Windows.Forms.Control.ImeMode%2A> настоящее время, не поддерживает свойство. Изменения <xref:System.Windows.Forms.Control.ImeMode%2A> будут проигнорированы размещенными элементами управления.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Взаимодействие в конструкторе WPF](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Windows Forms и архитектура ввода взаимодействия WPF](windows-forms-and-wpf-interoperability-input-architecture.md)
- [Практическое руководство. Включение визуальных стилей в гибридном приложении](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [Вопросы, связанные с макетом элемента WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md)
- [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md)
- [Ошибки во время разработки в конструкторе Windows Forms](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [Миграция и взаимодействие систем](migration-and-interoperability.md)
