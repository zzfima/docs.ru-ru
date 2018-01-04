---
title: "Вопросы, связанные с макетом элемента WindowsFormsHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element layout considerations [WPF]
- dynamic layout [WPF interoperability]
- device-independent pixels
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 895185797ebdef2145caec4c1c5ac26e3688c463
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>Вопросы, связанные с макетом элемента WindowsFormsHost
В этом разделе описывается как <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент взаимодействует с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] система макета.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] поддерживают разные, но похожую логику для изменения размера и размещения элементов на форму или страницу. При создании гибридного пользовательского интерфейса (UI), на котором размещена [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент объединяет две схемы макета.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>Различия в макет WPF и Windows Forms  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]используя макет зависящая от разрешения. Все [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] измерения макета задаются с помощью *аппаратно независимых пикселях*. Аппаратно независимый пиксель — одну девяносто шестую дюйма размера и разрешения, чтобы получить аналогичные результаты независимо от того, вы отрисовывают монитор 72 dpi или на принтер 19200 dpi.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также основана на *динамический макет*. Это означает, что элемент пользовательского интерфейса располагается на формы или страницы в соответствии с его содержимым, родительского контейнера макета и доступным размером экрана. Динамический макет упрощает локализацию, автоматически изменяя размер и положение элементов пользовательского интерфейса, когда строки, содержащиеся в них изменения длины.  
  
 Макет в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] зависящие от устройства, и скорее всего, будут статическими. Как правило [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления расположены точно на форме с использованием измерений, указанных в пикселях оборудования. Тем не менее [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] поддерживает некоторые возможности динамического макета, показанных в следующей таблице.  
  
|Функция разметки|Описание:|  
|--------------------|-----------------|  
|Автоматическое изменение размера|Некоторые [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] размера элементов управления, целью верного отображения их содержимого. Дополнительные сведения см. в разделе [Общие](../../../../docs/framework/winforms/controls/autosize-property-overview.md).|  
|Привязка и закрепление|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]элементы управления поддерживают размещение и изменение размера, основанное на родительском контейнере. Дополнительные сведения см. в разделах <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.|  
|Автоматическое масштабирование|Контейнерные элементы управления изменение размера себя и своих дочерних элементов, на основе разрешения устройства вывода или размер в пикселях шрифт контейнера по умолчанию. Дополнительные сведения см. в разделе [автоматическое масштабирование в Windows Forms](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md).|  
|Контейнеры макета|<xref:System.Windows.Forms.FlowLayoutPanel> И <xref:System.Windows.Forms.TableLayoutPanel> элементы управления упорядочить их дочерние элементы управления и размер самостоятельно, в зависимости от их содержимого.|  
  
## <a name="layout-limitations"></a>Ограничения для макета  
 Как правило [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления нельзя масштабировать и преобразованы в возможный размер в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Ниже перечислены известные ограничения при <xref:System.Windows.Forms.Integration.WindowsFormsHost> пытается интегрировать его вложенный элемент [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] система макета.  
  
-   В некоторых случаях размеры элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] изменять нельзя, или же их можно изменять, но только в фиксированных пределах. Например [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> элемент управления поддерживает только одну высоту, которая определяется размером шрифта элемента управления. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] динамический макет, где элементы можно растянуть по вертикали, вложенный <xref:System.Windows.Forms.ComboBox> управления не растягивается, как ожидалось.  
  
-   Элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] нельзя поворачивать или наклонять. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Вызывает элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> событий при применении преобразования наклона или поворота. Если не обработать <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> событий, <xref:System.InvalidOperationException> возникает.  
  
-   В большинстве случаев элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не поддерживают пропорциональное масштабирование. Несмотря на то, что общий размер элемента управления масштабируется, дочерние элементы управления и компоненты элемента управления могут изменять размеры не так, как ожидается. Это ограничение зависит от поддержки масштабирования каждым элементом управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Кроме того, нельзя масштабировать [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления до размера 0 пикселей.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]элементы управления поддерживают автоматическое масштабирование, в котором формы будут автоматически изменены и его элементы управления, в зависимости от размера шрифта. В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] изменение размера шрифта не влечет за собой изменение размера всего макета, хотя отдельные элементы могут динамически изменять размер.  
  
### <a name="z-order"></a>Z-порядок  
 В пользовательском интерфейсе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно изменить z-порядок элементов для контроля поведения перекрывания. Вложенный элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] рисуется в отдельном HWND, причем он всегда рисуется поверх элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Вложенный [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления также отображается поверх любых <xref:System.Windows.Documents.Adorner> элементов.  
  
## <a name="layout-behavior"></a>Поведение макета  
 В следующих разделах описаны определенные аспекты поведения макета при размещении [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>Масштабирование, преобразованием единиц измерения и независимость от оборудования  
 Каждый раз, когда <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент выполняет операции, связанные с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] участвующих измерения две системы координат: аппаратно независимых пикселях для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и пикселей оборудования для [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Таким образом необходимо установить правильную модульных и преобразования масштабирования, чтобы добиться согласованного макета.  
  
 Преобразование между системами координат зависит от текущего разрешения устройства и любого макета или преобразований отрисовки, примененных к <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент или его предки.  
  
 Если устройство вывода 96 dpi, без масштабирования, примененных к <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент, один аппаратно независимый пиксель равен одному пикселю оборудования.  
  
 Во всех остальных случаях требуется масштабирование системы координат. Размещаемый элемент управления не изменяется. Вместо этого <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент пытается масштабировать размещенного элемента управления и всех его дочерних элементов управления. Поскольку [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не полностью поддерживает масштабирование, <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент масштабируется до степени, поддерживаемой определенными элементами управления.  
  
 Переопределить <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> метод для предоставления пользовательского поведения масштабирования для размещаемого [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] элемента управления.  
  
 Дополнение к масштабированию, <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент обрабатывает случаи округления и переполнения, как описано в следующей таблице.  
  
|Проблема преобразования|Описание:|  
|----------------------|-----------------|  
|Округление|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]аппаратно независимый пиксель измерения задаются в виде `double`, и [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] оборудования пикселах задаются в виде `int`. В случаях, где `double`-измерения, основанные на преобразуются в `int`-на основе измерений, <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент использует стандартное округление, поэтому дробные значения меньше 0,5 округляются до 0.|  
|Переполнение|При <xref:System.Windows.Forms.Integration.WindowsFormsHost> преобразует элемент из `double` значения `int` значения, возможна переполнения. Значения, превышающие <xref:System.Int32.MaxValue> присваиваются <xref:System.Int32.MaxValue>.|  
  
### <a name="layout-related-properties"></a>Свойства, связанные с макетом  
 Свойства, управляющие поведением макета в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов сопоставляются соответствующим образом с <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента. Дополнительные сведения см. в разделе [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
### <a name="layout-changes-in-the-hosted-control"></a>Изменения макета в размещенном элементе управления  
 Изменения макета в размещаемом [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления распространяются на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для запуска обновлений макета. <xref:System.Windows.UIElement.InvalidateMeasure%2A> Метод <xref:System.Windows.Forms.Integration.WindowsFormsHost> гарантирует, что изменения макета в размещенном элементе управления вызывают [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] запуск обработчика макета.  
  
### <a name="continuously-sized-windows-forms-controls"></a>Постоянно размера элементов управления Windows Forms  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]элементы управления, которые поддерживают непрерывное масштабирование, полностью взаимодействуют с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] система макета. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент использует <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> методы обычным для определения размеров и расположения размещенного [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.  
  
### <a name="sizing-algorithm"></a>Алгоритм изменения размера  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент использует следующую процедуру для определения размера размещенного элемента управления:  
  
1.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> Переопределяет <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> методы.  
  
2.  Для определения размера размещенного элемента управления <xref:System.Windows.FrameworkElement.MeasureOverride%2A> метод вызывает размещенного элемента управления <xref:System.Windows.Forms.Control.GetPreferredSize%2A> метод с ограничением, полученным от ограничения, передаваемый <xref:System.Windows.FrameworkElement.MeasureOverride%2A> метод.  
  
3.  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Метод пытается задать размещенного элемента управления с ограничением заданного размера.  
  
4.  Если размещенного элемента управления <xref:System.Windows.Forms.Control.Size%2A> соответствует указанным ограничениям, размещенного элемента управления изменяется в ограничение.  
  
 Если <xref:System.Windows.Forms.Control.Size%2A> свойства не соответствует указанным ограничениям, размещаемый элемент управления не поддерживает постоянное изменение размера. Например <xref:System.Windows.Forms.MonthCalendar> управления допускает только дискретные размеры. Разрешенные размеры для данного элемента управления состоят из целых чисел (представляющие номер месяца) для высоты и ширины. В подобных случаях <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент ведет себя следующим образом:  
  
-   Если <xref:System.Windows.Forms.Control.Size%2A> свойство возвращает большего размера, чем указанное ограничение, <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент отсекает размещенного элемента управления. Высота и ширина обрабатываются отдельно, поэтому размещаемый элемент управления может быть ограничен в любом направлении.  
  
-   Если <xref:System.Windows.Forms.Control.Size%2A> свойство возвращает меньший размер, чем указанное ограничение, <xref:System.Windows.Forms.Integration.WindowsFormsHost> принимает это значение размера и возвращает значение для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] система макета.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-arranging-windows-forms-controls-in-wpf.md)  
 [Элементы управления упорядочение Windows Forms в образце WPF](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
