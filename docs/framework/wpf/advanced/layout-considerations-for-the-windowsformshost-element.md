---
title: Вопросы, связанные с макетом элемента WindowsFormsHost
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element layout considerations [WPF]
- dynamic layout [WPF interoperability]
- device-independent pixels
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
ms.openlocfilehash: 9f97639447284b792d52cf4aa25b81f584d7291a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787908"
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>Вопросы, связанные с макетом элемента WindowsFormsHost
В этом разделе описано, как элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> взаимодействует с системой разметки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и Windows Forms поддерживают разную, но похожую логику для определения размеров и позиционирования элементов на форме или странице. При создании гибридного пользовательского интерфейса, размещающего элементы управления Windows Forms в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> интегрирует две схемы макета.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>Различия в макете между WPF и Windows Forms  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует макет, не зависящий от разрешения. Все измерения макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] задаются с помощью *аппаратно-независимых пикселей*. Аппаратно-независимый пиксель — это один девяносто-шестой дюйма в размере и не зависит от разрешения, поэтому вы получаете аналогичные результаты независимо от того, выполняется ли визуализация на мониторе с 72 dpi или на принтере 19 200-dpi.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также основано на *динамическом макете*. Это означает, что элемент пользовательского интерфейса упорядочивает себя на форме или странице в соответствии с его содержимым, родительским контейнером макета и доступным размером экрана. Динамический макет упрощает локализацию, автоматически настраивая размер и положение элементов пользовательского интерфейса, когда строки, которые они содержат, изменили длину.  
  
 Макет в Windows Forms зависит от устройства и, скорее всего, является статическим. Как правило, Windows Forms элементы управления располагаются абсолютно на форме с использованием измерений, заданных в аппаратных пикселях. Однако Windows Forms поддерживает некоторые функции динамического макета, как показано в следующей таблице.  
  
|Функция макета|Описание|  
|--------------------|-----------------|  
|Автоматическое изменение размера|Некоторые Windows Forms элементы управления изменяют размер, чтобы правильно отображать их содержимое. Дополнительные сведения см. в разделе [Общие сведения о свойстве AutoSize](../../winforms/controls/autosize-property-overview.md).|  
|Привязка и закрепление|Элементы управления Windows Forms поддерживают размещение и изменение размера на основе родительского контейнера. Дополнительные сведения см. в разделах <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.|  
|Автомасштабирования|Размеры элементов управления контейнера и их дочерние элементы изменяются в зависимости от разрешения выходного устройства или размера (в пикселях) шрифта контейнера по умолчанию. Дополнительные сведения см. [в разделе Автоматическое масштабирование в Windows Forms](../../winforms/automatic-scaling-in-windows-forms.md).|  
|Контейнеры макета|Элементы управления <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel> упорядочивают свои дочерние элементы управления и сами имеют свой размер в соответствии с их содержимым.|  
  
## <a name="layout-limitations"></a>Ограничения макета  
 В общем случае Windows Forms элементы управления не могут масштабироваться и преобразовываться в экстенты, доступные в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. В следующем списке описаны известные ограничения, когда элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> пытается интегрировать его размещенный элемент управления Windows Forms в систему разметки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- В некоторых случаях размеры элементов управления Windows Forms не могут изменяться или их размер можно изменять только до определенных размеров. Например, элемент управления Windows Forms <xref:System.Windows.Forms.ComboBox> поддерживает только одну высоту, которая определяется размером шрифта элемента управления. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] динамическом макете, в котором элементы могут растягиваться вертикально, размещаемый элемент управления <xref:System.Windows.Forms.ComboBox> не будет растягиваться должным образом.  
  
- Элементы управления Windows Forms нельзя поворачивать или расклонять. Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> вызывает событие <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>, если применяется преобразование «наклон» или «вращение». Если событие <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> не обрабатывается, возникает <xref:System.InvalidOperationException>.  
  
- В большинстве случаев Windows Forms элементы управления не поддерживают пропорциональное масштабирование. Несмотря на то, что общий размер элемента управления масштабируется, дочерние элементы управления и компоненты элемента управления могут изменять размеры не так, как ожидается. Это ограничение зависит от того, насколько хорошо каждый элемент управления Windows Forms поддерживает масштабирование. Кроме того, нельзя масштабировать элементы управления Windows Forms вниз до размера 0 пикселей.  
  
- Windows Forms элементы управления поддерживают Автомасштабирование, при котором форма автоматически изменяет размер и элементы управления в зависимости от размера шрифта. В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] изменение размера шрифта не влечет за собой изменение размера всего макета, хотя отдельные элементы могут динамически изменять размер.  
  
### <a name="z-order"></a>Z-порядок  
 В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно изменить z-порядок элементов для контроля поведения перекрывания. Размещенный элемент управления Windows Forms рисуется в отдельном HWND, поэтому он всегда отображается поверх [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов.  
  
 Размещенный элемент управления Windows Forms также рисуется поверх любого <xref:System.Windows.Documents.Adorner> элементов.  
  
## <a name="layout-behavior"></a>Поведение макета  
 В следующих разделах описываются конкретные аспекты поведения макета при размещении элементов управления Windows Forms в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>Масштабирование, преобразование единиц и независимость устройств  
 Каждый раз, когда элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> выполняет операции с измерениями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и Windows Forms, участвуют две системы координат: аппаратно-независимые пиксели для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и аппаратных пикселей для Windows Forms. Поэтому необходимо применить соответствующие преобразования единиц и масштабирования для достижения согласованного макета.  
  
 Преобразование между системами координат зависит от текущего разрешения устройства и любых преобразований макета или отрисовки, примененных к элементу <xref:System.Windows.Forms.Integration.WindowsFormsHost> или его предкам.  
  
 Если выходное устройство равно 96 dpi и к элементу <xref:System.Windows.Forms.Integration.WindowsFormsHost> не применено масштабирование, то один аппаратно-зависимый пиксель равен одному пикселю оборудования.  
  
 Во всех остальных случаях требуется масштабирование системы координат. Размер размещенного элемента управления не изменяется. Вместо этого элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> пытается масштабировать размещаемый элемент управления и все его дочерние элементы управления. Поскольку Windows Forms не полностью поддерживает масштабирование, элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> масштабируется до степени, поддерживаемой определенными элементами управления.  
  
 Переопределите метод <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A>, чтобы обеспечить пользовательское поведение масштабирования для размещаемого элемента управления Windows Forms.  
  
 Помимо масштабирования, элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> обрабатывает варианты округления и переполнения, как описано в следующей таблице.  
  
|Проблемы с преобразованием|Описание|  
|----------------------|-----------------|  
|округление;|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] измерения, независимые от устройства, задаются как `double`, а Windows Forms измерения пикселей оборудования задаются как `int`. В случаях, когда измерения на основе `double`преобразуются в измерения на основе `int`, элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> использует стандартное округление, чтобы дробные значения меньше 0,5 округлялись вниз до 0.|  
|Переполнение|Когда элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> преобразует из `double` значений в значения `int`, возможно переполнение. Значения, превышающие <xref:System.Int32.MaxValue>, задаются равными <xref:System.Int32.MaxValue>.|  
  
### <a name="layout-related-properties"></a>Свойства, связанные с макетом  
 Свойства, управляющие поведением макета в элементах управления Windows Forms и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], соответствующим образом сопоставляются элементу <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="layout-changes-in-the-hosted-control"></a>Изменения макета в размещенном элементе управления  
 Изменения макета в размещенном элементе управления Windows Forms распространяются на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для активации обновлений макета. Метод <xref:System.Windows.UIElement.InvalidateMeasure%2A> на <xref:System.Windows.Forms.Integration.WindowsFormsHost> гарантирует, что изменения макета в размещенном элементе управления приведут к запуску обработчика разметки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="continuously-sized-windows-forms-controls"></a>Постоянно изменяемые элементы управления Windows Forms  
 Windows Forms элементы управления, поддерживающие непрерывное масштабирование, полностью взаимодействуют с системой разметки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> использует методы <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> как обычно для изменения размера и упорядочивания размещаемого элемента управления Windows Forms.  
  
### <a name="sizing-algorithm"></a>Алгоритм изменения размера  
 Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> использует следующую процедуру для изменения размера размещенного элемента управления:  
  
1. Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> переопределяет методы <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.  
  
2. Чтобы определить размер размещаемого элемента управления, метод <xref:System.Windows.FrameworkElement.MeasureOverride%2A> вызывает метод <xref:System.Windows.Forms.Control.GetPreferredSize%2A> размещенного элемента управления с ограничением, переведенным из ограничения, переданного в метод <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  
  
3. Метод <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> пытается задать для размещенного элемента управления указанное ограничение размера.  
  
4. Если свойство <xref:System.Windows.Forms.Control.Size%2A> размещенного элемента управления соответствует указанному ограничению, размер размещаемого элемента управления определяется ограничением.  
  
 Если свойство <xref:System.Windows.Forms.Control.Size%2A> не соответствует указанному ограничению, размещенный элемент управления не поддерживает непрерывное изменение размера. Например, элемент управления <xref:System.Windows.Forms.MonthCalendar> допускает только дискретные размеры. Допустимые размеры для этого элемента управления состоят из целых чисел (представляющих число месяцев) как для высоты, так и для ширины. В таких случаях элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> ведет себя следующим образом:  
  
- Если свойство <xref:System.Windows.Forms.Control.Size%2A> возвращает больший размер, чем указанное ограничение, элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> обрезает размещаемый элемент управления. Высота и ширина обрабатываются отдельно, поэтому размещаемый элемент управления может быть обрезан в любом направлении.  
  
- Если свойство <xref:System.Windows.Forms.Control.Size%2A> возвращает меньший размер, чем указанное ограничение, <xref:System.Windows.Forms.Integration.WindowsFormsHost> принимает это значение размера и возвращает значение в систему макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF](walkthrough-arranging-windows-forms-controls-in-wpf.md)
- [Пример упорядочивания элементов управления Windows Forms в WPF](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Сопоставление свойств Windows Forms и WPF](windows-forms-and-wpf-property-mapping.md)
- [Миграция и взаимодействие систем](migration-and-interoperability.md)
