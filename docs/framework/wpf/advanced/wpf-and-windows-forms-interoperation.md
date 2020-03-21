---
title: Формы WPF и Windows interop
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 76d1e97c92946267aa1217f52c93594fb63d20de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187149"
---
# <a name="wpf-and-windows-forms-interoperation"></a>Взаимодействие WPF и Windows Forms
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]и Windows Forms представляют две различные архитектуры для создания интерфейсов приложений. В <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> пространстве имен предусмотрены классы, позволяющие внедрить общие сценарии интероперации. Два ключевых класса, которые <xref:System.Windows.Forms.Integration.WindowsFormsHost> реализуют возможности интероперации, являются и <xref:System.Windows.Forms.Integration.ElementHost>. В этом разделе описано, какие сценарии взаимодействия поддерживаются, а какие нет.  
  
> [!NOTE]
> Особое внимание уделено сценарию *гибридного элемента управления*. Гибридный элемент управления — это элемент управления на основе одной технологии, в который вложен элемент управления на основе другой технологии. Это также называется *вложенным взаимодействием*. В *многоуровневом гибридном элементе управления* более одного уровня вложения. Примером многоуровневого вложенного интероперации является элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления форм Windows, содержащий элемент управления, содержащий другой элемент управления Windows Forms. Многоуровневые гибридные элементы управления не поддерживаются.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>
## <a name="hosting-windows-forms-controls-in-wpf"></a>Размещение элементов управления Windows Forms в WPF  
 Следующие сценарии интероперации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживаются при размещении элемента управления Windows Forms:  
  
- Элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления может размещать один или несколько элементов управления Windows Forms с помощью XAML.  
  
- Он может размещать один или несколько элементов управления Windows Forms с помощью кода.  
  
- Он может размещать элементы управления контейнерами Windows Forms, содержащие другие элементы управления Windows Forms.  
  
- Он может размещать форму мастера/детали с деталями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] master и Windows Forms.  
  
- Он может разместить форму мастера/детали с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] мастером форм Windows и деталями.  
  
- Он может размещать один или несколько элементов управления ActiveX.  
  
- В него могут быть вложены один или несколько составных элементов управления.  
  
- С помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] в него могут быть вложены гибридные элементы управления.  
  
- С помощью кода в него могут быть вложены гибридные элементы управления.  
  
### <a name="layout-support"></a>Поддержка макета  
 В следующем списке описаны <xref:System.Windows.Forms.Integration.WindowsFormsHost> известные ограничения, когда элемент пытается [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] интегрировать свой размещенный элемент управления Формами Windows в систему компоновки.  
  
- В некоторых случаях элементы управления Windows Forms не могут быть уменьшены или могут быть уменьшены только по определенным размерам. Например, элемент <xref:System.Windows.Forms.ComboBox> управления Windows Forms поддерживает только одну высоту, которая определяется размером шрифта элемента управления. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] динамической компоновке, которая предполагает, <xref:System.Windows.Forms.ComboBox> что элементы могут растягиваться вертикально, размещенный элемент управления не растянется, как ожидалось.  
  
- Элементы управления Windows Forms не могут быть повернуты или искажены. Например, при повороте пользовательского интерфейса на 90 градусов размещаемые элементы управления Windows Forms сохранят их вертикальное положение.  
  
- В большинстве случаев элементы управления Windows Forms не поддерживают пропорциональное масштабирование. Несмотря на то, что общий размер элемента управления масштабируется, дочерние элементы управления и компоненты элемента управления могут изменять размеры не так, как ожидается. Это ограничение зависит от того, насколько хорошо каждый элемент управления Windows Forms поддерживает масштабирование.  
  
- В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно изменить z-порядок элементов для контроля поведения перекрывания. Развлеченный элемент управления формами Windows нарисован в отдельном HWND, поэтому он всегда нарисован поверх элементов. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
- Формы Windows поддерживают автоматическое масштабирование в зависимости от размера шрифта. В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] изменение размера шрифта не влечет за собой изменение размера всего макета, хотя отдельные элементы могут динамически изменять размер.  
  
### <a name="ambient-properties"></a>Внешние свойства  
 Некоторые из свойств элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления имеют эквиваленты форм Windows. Эти окружающие свойства распространяются на размещенные элементы управления Windows <xref:System.Windows.Forms.Integration.WindowsFormsHost> Forms и размещаются в качестве общедоступных свойств на элементе управления. Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления преобразует [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] каждое свойство окружающего в эквивалент Windows Forms.  
  
 Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Поведение  
 В приведенной ниже таблице описаны возможности взаимодействия.  
  
|Поведение|Поддерживается|Не поддерживается|  
|--------------|---------------|-------------------|  
|Прозрачность|Элементуправления Windows Forms поддерживает прозрачность. Фон родительского [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления может стать фоном размещаемых элементов управления Windows Forms.|Некоторые элементы управления Windows Forms не поддерживают прозрачность. Например, <xref:System.Windows.Forms.TextBox> элементы управления и <xref:System.Windows.Forms.ComboBox> элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]управления не будут прозрачными при размещении.|  
|Переход по клавише TAB|Заказ на размещение элементов управления Windows Forms такой же, как и при размещении этих элементов управления в приложении на базе Windows Forms.<br /><br /> Вкладка от [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления к управлению формами Windows с ключом TAB и клавишами SHIFT-TAB работает в обычном режиме.<br /><br /> Элементы управления Windows <xref:System.Windows.Forms.Control.TabStop%2A> Forms, `false` которые имеют свойство значение не получают фокус, когда пользователь вкладок через элементы управления.<br /><br /> - <xref:System.Windows.Forms.Integration.WindowsFormsHost> Каждый <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> элемент управления имеет значение, которое определяет, когда этот <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент управления получит фокус.<br />- Элементы управления Windows <xref:System.Windows.Forms.Integration.WindowsFormsHost> Forms, содержащиеся внутри <xref:System.Windows.Forms.Control.TabIndex%2A> контейнера, соответствуют порядку, указанному отелем. При переходе от последнего индекса табуляции фокус получает следующий элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], если таковой существует. Если другого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] фокусируемого элемента управления не существует, табирование возвращается к первому управлению формами Windows в порядке вкладок.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>значения для элементов <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления внутри являются относительно элементов <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления образов Windows, которые содержатся в элементах управления.<br />— При переходе по табуляции учитывается модель поведения элемента управления. Например, нажатие клавиши <xref:System.Windows.Forms.TextBox> TAB в <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> элементе `true` управления, которое имеет значение свойства, вводит вкладку в текстовое поле вместо перемещения фокуса.|Неприменимо.|  
|Переход с помощью клавиш со стрелками|- Навигация со <xref:System.Windows.Forms.Integration.WindowsFormsHost> стрелками в элементе управления такая же, как и в обычном управлении контейнером Windows Forms: клавиши UP ARROW и LEFT ARROW выберите предыдущий элемент управления, а клавиши DOWN ARROW и RIGHT ARROW выберите следующий элемент управления.<br />- Клавиши UP ARROW и LEFT ARROW от <xref:System.Windows.Forms.Integration.WindowsFormsHost> первого элемента управления, содержащегося в элементе управления, выполняют то же действие, что и ярлык клавиатуры SHIFT-TAB. Если есть фокусируемый [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] контроль, фокус <xref:System.Windows.Forms.Integration.WindowsFormsHost> перемещается вне контроля. Такое поведение отличается <xref:System.Windows.Forms.ContainerControl> от стандартного поведения тем, что не происходит упаковка до последнего элемента управления. Если другого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] фокусируемого элемента управления не существует, фокус возвращается к последнему управлению формами Windows в порядке вкладок.<br />- КЛАВИШи DOWN ARROW и RIGHT ARROW от <xref:System.Windows.Forms.Integration.WindowsFormsHost> последнего элемента управления, содержащегося в элементе управления, выполняют то же действие, что и ключ TAB. Если есть фокусируемый [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] контроль, фокус <xref:System.Windows.Forms.Integration.WindowsFormsHost> перемещается вне контроля. Такое поведение отличается <xref:System.Windows.Forms.ContainerControl> от стандартного поведения тем, что не происходит упаковки к первому элементу управления. Если другого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] фокусируемого элемента управления не существует, фокус возвращается к первому управлению формами Windows в порядке вкладок.|Неприменимо.|  
|Клавиши быстрого доступа|Клавиши быстрого доступа работают как обычно, за исключением пунктов, оговоренных в столбце "Не поддерживается".|Повторяющиеся в различных технологиях клавиши быстрого доступа не работают как обычные повторяющиеся клавиши быстрого доступа. Когда ускоритель дублируется между технологиями, по крайней мере один из них [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] находится на элементе управления Windows Forms, а другой — на элементе управления, элемент управления Windows Forms всегда получает ускоритель. Фокус не переключается между элементами управления с одинаковыми клавишами быстрого доступа.|  
|Сочетание клавиш|Сочетания клавиш работают как обычно, за исключением пунктов, оговоренных в столбце "Не поддерживается".|- Ключи ярлыка Windows Forms, которые обрабатываются на этапе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предварительной обработки, всегда имеют приоритет над ключами ярлыка. Например, если у <xref:System.Windows.Forms.ToolStrip> вас есть элемент управления с определенными ключами быстрого сокращения CTRL-S, и есть [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] команда, связанная с CTRL-S, обработчик <xref:System.Windows.Forms.ToolStrip> управления всегда вызывается первым, независимо от фокусировки.<br />- Ключи ярлыка Windows Forms, <xref:System.Windows.Forms.Control.KeyDown> обрабатываемые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]событием, обрабатываются последними в. Предотвратить такое поведение можно, переопределив <xref:System.Windows.Forms.Control.IsInputKey%2A> метод <xref:System.Windows.Forms.Control.PreviewKeyDown> управления Windows Forms или обгонив событие. Возврат `true` из <xref:System.Windows.Forms.Control.IsInputKey%2A> метода или установите <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> значение `true` свойства <xref:System.Windows.Forms.Control.PreviewKeyDown> в обработчике событий.|  
|AcceptsReturn, AcceptsTab и другие специфические свойства элементов управления|Свойства, изменяющие поведение клавиатуры по умолчанию, работают <xref:System.Windows.Forms.Control.IsInputKey%2A> в `true`обычном режиме, предполагая, что контроль Форм Windows переопределяет способ возврата.|Элементы управления Windows, изменяющие <xref:System.Windows.Forms.Control.KeyDown> поведение клавиатуры по [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] умолчанию при обработке события, обрабатываются последними в элементе управления хоста. Так как эти элементы управления обрабатываются последними, они могут привести к непредвиденному поведению.|  
|События Enter и Leave|Когда фокус не переходит <xref:System.Windows.Forms.Integration.ElementHost> к элементу управления, события Enter and Leave возникают как обычно, когда фокус меняется в одном <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементе управления.|События Enter и Leave не вызываются при следующих переводах фокуса:<br /><br /> - Изнутри вне <xref:System.Windows.Forms.Integration.WindowsFormsHost> контроля.<br />- Снаружи внутрь <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления.<br />- Вне <xref:System.Windows.Forms.Integration.WindowsFormsHost> контроля.<br />- От управления Windows Forms, размещенного в элементе <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления, до элемента <xref:System.Windows.Forms.Integration.ElementHost> управления, размещенного внутри того же. <xref:System.Windows.Forms.Integration.WindowsFormsHost>|  
|Многопоточность|Поддерживаются все возможности многопоточности.|Как формы Windows, так и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] технологии предполагают однопоточной параллели. Во время отладки вызовы объектов платформы из других потоков будут вызывать исключение для принудительного выполнения этого требования.|  
|Безопасность|Все сценарии взаимодействия требуют полного доверия.|Не допускаются сценарии взаимодействия с частичным доверием.|  
|Возможности доступа|Поддерживаются все сценарии специальных возможностей. Вспомогательные технологические продукты функционируют правильно, когда они [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используются для гибридных приложений, которые содержат как формы Windows, так и элементы управления.|Неприменимо.|  
|Буфер обмена|Все операции с буфером обмена работают обычным образом. Это включает в себя резки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и вставки между формами Windows и элементов управления.|Неприменимо.|  
|Функция перетаскивания|Все операции перетаскивания работают обычным образом. Это включает в себя [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] операции между формами Windows и элементами управления.|Неприменимо.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>
## <a name="hosting-wpf-controls-in-windows-forms"></a>Размещение элементов управления WPF в Windows Forms  
 Следующие сценарии интероперации поддерживаются при [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управлении Windows Forms:  
  
- Вложение одного или нескольких элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью кода.  
  
- Связывание страницы свойств с одним или несколькими вложенными элементами управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Вложение одной или нескольких страниц [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в форму.  
  
- Запуск окна [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Хостинг мастер / деталь форме с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Windows Формы мастера и детали.  
  
- Хостинг мастер / деталь [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] форме с мастером и Windows Формы детали.  
  
- Вложение пользовательских элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Вложение гибридных элементов управления.  
  
### <a name="ambient-properties"></a>Внешние свойства  
 Некоторые из свойств окружающей среды [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления Windows Forms имеют эквиваленты. Эти окружающие свойства распространяются на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] размещенные элементы управления <xref:System.Windows.Forms.Integration.ElementHost> и размещаются в качестве общедоступных свойств на элементе управления. Элемент <xref:System.Windows.Forms.Integration.ElementHost> управления переводит каждое свойство [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] окружающего Windows в эквивалент.  
  
 Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Поведение  
 В приведенной ниже таблице описаны возможности взаимодействия.  
  
|Поведение|Поддерживается|Не поддерживается|  
|--------------|---------------|-------------------|  
|Прозрачность|Отрисовка элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает прозрачность. Фон родительского управления формами Windows может [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] стать фоном размещаемых элементов управления.|Неприменимо.|  
|Многопоточность|Поддерживаются все возможности многопоточности.|Как формы Windows, так и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] технологии предполагают однопоточной параллели. Во время отладки вызовы объектов платформы из других потоков будут вызывать исключение для принудительного выполнения этого требования.|  
|Безопасность|Все сценарии взаимодействия требуют полного доверия.|Не допускаются сценарии взаимодействия с частичным доверием.|  
|Возможности доступа|Поддерживаются все сценарии специальных возможностей. Вспомогательные технологические продукты функционируют правильно, когда они [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используются для гибридных приложений, которые содержат как формы Windows, так и элементы управления.|Неприменимо.|  
|Буфер обмена|Все операции с буфером обмена работают обычным образом. Это включает в себя резки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и вставки между формами Windows и элементов управления.|Неприменимо.|  
|Функция перетаскивания|Все операции перетаскивания работают обычным образом. Это включает в себя [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] операции между формами Windows и элементами управления.|Неприменимо.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md)
