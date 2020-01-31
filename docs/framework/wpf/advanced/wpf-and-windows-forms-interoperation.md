---
title: Взаимодействие WPF и Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 5141b84ecd002d920f0d4130bdc2529c0fce4994
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794057"
---
# <a name="wpf-and-windows-forms-interoperation"></a>Взаимодействие WPF и Windows Forms
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и Windows Forms представляют две разные архитектуры для создания интерфейсов приложений. Пространство имен <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> предоставляет классы, обеспечивающие общие сценарии взаимодействия. Двумя ключевыми классами, реализующими возможности взаимодействия, являются <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost>. В этом разделе описано, какие сценарии взаимодействия поддерживаются, а какие нет.  
  
> [!NOTE]
> Особое внимание уделено сценарию *гибридного элемента управления*. Гибридный элемент управления — это элемент управления на основе одной технологии, в который вложен элемент управления на основе другой технологии. Это также называется *вложенным взаимодействием*. В *многоуровневом гибридном элементе управления* более одного уровня вложения. Примером многоуровневой вложенной операции является элемент управления Windows Forms, содержащий элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], который содержит другой элемент управления Windows Forms. Многоуровневые гибридные элементы управления не поддерживаются.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## <a name="hosting-windows-forms-controls-in-wpf"></a>Размещение элементов управления Windows Forms в WPF  
 Следующие сценарии взаимодействия поддерживаются, когда элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] размещает элемент управления Windows Forms:  
  
- Элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может содержать один или несколько элементов управления Windows Forms с помощью XAML.  
  
- В нем может размещаться один или несколько элементов управления Windows Forms с помощью кода.  
  
- В нем могут размещаться Windows Forms контейнерные элементы управления, которые содержат другие элементы управления Windows Forms.  
  
- В нем может размещаться форма «основной/подробности» с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] главным и Windows Forms сведениями.  
  
- В нем может размещаться форма «основной/подробности» с Windows Forms главным и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сведениями.  
  
- В ней может размещаться один или несколько элементов управления ActiveX.  
  
- В него могут быть вложены один или несколько составных элементов управления.  
  
- С помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] в него могут быть вложены гибридные элементы управления.  
  
- С помощью кода в него могут быть вложены гибридные элементы управления.  
  
### <a name="layout-support"></a>Поддержка макета  
 В следующем списке описаны известные ограничения, когда элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> пытается интегрировать его размещенный элемент управления Windows Forms в систему разметки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- В некоторых случаях размеры элементов управления Windows Forms не могут изменяться или их размер можно изменять только до определенных размеров. Например, элемент управления Windows Forms <xref:System.Windows.Forms.ComboBox> поддерживает только одну высоту, которая определяется размером шрифта элемента управления. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] динамическом макете, в котором предполагается, что элементы могут растягиваться вертикально, размещаемый элемент управления <xref:System.Windows.Forms.ComboBox> не будет растягиваться должным образом.  
  
- Элементы управления Windows Forms нельзя поворачивать или расклонять. Например, при повороте пользовательского интерфейса на 90 градусов размещаемые элементы управления Windows Forms будут поддерживать свое вертикальное расположение.  
  
- В большинстве случаев Windows Forms элементы управления не поддерживают пропорциональное масштабирование. Несмотря на то, что общий размер элемента управления масштабируется, дочерние элементы управления и компоненты элемента управления могут изменять размеры не так, как ожидается. Это ограничение зависит от того, насколько хорошо каждый элемент управления Windows Forms поддерживает масштабирование.  
  
- В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно изменить z-порядок элементов для контроля поведения перекрывания. Размещенный элемент управления Windows Forms рисуется в отдельном HWND, поэтому он всегда отображается поверх [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов.  
  
- Windows Forms элементы управления поддерживают автомасштабирование на основе размера шрифта. В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] изменение размера шрифта не влечет за собой изменение размера всего макета, хотя отдельные элементы могут динамически изменять размер.  
  
### <a name="ambient-properties"></a>Внешние свойства  
 Некоторые свойства окружения элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют Windows Forms эквиваленты. Эти внешние свойства распространяются на размещенные элементы управления Windows Forms и предоставляются как общие свойства элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> преобразует каждое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] внешнее свойство в его Windows Forms эквивалент.  
  
 Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Поведение  
 В приведенной ниже таблице описаны возможности взаимодействия.  
  
|Поведение|Поддерживается|Не поддерживаются|  
|--------------|---------------|-------------------|  
|Прозрачность|Отрисовка Windows Forms элемента управления поддерживает прозрачность. Фон родительского элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может стать фоном размещенных Windows Forms элементов управления.|Некоторые элементы управления Windows Forms не поддерживают прозрачность. Например, элементы управления <xref:System.Windows.Forms.TextBox> и <xref:System.Windows.Forms.ComboBox> не будут прозрачными при размещении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|Переход по клавише TAB|Порядок табуляции для размещенных Windows Forms элементов управления аналогичен порядку, когда эти элементы управления размещаются в приложении на основе Windows Forms.<br /><br /> Переход от элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] к элементу управления Windows Forms с помощью клавиши TAB и клавиш SHIFT + TAB работает как обычно.<br /><br /> Windows Forms элементы управления со значением свойства <xref:System.Windows.Forms.Control.TabStop%2A> `false` не получают фокус при использовании вкладок пользователей через элементы управления.<br /><br /> — Каждый <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент управления имеет <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> значение, определяющее, когда этот элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> будет получать фокус.<br />— Windows Forms элементы управления, содержащиеся в контейнере <xref:System.Windows.Forms.Integration.WindowsFormsHost>, следуют порядку, указанному свойством <xref:System.Windows.Forms.Control.TabIndex%2A>. При переходе от последнего индекса табуляции фокус получает следующий элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], если таковой существует. Если других элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с фокусом не существует, переход к первому элементу управления Windows Forms в последовательности табуляции.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> значения элементов управления внутри <xref:System.Windows.Forms.Integration.WindowsFormsHost> относятся к родственным элементам управления Windows Forms, содержащимся в элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />— При переходе по табуляции учитывается модель поведения элемента управления. Например, если нажать клавишу TAB в элементе управления <xref:System.Windows.Forms.TextBox> с <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A>ным значением свойства `true`, вместо перемещения фокуса в текстовое поле будет введена вкладка.|Не применяется|  
|Переход с помощью клавиш со стрелками|— Навигация с помощью клавиш со стрелками в элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> аналогична обычной Windows Forms контейнерному элементу управления: стрелка вверх и клавиши со СТРЕЛКАми влево выбирают предыдущий элемент управления, а стрелка вниз и клавиша со стрелкой вправо — выбор следующего элемента управления.<br />— Клавиши Стрелка вверх и стрелка влево из первого элемента управления, содержащегося в элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>, выполняют те же действия, что и сочетания клавиш SHIFT + TAB. Если имеется элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с фокусом, фокус перемещается за пределы элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Это поведение отличается от стандартного <xref:System.Windows.Forms.ContainerControl>ного поведения в том, что переход к последнему элементу управления не выполняется. Если других элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с фокусом не существует, фокус возвращается к последнему элементу управления Windows Forms в последовательности табуляции.<br />— Стрелка вниз и клавиши со СТРЕЛКАми вправо от последнего элемента управления, содержащегося в элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>, выполняют то же действие, что и клавиша TAB. Если имеется элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с фокусом, фокус перемещается за пределы элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Это поведение отличается от стандартного <xref:System.Windows.Forms.ContainerControl>ного поведения в том, что переход к первому элементу управления не выполняется. Если других элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с фокусом не существует, фокус возвращается к первому элементу управления Windows Forms в последовательности табуляции.|Не применяется|  
|Клавиши быстрого доступа|Клавиши быстрого доступа работают как обычно, за исключением пунктов, оговоренных в столбце "Не поддерживается".|Повторяющиеся в различных технологиях клавиши быстрого доступа не работают как обычные повторяющиеся клавиши быстрого доступа. Когда сочетание клавиш дублируется между технологиями, по крайней мере один элемент управления Windows Forms и другой в элементе управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], элемент управления Windows Forms всегда получает ускоритель. Фокус не переключается между элементами управления с одинаковыми клавишами быстрого доступа.|  
|Сочетания клавиш|Сочетания клавиш работают как обычно, за исключением пунктов, оговоренных в столбце "Не поддерживается".|— Windows Forms сочетания клавиш, которые обрабатываются на этапе предварительной обработки, всегда имеют более высокий приоритет, чем [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сочетания клавиш. Например, если у вас есть элемент управления <xref:System.Windows.Forms.ToolStrip> с определенными сочетаниями клавиш CTRL + S и имеется команда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], привязанная к CTRL + S, то обработчик элемента управления <xref:System.Windows.Forms.ToolStrip> всегда вызывается первым, независимо от фокуса.<br />— Windows Forms сочетания клавиш, которые обрабатываются событием <xref:System.Windows.Forms.Control.KeyDown>, обрабатываются последними в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Это поведение можно предотвратить, переопределив метод <xref:System.Windows.Forms.Control.IsInputKey%2A> Windows Forms элемента управления или обрабатывая событие <xref:System.Windows.Forms.Control.PreviewKeyDown>. Возвращайте `true` из метода <xref:System.Windows.Forms.Control.IsInputKey%2A> или задайте для свойства <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> значение `true` в обработчике событий <xref:System.Windows.Forms.Control.PreviewKeyDown>.|  
|AcceptsReturn, AcceptsTab и другие специфические свойства элементов управления|Свойства, изменяющие поведение клавиатуры по умолчанию, работают обычным образом, предполагая, что Windows Forms элемент управления переопределяет метод <xref:System.Windows.Forms.Control.IsInputKey%2A>, возвращающий `true`.|Windows Forms элементы управления, изменяющие поведение клавиатуры по умолчанию, обрабатывая событие <xref:System.Windows.Forms.Control.KeyDown>, обрабатываются последними в ведущем элементе управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Так как эти элементы управления обрабатываются последними, они могут привести к непредвиденному поведению.|  
|События Enter и Leave|Если фокус не переходит на содержащий <xref:System.Windows.Forms.Integration.ElementHost> элемент управления, события Enter и Leave создаются обычным образом при изменении фокуса в одном элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.|События Enter и Leave не вызываются при следующих переводах фокуса:<br /><br /> — Из внутри в, за пределами элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />— С внешней стороны до внутри элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />— За пределами элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />— Из элемента управления Windows Forms, размещенного в элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>, в элемент управления <xref:System.Windows.Forms.Integration.ElementHost>, размещенный в том же <xref:System.Windows.Forms.Integration.WindowsFormsHost>.|  
|Многопоточность|Поддерживаются все возможности многопоточности.|Для технологий Windows Forms и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предполагается однопотоковая модель параллелизма. Во время отладки вызовы объектов платформы из других потоков будут вызывать исключение для принудительного выполнения этого требования.|  
|по безопасности|Все сценарии взаимодействия требуют полного доверия.|Не допускаются сценарии взаимодействия с частичным доверием.|  
|Специальные возможности|Поддерживаются все сценарии специальных возможностей. Продукты с поддержкой специальных возможностей правильно работают, если они используются для гибридных приложений, которые содержат как Windows Forms, так и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ные элементы управления.|Не применяется|  
|буфер обмена|Все операции с буфером обмена работают обычным образом. Сюда входит Вырезание и вставление между элементами управления Windows Forms и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Не применяется|  
|Функция перетаскивания|Все операции перетаскивания работают обычным образом. Сюда входят операции между Windows Formsми и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ными элементами управления.|Не применяется|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## <a name="hosting-wpf-controls-in-windows-forms"></a>Размещение элементов управления WPF в Windows Forms  
 Следующие сценарии взаимодействия поддерживаются, когда элемент управления Windows Forms размещает элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
- Вложение одного или нескольких элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью кода.  
  
- Связывание страницы свойств с одним или несколькими вложенными элементами управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Вложение одной или нескольких страниц [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в форму.  
  
- Запуск окна [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Размещение формы «основной/подробности» с Windows Forms главным и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сведениями.  
  
- Размещение формы «основной/подробности» с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] главным и Windows Forms сведениями.  
  
- Вложение пользовательских элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Вложение гибридных элементов управления.  
  
### <a name="ambient-properties"></a>Внешние свойства  
 Некоторые свойства окружения элементов управления Windows Forms имеют [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эквиваленты. Эти внешние свойства распространяются на размещенные элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и предоставляются как общие свойства элемента управления <xref:System.Windows.Forms.Integration.ElementHost>. <xref:System.Windows.Forms.Integration.ElementHost> элемент управления преобразует каждое Windows Forms внешнее свойство в его [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эквивалент.  
  
 Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Поведение  
 В приведенной ниже таблице описаны возможности взаимодействия.  
  
|Поведение|Поддерживается|Не поддерживаются|  
|--------------|---------------|-------------------|  
|Прозрачность|Отрисовка элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает прозрачность. Фон родительского элемента управления Windows Forms может стать фоном размещенных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления.|Не применяется|  
|Многопоточность|Поддерживаются все возможности многопоточности.|Для технологий Windows Forms и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предполагается однопотоковая модель параллелизма. Во время отладки вызовы объектов платформы из других потоков будут вызывать исключение для принудительного выполнения этого требования.|  
|по безопасности|Все сценарии взаимодействия требуют полного доверия.|Не допускаются сценарии взаимодействия с частичным доверием.|  
|Специальные возможности|Поддерживаются все сценарии специальных возможностей. Продукты с поддержкой специальных возможностей правильно работают, если они используются для гибридных приложений, которые содержат как Windows Forms, так и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ные элементы управления.|Не применяется|  
|буфер обмена|Все операции с буфером обмена работают обычным образом. Сюда входит Вырезание и вставление между элементами управления Windows Forms и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Не применяется|  
|Функция перетаскивания|Все операции перетаскивания работают обычным образом. Сюда входят операции между Windows Formsми и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ными элементами управления.|Не применяется|  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md)
