---
title: "Вопросы, связанные с макетом элемента WindowsFormsHost | Microsoft Docs"
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
  - "аппаратно-независимые пиксели"
  - "динамический макет [взаимодействие с WPF]"
  - "взаимодействие [WPF], Windows Forms"
  - "Windows Forms [WPF], взаимодействие с"
  - "Windows Forms, взаимодействие с WPF"
  - "WindowsFormsHost - вопросы, связанные с макетом элемента"
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Вопросы, связанные с макетом элемента WindowsFormsHost
В этом разделе описывается то, как элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> взаимодействует с системой макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] поддерживают разную, но похожую логику для изменения размера и размещения элементов на форме или странице.  При создании гибридного пользовательского интерфейса \(UI\), содержащего элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> объединяет две схемы макета.  
  
## Различия между макетами в WPF и Windows Forms  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует макет, не зависящий от разрешения.  Все измерения макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] задаются с помощью *аппаратно\-независимых пикселей*.  Аппаратно\-независимый пиксель — это пиксель размером в одну девяносто шестую дюйма, который не зависит от разрешения. Поэтому можно получить одинаковые результаты независимо от того, отображается ли результат на мониторе с разрешением 72 точки на дюйм или на принтере с разрешением 19 200 точек на дюйм.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также основана на *динамическом макете*.  Это означает, что элемент пользовательского интерфейса располагается на форме или странице в соответствии с его содержимым, его контейнером родительского макета и доступным размером экрана.  Динамический макет упрощает локализацию, автоматически изменяя размер и положение элементов пользовательского интерфейса при изменении длины строк в них.  
  
 Макет в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] является аппаратно зависимым и с большой вероятностью будет статичным.  Обычно элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] расположены точно на форме с использованием измерений, указанных в аппаратно\-зависимых пикселях.  Тем не менее, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] поддерживает некоторые возможности динамического макета. Некоторые из них представлены в следующей таблице.  
  
|Возможность|Описание|  
|-----------------|--------------|  
|Автоподбор размеров|Некоторые элементы [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] изменяют свой размер с целью верного отображения их содержимого.  Дополнительные сведения см. в разделе [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).|  
|Привязка и закрепление|Элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] поддерживают размещение и изменение размера, основанное на родительском контейнере.  Дополнительные сведения см. в разделах <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=fullName> и <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=fullName>.|  
|Автоматическое масштабирование|Контейнерные элементы управления изменяют свой размер и размер своих потомков в зависимости от разрешения устройства вывода или размера контейнерного шрифта по умолчанию \(в пикселях\).  Дополнительные сведения см. в разделе [Автоматическое масштабирование в Windows Forms](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md).|  
|Контейнеры макета|Элементы управления <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel> упорядочивают свои дочерние элементы управления и изменяют их размер самостоятельно, в зависимости от их содержимого.|  
  
## Ограничения макета  
 В общем случае, элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не могут быть масштабированы и преобразованы в возможный размер в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  В следующем списке перечислены известные ограничения при попытке элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> интегрировать его вложенный элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в систему макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   В некоторых случаях размеры элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] изменять нельзя или же их можно изменять, но только в фиксированных пределах.  Например, элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> поддерживает только одну высоту, которая определяется размером шрифта элемента управления.  В динамическом макете [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в котором элементы можно растянуть по вертикали, вложенный элемент управления <xref:System.Windows.Forms.ComboBox> не растягивается, как ожидалось бы.  
  
-   Элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] нельзя поворачивать или наклонять.  Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> вызывает событие <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> при применении преобразования наклона или поворота.  Если не обработать событие <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>, возникает <xref:System.InvalidOperationException>.  
  
-   В большинстве случаев элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не поддерживают пропорциональное масштабирование.  Не смотря на то, что общий размер элемента управления масштабируется, дочерние элементы управления и компоненты элемента управления могут изменять размеры не так, как ожидалось.  Это ограничение зависит от поддержки масштабирования каждым элементом управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Кроме этого, нельзя масштабировать элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] до размера 0 пикселей.  
  
-   Элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] поддерживают автоматическое масштабирование, при котором форма будет автоматически изменять свой размер и размер своих элементов управления в зависимости от размера шрифта.  В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] изменение размера шрифта не влечет за собой изменение размера всего макета, хотя отдельные элементы могут динамически изменять размер.  
  
### z\-порядок  
 В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно изменить z\-порядок элементов для контроля поведения перекрывания.  Вложенный элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] рисуется в отдельном HWND, причем он всегда рисуется поверх элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Вложенный элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] также отображается поверх любых элементов <xref:System.Windows.Documents.Adorner>.  
  
## Поведение макета  
 В следующих разделах описываются определенные аспекты поведения макета при размещении элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Масштабирование, пересчет единиц измерения и независимость от оборудования  
 Всякий раз, когда элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> выполняет операции, связанные с измерениями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], в этом участвуют две системы координат: аппаратно\-независимые пиксели для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и аппаратно\-зависимые пиксели для [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Поэтому для получения единообразного макета необходимо применить соответствующий пересчет единиц измерения и преобразования масштабирования.  
  
 Преобразование между системами координат зависит от текущего разрешения устройства и любого макета или преобразований отрисовки, примененных к элементу <xref:System.Windows.Forms.Integration.WindowsFormsHost> или к его родительским элементам.  
  
 Если устройство вывода имеет разрешение 96 пикселей на дюйм и к элементу <xref:System.Windows.Forms.Integration.WindowsFormsHost> не было применено масштабирование, то один аппаратно\-независимый пиксель равен одному аппаратно\-зависимому пикселю.  
  
 Во всех остальных случаях требуется масштабирование системы координат.  Размеры размещаемого элемента управления не изменяются.  Вместо этого, элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> пытается масштабировать размещаемый элемент управления и все его дочерние элементы управления.  Поскольку [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не полностью поддерживает масштабирование, элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> масштабируется до степени, поддерживаемой определенными элементами управления.  
  
 Переопределите метод <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> для предоставления пользовательского поведения масштабирования для размещаемого элемента управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  
  
 В дополнение к масштабированию, элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> обрабатывает случаи округления и переполнения как описано в следующей таблице.  
  
|Проблема преобразования|Описание|  
|-----------------------------|--------------|  
|Округление|Измерения аппаратно\-независимых пикселей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] задаются как `double`, а измерения аппаратно\-зависимых пикселей [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] задаются как `int`.  Когда измерения, основанные на `double`, преобразуются в измерения, основанные на `int`, элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> использует стандартное округление, поэтому дробные значения меньше 0,5 округляются до 0.|  
|Переполнение|При преобразовании элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> из значений `double` в значения `int` возможно переполнение.  Значения, превосходящие <xref:System.Int32.MaxValue>, устанавливаются равными <xref:System.Int32.MaxValue>.|  
  
### Свойства, связанные с макетом  
 Свойства, управляющие поведением макета в элементах управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и элементах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], сопоставляются соответствующим образом с элементом <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
### Изменения макета в размещаемом элементе управления  
 Изменения макета в размещаемом элементе управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] передаются [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для запуска обновлений макета.  Метод <xref:System.Windows.UIElement.InvalidateMeasure%2A> в <xref:System.Windows.Forms.Integration.WindowsFormsHost> обеспечивает то, что изменения макета в размещенном элементе управления вызывают запуск обработчика макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Постоянно изменяемые в размерах элементы управления Windows Forms  
 Элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], которые поддерживают непрерывное масштабирование, полностью взаимодействуют с системой макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> использует методы <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> в качестве обычных методов изменения размера и расположения размещенного элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
### Алгоритм изменения размера  
 Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> использует следующую процедуру для изменения размера размещенного элемента управления:  
  
1.  Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> переопределяет методы <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.  
  
2.  Для определения размера размещенного элемента управления метод <xref:System.Windows.FrameworkElement.MeasureOverride%2A> вызывает метод <xref:System.Windows.Forms.Control.GetPreferredSize%2A> размещенного элемента управления с ограничением, полученным от ограничения, переданного методу <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  
  
3.  Метод <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> пытается установить размещенный элемент управления в соответствии с ограничением заданного размера.  
  
4.  Если свойство размещенного элемента управления <xref:System.Windows.Forms.Control.Size%2A> соответствует указанным ограничениям, размеры размещаемого элемента управления изменяются в соответствии с ограничениями.  
  
 Если свойство <xref:System.Windows.Forms.Control.Size%2A> не соответствует указанным ограничениям, размещаемый элемент управления не поддерживает постоянное изменение размера.  Например, элемент управления <xref:System.Windows.Forms.MonthCalendar> допускает только дискретные размеры.  Разрешенные размеры для данного элемента управления состоят из целых чисел \(представляющие номер месяца\) для высоты и ширины.  В подобных случаях элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> ведет себя следующим образом:  
  
-   Если свойство <xref:System.Windows.Forms.Control.Size%2A> возвращает больший размер, чем указанное ограничение, элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> выравнивает размещенный элемент управления в соответствии с ограничением.  Высота и ширина обрабатываются отдельно, поэтому размещаемый элемент управления может быть ограничен в любом направлении.  
  
-   Если свойство <xref:System.Windows.Forms.Control.Size%2A> возвращает меньший размер, чем указанное ограничение, <xref:System.Windows.Forms.Integration.WindowsFormsHost> принимает это значение размера и возвращает значение в систему макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-arranging-windows-forms-controls-in-wpf.md)   
 [Упорядочение элементов управления Windows Forms в приложении WPF](http://go.microsoft.com/fwlink/?LinkID=159971)   
 [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)