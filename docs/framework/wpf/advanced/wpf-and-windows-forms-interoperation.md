---
title: "Взаимодействие WPF и Windows Forms | Microsoft Docs"
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
  - "гибридные элементы управления [взаимодействие с WPF]"
  - "взаимодействие [WPF], Windows Forms"
  - "вложенное взаимодействие [WPF]"
  - "Windows Forms [WPF], взаимодействие с"
  - "Windows Forms, взаимодействие с WPF"
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Взаимодействие WPF и Windows Forms
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] представляют собой две различные архитектуры для создания интерфейсов приложений.  Пространство имен <xref:System.Windows.Forms.Integration?displayProperty=fullName> предоставляет классы, обеспечивающие общие сценарии взаимодействия.  Ключевыми классами, реализующими возможности взаимодействия, являются <xref:System.Windows.Forms.Integration.WindowsFormsHost> и <xref:System.Windows.Forms.Integration.ElementHost>.  В этом разделе описано, какие сценарии взаимодействия поддерживаются, а какие нет.  
  
> [!NOTE]
>  Особое внимание уделено скрипту *гибридного элемента управления*.  Гибридный элемент управления состоит из элемента управления одной технологии и вложенного в него элемента управления другой технологии.  Это также называется *вложенное взаимодействие*.  В *многоуровневом гибридном элементе управления* более одного уровня вложения.  Примером многоуровневого вложенного взаимодействия является элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], который содержит элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], содержащий другой элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Многоуровневые гибридные элементы управления не поддерживаются.  
  
   
  
<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## Размещение элементов управления Windows Forms в WPF  
 Если в элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вложен элемент управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)], поддерживаются следующие сценарии взаимодействия.  
  
-   В элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью XAML могут быть вложены один или несколько элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   С помощью кода в него могут быть вложены один или несколько элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   В него могут быть вложены контейнерные элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], содержащие элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   В него может быть вложена форма с отношением "главный\-подчиненный" с главным [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и подчиненными [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   В него может быть вложена форма с отношением "главный\-подчиненный" с главным [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и подчиненными [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   В него могут быть вложены один или несколько элементов управления [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)].  
  
-   В него могут быть вложены один или несколько составных элементов управления.  
  
-   С помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] в него могут быть вложены гибридные элементы управления.  
  
-   С помощью кода в него могут быть вложены гибридные элементы управления.  
  
### Поддержка макета  
 В следующем списке перечислены известные ограничения при попытке элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> интегрировать его вложенный элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в систему макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   В некоторых случаях размеры элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] изменять нельзя или же их можно изменять, но только в фиксированных пределах.  Например, элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> поддерживает только одну высоту, которая определяется размером шрифта элемента управления.  В динамическом макете [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в котором предполагается, что элементы можно растянуть по вертикали, вложенный элемент управления <xref:System.Windows.Forms.ComboBox> не растягивается, как ожидалось.  
  
-   Элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] нельзя поворачивать или наклонять.  Например, при повороте пользовательского интерфейса на 90 градусов вложенные элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сохранят свое вертикальное положение.  
  
-   В большинстве случаев элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не поддерживают пропорциональное масштабирование.  Не смотря на то, что общий размер элемента управления масштабируется, дочерние элементы управления и компоненты элемента управления могут изменять размеры не так, как ожидалось.  Это ограничение зависит от поддержки масштабирования каждым элементом управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно изменить z\-порядок элементов для контроля поведения перекрывания.  Вложенный элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] рисуется в отдельном HWND, причем он всегда рисуется поверх элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] поддерживают автоматическое масштабирование в соответствии с размером шрифта.  В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] изменение размера шрифта не влечет за собой изменение размера всего макета, хотя отдельные элементы могут динамически изменять размер.  
  
### Свойства окружения  
 Некоторые свойства окружения элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют эквиваленты [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Эти свойства окружения распространяются на вложенные элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и предоставляются как общие свойства элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> переводит каждое свойство окружения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в его эквивалент[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
### Поведение  
 В следующей таблице описаны возможности взаимодействия.  
  
|Поведение|Поддерживается|Не поддерживаются|  
|---------------|--------------------|-----------------------|  
|Прозрачность|Отрисовка элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] поддерживает прозрачность.  Фон родительского элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может стать фоном вложенного элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].|Некоторые элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не поддерживает прозрачность.  Например, элементы управления <xref:System.Windows.Forms.TextBox> и <xref:System.Windows.Forms.ComboBox> не будут прозрачными при вложении в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|Переход по клавише табуляции|Последовательность перехода для вложенных элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] та же, что и при вложении этих элементов управления в приложение, основанное на [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].<br /><br /> Переход от элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] к элементу управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] по клавишам TAB и SHIFT \+ TAB работает как обычно.<br /><br /> Элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], имеющих значение `false` свойства <xref:System.Windows.Forms.Control.TabStop%2A>, не получают фокус, когда пользователь переключается между элементами управления.<br /><br /> -   Каждый элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> имеет значение <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>, которое определяет, когда данный элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> получит фокус.<br />-   Элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], содержащиеся внутри контейнера <xref:System.Windows.Forms.Integration.WindowsFormsHost>, также следует порядку, заданному свойством <xref:System.Windows.Forms.Control.TabIndex%2A>.  При переходе от последнего индекса табуляции фокус получает следующий элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], если таковой существует.  Если нет других элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], принимающих фокус, то переход по табуляции устанавливает фокус на первый элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в последовательности перехода по табуляции.<br />-   Значения <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> для элементов управления в <xref:System.Windows.Forms.Integration.WindowsFormsHost> устанавливаются по отношению к родственным элементам управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], содержащимся в элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-   Переход по табуляции осуществляется и по специальным моделям поведения элементов управления.  Например, нажатие клавиши TAB в элементе управления <xref:System.Windows.Forms.TextBox> со значением `true` свойства <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> вместо перемещения фокуса активирует текстовое поле.|Неприменимо.|  
|Переход по клавишам со стрелками|-   Переход по клавишам со стрелками в элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> такой же, как и в обычном контейнерном элементе управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Клавиши со стрелками ВВЕРХ и ВЛЕВО выбирают предыдущий элемент управления, клавиши со стрелками ВНИЗ и ВПРАВО выбирают следующий элемент управления.<br />-   Для первого элемента управления, содержащегося в элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>, клавиши со стрелками ВВЕРХ и ВЛЕВО выполняют те же действия, что и сочетание клавиш SHIFT \+ TAB.  Если имеется принимающий фокус элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], то фокус перемещается за пределы элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Такое поведение отличается от стандартного поведения <xref:System.Windows.Forms.ContainerControl> тем, что не происходит перехода к последнему элементу управления.  Если нет других элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], принимающих фокус, фокус возвращается к последнему элементу управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в последовательности табуляции.<br />-   Для последнего элемента управления, содержащегося в элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>, клавиши со стрелками ВНИЗ и ВПРАВО выполняют же действие, что и клавиша TAB.  Если имеется принимающий фокус элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], то фокус перемещается за пределы элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Такое поведение отличается от стандартного поведения <xref:System.Windows.Forms.ContainerControl> тем, что не происходит перехода к первому элементу управления.  Если нет других элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], принимающих фокус, то фокус возвращается к первому элементу управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в последовательности перехода.|Неприменимо.|  
|Клавиши быстрого доступа|Клавиши быстрого доступа работают как обычно, за исключением пунктов, оговоренных в столбце "Не поддерживается".|Повторяющиеся в различных технологиях клавиши быстрого доступа не работают как обычные повторяющиеся клавиши быстрого доступа.  При повторении клавиш быстрого доступа в различных технологиях по крайней мере одним элементом управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и одним элементом управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], клавиша быстрого доступа всегда присваивается элементу управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Фокус не переключается между элементами управления с одинаковыми клавишами быстрого доступа.|  
|Сочетание клавиш|Горячие клавиши работают как обычно, за исключением пунктов, оговоренных в столбце "Не поддерживается".|-   Горячие клавиши [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], заданные на этапе предварительной обработки, всегда имеют приоритет перед горячими клавишами [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Например, если имеется элемент управления <xref:System.Windows.Forms.ToolStrip> с горячими клавишами CTRL\+S и есть команда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], привязанная к CTRL\+S, первым всегда вызывается обработчик элементов управления <xref:System.Windows.Forms.ToolStrip>, независимо от фокуса.<br />-   Горячие клавиши [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], обрабатываемые событием <xref:System.Windows.Forms.Control.KeyDown>, в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обрабатываются последними.  Можно предотвратить такое поведение путем переопределения метода <xref:System.Windows.Forms.Control.IsInputKey%2A> элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] или путем обработки события <xref:System.Windows.Forms.Control.PreviewKeyDown>.  Возвращайте значение `true` в методе <xref:System.Windows.Forms.Control.IsInputKey%2A>, или задайте свойству <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=fullName> значение `true` в вашем обработчике событий <xref:System.Windows.Forms.Control.PreviewKeyDown>.|  
|AcceptsReturn AcceptsTab и другие специфические свойства элементов управления|Свойства, изменяющие стандартное поведение клавиатуры обычным образом, причем предполагается, что элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] переопределяет метод <xref:System.Windows.Forms.Control.IsInputKey%2A> так, чтобы он возвращал `true`.|Элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], изменяющие стандартное поведение клавиатуры при обработке событий <xref:System.Windows.Forms.Control.KeyDown>, обрабатываются во вложенном элементе управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] последними.  Поскольку эти элементы управления обрабатываются последними, они могут привести к непредвиденному поведению.|  
|События Enter и Leave|Если фокус не устанавливается на элемент управления, содержащий <xref:System.Windows.Forms.Integration.ElementHost>, при смене фокуса в одном элементе управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> обычно вызываются события Enter и Leave.|События Enter и Leave не вызываются при следующем изменении фокуса:<br /><br /> -   Изнутри элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> наружу.<br />-   Снаружи элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> внутрь.<br />-   За пределами элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-   Из элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], вложенного в элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> на элемент управления <xref:System.Windows.Forms.Integration.ElementHost>, вложенный в тот же <xref:System.Windows.Forms.Integration.WindowsFormsHost>.|  
|Многопоточность|Поддерживаются все возможности многопоточности.|И технология [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], и технология [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предполагают однопоточную модель одновременного выполнения.  Во время отладки вызовы объектов структуры из других потоков будут вызывать исключение для принудительного выполнения этого требования.|  
|Безопасность|Все сценарии взаимодействия требуют полного доверия.|Не допускаются сценарии взаимодействия с частичным доверием.|  
|Специальные возможности|Поддерживаются все сценарии специальных возможностей.  Продукты вспомогательной технологии работают корректно, когда они используются для гибридных приложений, содержащих как элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], так и элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Неприменимо.|  
|Буфер обмена|Все операции буфера обмена работают обычным образом.  Сюда входят вырезания и вставки между элементами управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Неприменимо.|  
|Функция перетаскивания|Все операции перетаскивания работают обычным образом.  Сюда входят операции между элементами управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Неприменимо.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## Размещение элементов управления WPF в Windows Forms  
 Если в элемент управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] вложен элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], поддерживаются следующие сценарии взаимодействия.  
  
-   Вложение одного или нескольких элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью кода.  
  
-   Связывание вкладки свойств с одним или несколькими вложенными элементами управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Вложение одной или нескольких страниц [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в форму.  
  
-   Запуск окна [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Вложение формы с отношением "главный\-подчиненный" с главным [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и подчиненными [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Вложение формы с отношением "главный\-подчиненный" с главным [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и подчиненными [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   Вложение пользовательских элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Вложение гибридных элементов управления.  
  
### Свойства окружения  
 Некоторые свойства окружения элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] имеют эквиваленты [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Эти свойства окружения распространяются на вложенные элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и предоставляются как общие свойства элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.  Элемент управления <xref:System.Windows.Forms.Integration.ElementHost> переводит каждое свойство окружения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в его эквивалент[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
### Поведение  
 В следующей таблице описаны возможности взаимодействия.  
  
|Поведение|Поддерживается|Не поддерживаются|  
|---------------|--------------------|-----------------------|  
|Прозрачность|Отрисовка элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает прозрачность.  Фон родительского элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] может стать фоном вложенного элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Неприменимо.|  
|Многопоточность|Поддерживаются все возможности многопоточности.|И технология [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], и технология [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предполагают однопоточную модель одновременного выполнения.  Во время отладки вызовы объектов структуры из других потоков будут вызывать исключение для принудительного выполнения этого требования.|  
|Безопасность|Все сценарии взаимодействия требуют полного доверия.|Не допускаются сценарии взаимодействия с частичным доверием.|  
|Специальные возможности|Поддерживаются все сценарии специальных возможностей.  Продукты вспомогательной технологии работают корректно, когда они используются для гибридных приложений, содержащих как элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], так и элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Неприменимо.|  
|Буфер обмена|Все операции буфера обмена работают обычным образом.  Сюда входят вырезания и вставки между элементами управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Неприменимо.|  
|Функция перетаскивания|Все операции перетаскивания работают обычным образом.  Сюда входят операции между элементами управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Неприменимо.|  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)