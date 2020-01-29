---
title: Сопоставление свойств Windows Forms и WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
ms.openlocfilehash: 07e58f87d886212426e25be83f988037549ab642
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735233"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Сопоставление свойств Windows Forms и WPF
Технологии [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют две аналогичные, но разные модели свойств. *Сопоставление свойств* поддерживает взаимодействие между двумя архитектурами и предоставляет следующие возможности:  
  
- Позволяет легко сопоставлять соответствующие изменения свойств в среде размещения с размещаемым элементом управления или элементом.  
  
- Обеспечивает обработку по умолчанию для сопоставления наиболее часто используемых свойств.  
  
- Позволяет легко удалять, переопределять или расширять свойства по умолчанию.  
  
- Гарантирует, что изменения значений свойств на узле автоматически обнаруживаются и преобразуются в размещенный элемент управления или элемент.  
  
> [!NOTE]
> События изменения свойства не распространяются на элемент управления размещения или иерархию элементов. Перевод свойства не выполняется, если локальное значение свойства не меняется из-за прямого задания, стилей, наследования, привязки данных или других механизмов, изменяющих значение свойства.  
  
 Для доступа к сопоставлению свойств используйте свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> и свойство <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> для элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Сопоставление свойств с элементом WindowsFormsHost  
 Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> преобразует свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по умолчанию в их [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] эквиваленты с помощью следующей таблицы преобразования.  
  
|Размещение Windows Presentation Foundation|Windows Forms|Поведение взаимодействия|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> задает свойство <xref:System.Windows.Forms.Control.BackColor%2A> размещаемого элемента управления и свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> размещаемого элемента управления. Сопоставление выполняется с помощью следующих правил.<br /><br /> — Если <xref:System.Windows.Controls.Control.Background%2A> является сплошным цветом, он преобразуется и используется для установки свойства <xref:System.Windows.Forms.Control.BackColor%2A> размещаемого элемента управления. Свойство <xref:System.Windows.Forms.Control.BackColor%2A> не задано для размещенного элемента управления, так как размещаемый элемент управления может наследовать значение свойства <xref:System.Windows.Forms.Control.BackColor%2A>. **Примечание.**  Размещенный элемент управления не поддерживает прозрачность. Любой цвет, назначенный <xref:System.Windows.Forms.Control.BackColor%2A>, должен быть полностью непрозрачным с альфа-значением 0xFF. <br /><br /> — Если <xref:System.Windows.Controls.Control.Background%2A> не является сплошным цветом, элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> создает точечный рисунок из свойства <xref:System.Windows.Controls.Control.Background%2A>. Элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> присваивает этот точечный рисунок свойству <xref:System.Windows.Forms.Control.BackgroundImage%2A> размещаемого элемента управления. Это дает эффект, аналогичный прозрачности. **Примечание.**  Это поведение можно переопределить, или можно удалить сопоставление свойств <xref:System.Windows.Controls.Control.Background%2A>.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Если сопоставление по умолчанию не было переназначено, <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент управления проходит по иерархии предков до тех пор, пока не найдет предка с установленным свойством <xref:System.Windows.FrameworkElement.Cursor%2A>. Это значение преобразуется в ближайшее соответствующее [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] курсоре.<br /><br /> Если сопоставление по умолчанию для свойства <xref:System.Windows.FrameworkElement.ForceCursor%2A> не было переназначено, обход для первого предка останавливается с <xref:System.Windows.FrameworkElement.ForceCursor%2A> установлен в значение `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> сопоставляется с <xref:System.Windows.Forms.RightToLeft.No>.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> сопоставляется с <xref:System.Windows.Forms.RightToLeft.Yes>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit> не сопоставлен.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> сопоставляется с <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A> на <xref:System.Drawing.Font?displayProperty=nameWithType> размещенного элемента управления|Набор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойств преобразуется в соответствующий <xref:System.Drawing.Font>. При изменении одного из этих свойств создается новый <xref:System.Drawing.Font>. Для <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic> отключена. Для <xref:System.Windows.FontStyles.Italic%2A> или <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle.Italic> включена.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A> на <xref:System.Drawing.Font?displayProperty=nameWithType> размещенного элемента управления|Набор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойств преобразуется в соответствующий <xref:System.Drawing.Font>. При изменении одного из этих свойств создается новый <xref:System.Drawing.Font>. Для <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>или <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold> включен. Для <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>или <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold> отключен.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|Набор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойств преобразуется в соответствующий <xref:System.Drawing.Font>. При изменении одного из этих свойств создается новый <xref:System.Drawing.Font>. Размер размещаемого элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] изменяется в зависимости от размера шрифта.<br /><br /> Размер шрифта в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выражается в виде одной 90-шестой дюйма, а в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] как одна Севенти дюйма. Соответствующее преобразование:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] размер шрифта = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] размер шрифта * 72,0/96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Сопоставление свойства <xref:System.Windows.Controls.Control.Foreground%2A> выполняется с помощью следующих правил.<br /><br /> — Если <xref:System.Windows.Controls.Control.Foreground%2A> является <xref:System.Windows.Media.SolidColorBrush>, используйте <xref:System.Windows.Media.SolidColorBrush.Color%2A> для <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />— Если <xref:System.Windows.Controls.Control.Foreground%2A> является <xref:System.Windows.Media.GradientBrush>, используйте цвет <xref:System.Windows.Media.GradientStop> с наименьшим значением смещения для <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />— Для любого другого типа <xref:System.Windows.Media.Brush> оставьте <xref:System.Windows.Forms.Control.ForeColor%2A> без изменений. Это означает, что используется значение по умолчанию.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Если параметр <xref:System.Windows.UIElement.IsEnabled%2A> установлен, <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент задает свойство <xref:System.Windows.Forms.Control.Enabled%2A> размещаемого элемента управления.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Всем четырем значениям свойства <xref:System.Windows.Forms.Control.Padding%2A> в размещенном элементе управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] присваивается одно и то же значение <xref:System.Windows.Thickness>.<br /><br /> -Значения, превышающие <xref:System.Int32.MaxValue>, задаются равными <xref:System.Int32.MaxValue>.<br />— Значения меньше <xref:System.Int32.MinValue> задаются равными <xref:System.Int32.MinValue>.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible> сопоставляется с <xref:System.Windows.Forms.Control.Visible%2A> = `true`. Размещенный элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] является видимым. Явное задание свойства <xref:System.Windows.Forms.Control.Visible%2A> для размещенного элемента управления на `false` не рекомендуется.<br />-   <xref:System.Windows.Visibility.Collapsed> сопоставляется с <xref:System.Windows.Forms.Control.Visible%2A> = `true` или `false`. Размещенный элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не рисуется, и его область сворачивается.<br />-   <xref:System.Windows.Visibility.Hidden>: размещаемый элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] занимает место в макете, но не отображается. В этом случае свойство <xref:System.Windows.Forms.Control.Visible%2A> имеет значение `true`. Явное задание свойства <xref:System.Windows.Forms.Control.Visible%2A> для размещенного элемента управления на `false` не рекомендуется.|  
  
 Вложенные свойства элементов контейнера полностью поддерживаются элементом <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
 Дополнительные сведения см. [в разделе Пошаговое руководство. Сопоставление свойств с помощью элемента WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## <a name="updates-to-parent-properties"></a>Обновления свойств родительского элемента  
 Изменения большинства родительских свойств приводят к размещению уведомлений в размещаемом дочернем элементе управления. В следующем списке описываются свойства, которые не вызывают уведомления при изменении их значений.  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 Например, если изменить значение свойства <xref:System.Windows.Controls.Control.Background%2A> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>, то свойство <xref:System.Windows.Forms.Control.BackColor%2A> размещаемого элемента управления не изменится.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Сопоставление свойств с элементом управления ElementHost  
 Следующие свойства предоставляют встроенные уведомления об изменениях. Не вызывайте метод <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> при сопоставлении этих свойств:  
  
- Автомасштаб  
  
- BackColor  
  
- BackgroundImage  
  
- BackgroundImageLayout  
  
- BindingContext  
  
- CausesValidation  
  
- ContextMenu  
  
- ContextMenuStrip  
  
- Курсор  
  
- Закрепить  
  
- Enabled  
  
- Шрифт  
  
- ForeColor  
  
- Местоположение  
  
- Поля  
  
- Заполнение  
  
- Parent  
  
- Region  
  
- RightToLeft  
  
- Размер  
  
- TabIndex  
  
- TabStop  
  
- Текст  
  
- Видимый  
  
 <xref:System.Windows.Forms.Integration.ElementHost> элемент управления преобразует свойства [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] по умолчанию в их [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эквиваленты с помощью следующей таблицы преобразования.  
  
 Дополнительные сведения см. [в разделе Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost](walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Размещение Windows Forms|Windows Presentation Foundation (WPF)|Поведение взаимодействия|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) в размещенном элементе|Установка этого свойства приводит к принудительному перерисовке с помощью <xref:System.Windows.Media.ImageBrush>. Если свойство <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> имеет значение `false` (по умолчанию), это <xref:System.Windows.Media.ImageBrush> основано на внешнем элементе управления <xref:System.Windows.Forms.Integration.ElementHost>, включая его <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> свойства и все присоединенные обработчики Paint.<br /><br /> Если свойство <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> имеет значение `true`, то <xref:System.Windows.Media.ImageBrush> основано на внешнем виде родительского элемента управления <xref:System.Windows.Forms.Integration.ElementHost>, включая свойства родителя <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> и все присоединенные обработчики Paint.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) в размещенном элементе|Задание этого свойства приводит к тому же поведению, описанному для сопоставления <xref:System.Windows.Forms.Control.BackColor%2A>.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) в размещенном элементе|Задание этого свойства приводит к тому же поведению, описанному для сопоставления <xref:System.Windows.Forms.Control.BackColor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|Стандартный курсор [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] преобразуется в соответствующий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] стандартный курсор. Если [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не является стандартным курсором, назначается значение по умолчанию.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|При установке <xref:System.Windows.Forms.Control.Enabled%2A> элемент управления <xref:System.Windows.Forms.Integration.ElementHost> устанавливает свойство <xref:System.Windows.UIElement.IsEnabled%2A> размещаемого элемента.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A> значение преобразуется в соответствующий набор свойств шрифта [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A> размещенного элемента|Если значение <xref:System.Drawing.Font.Bold%2A> равно `true`, то <xref:System.Windows.Controls.Control.FontWeight%2A> присваивается значение <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Если значение <xref:System.Drawing.Font.Bold%2A> равно `false`, то <xref:System.Windows.Controls.Control.FontWeight%2A> присваивается значение <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A> размещенного элемента|Если значение <xref:System.Drawing.Font.Italic%2A> равно `true`, то <xref:System.Windows.Controls.Control.FontStyle%2A> присваивается значение <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Если значение <xref:System.Drawing.Font.Italic%2A> равно `false`, то <xref:System.Windows.Controls.Control.FontStyle%2A> присваивается значение <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations> размещенного элемента|Применяется только при размещении элемента управления <xref:System.Windows.Controls.TextBlock>.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations> размещенного элемента|Применяется только при размещении элемента управления <xref:System.Windows.Controls.TextBlock>.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> сопоставляется с <xref:System.Windows.FlowDirection.LeftToRight>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> сопоставляется с <xref:System.Windows.FlowDirection.RightToLeft>.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|Элемент управления <xref:System.Windows.Forms.Integration.ElementHost> задает свойство <xref:System.Windows.UIElement.Visibility%2A> в размещенном элементе, используя следующие правила.<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true` сопоставлены с <xref:System.Windows.Visibility.Visible>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false` сопоставлены с <xref:System.Windows.Visibility.Hidden>.|  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
- [Взаимодействие WPF и Windows Forms](wpf-and-windows-forms-interoperation.md)
- [Пошаговое руководство. Сопоставление свойств с помощью элемента WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost](walkthrough-mapping-properties-using-the-elementhost-control.md)
