---
title: Сопоставление свойств Windows Forms и WPF
ms.date: 03/30/2017
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
ms.openlocfilehash: f2177c65a8b1a1d5ad2f5bad67591e6d98087539
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Сопоставление свойств Windows Forms и WPF
[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] И [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] технологии имеют две модели похожие, но различные свойства. *Сопоставление свойств* поддерживает взаимодействие между этими двумя архитектурами и предоставляет следующие возможности:  
  
-   Упрощает сопоставление изменений соответствующего свойства в среде узла размещенного элемента управления или элемент.  
  
-   Предоставляет по умолчанию обработка для сопоставления наиболее часто используемые свойства.  
  
-   Позволяет легко удалять, переопределять или расширять свойств по умолчанию.  
  
-   Гарантирует, что изменения значения свойства узла автоматически обнаруживаются и преобразованный размещенного элемента управления или элемента.  
  
> [!NOTE]
>  События изменения свойств не распространяются вверх размещения элемента управления или элемента иерархии. Свойство преобразование не выполняется, если локальное значение свойства не изменяется из-за прямой установки, стили, наследования, привязки данных или других механизмов, которые изменяют значение свойства.  
  
 Используйте <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент и <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> свойства <xref:System.Windows.Forms.Integration.ElementHost> элемента управления для доступа к сопоставлению свойств.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Сопоставление свойств с помощью элемента WindowsFormsHost  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> По умолчанию преобразует элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства, чтобы их [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] эквиваленты с помощью следующей таблицы преобразования.  
  
|Размещение Windows Presentation Foundation|Windows Forms|Возможности взаимодействия|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Integration.WindowsFormsHost> Наборы элементов <xref:System.Windows.Forms.Control.BackColor%2A> свойство размещенного элемента управления и <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство размещенного элемента управления. Сопоставление выполняется по следующим правилам:<br /><br /> -Если <xref:System.Windows.Controls.Control.Background%2A> является сплошным цветом, его преобразования и используется для задания <xref:System.Windows.Forms.Control.BackColor%2A> свойство размещенного элемента управления. <xref:System.Windows.Forms.Control.BackColor%2A> Свойство не задано размещенным элементом управления, поскольку размещаемый элемент управления может наследовать значение <xref:System.Windows.Forms.Control.BackColor%2A> свойства. **Примечание:** размещенного элемента управления не поддерживают прозрачность. Любой цвет, назначенный <xref:System.Windows.Forms.Control.BackColor%2A> должен быть полностью непрозрачным, со значением альфа 0xFF. <br /><br /> -Если <xref:System.Windows.Controls.Control.Background%2A> не сплошным цветом, <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления создает точечный рисунок из <xref:System.Windows.Controls.Control.Background%2A> свойство. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Управления присваивает данному рисунку <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство размещенного элемента управления. Это дает эффект, аналогичный прозрачности. **Примечание:** это поведение можно переопределить или удалить <xref:System.Windows.Controls.Control.Background%2A> сопоставление свойств.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Если сопоставление по умолчанию не было назначено заново, <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления проходит через иерархии предков, пока не найдет предка с его <xref:System.Windows.FrameworkElement.Cursor%2A> набор свойств. Это значение переводится в ближайший соответствующий [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] курсора.<br /><br /> Если сопоставление по умолчанию для <xref:System.Windows.FrameworkElement.ForceCursor%2A> свойство не было назначено заново, поиск завершается на первом предке со <xref:System.Windows.FrameworkElement.ForceCursor%2A> значение `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> сопоставляется с <xref:System.Windows.Forms.RightToLeft.No>.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> сопоставляется с <xref:System.Windows.Forms.RightToLeft.Yes>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit> не сопоставлен.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> сопоставляется с <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A> размещенным элементом управления <xref:System.Drawing.Font?displayProperty=nameWithType>|Набор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства преобразуется в соответствующий <xref:System.Drawing.Font>. При изменении одного из этих свойств, новый <xref:System.Drawing.Font> создается. Для <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic> отключена. Для <xref:System.Windows.FontStyles.Italic%2A> или <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle.Italic> включен.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A> размещенным элементом управления <xref:System.Drawing.Font?displayProperty=nameWithType>|Набор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства преобразуется в соответствующий <xref:System.Drawing.Font>. При изменении одного из этих свойств, новый <xref:System.Drawing.Font> создается. Для <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>, или <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold> включен. Для <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>, или <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold> отключена.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|Набор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства преобразуется в соответствующий <xref:System.Drawing.Font>. При изменении одного из этих свойств, новый <xref:System.Drawing.Font> создается. Размещаемый [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемент управления на основе размера шрифта.<br /><br /> Размер шрифта в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выражается как одну девяносто шестую дюйма, а в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] как одна семисекундная дюйма. Соответствующее преобразование является:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] размер шрифта = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] размер шрифта * 72,0 / 96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Foreground%2A> Сопоставление свойств выполняется с помощью следующих правил:<br /><br /> -Если <xref:System.Windows.Controls.Control.Foreground%2A> — <xref:System.Windows.Media.SolidColorBrush>, используйте <xref:System.Windows.Media.SolidColorBrush.Color%2A> для <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Если <xref:System.Windows.Controls.Control.Foreground%2A> — <xref:System.Windows.Media.GradientBrush>, используйте цвет <xref:System.Windows.Media.GradientStop> с наименьшим значением смещения для <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Для любых других <xref:System.Windows.Media.Brush> введите, оставьте <xref:System.Windows.Forms.Control.ForeColor%2A> без изменений. Это означает, что используется значение по умолчанию.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Когда <xref:System.Windows.UIElement.IsEnabled%2A> имеет значение <xref:System.Windows.Forms.Integration.WindowsFormsHost> наборы элементов <xref:System.Windows.Forms.Control.Enabled%2A> свойство размещенным элементом управления.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Все четыре значения <xref:System.Windows.Forms.Control.Padding%2A> свойство размещаемого [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления задаются с тем же <xref:System.Windows.Thickness> значение.<br /><br /> -Значения, превышающие <xref:System.Int32.MaxValue> присваиваются <xref:System.Int32.MaxValue>.<br />-Значения меньше, чем <xref:System.Int32.MinValue> присваиваются <xref:System.Int32.MinValue>.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible> Сопоставляет <xref:System.Windows.Forms.Control.Visible%2A>  =  `true`. Размещаемый [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемент управления является видимым. После явного задания <xref:System.Windows.Forms.Control.Visible%2A> свойства размещенного элемента управления для `false` не рекомендуется.<br />-   <xref:System.Windows.Visibility.Collapsed> Сопоставляет <xref:System.Windows.Forms.Control.Visible%2A>  =  `true` или `false`. Размещаемый [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления не рисуется, и его область свернута.<br />-   <xref:System.Windows.Visibility.Hidden> : Размещаемый [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления занимает место в макете, но не отображается. В этом случае <xref:System.Windows.Forms.Control.Visible%2A> свойству `true`. После явного задания <xref:System.Windows.Forms.Control.Visible%2A> свойства размещенного элемента управления для `false` не рекомендуется.|  
  
 Вложенные свойства элементов контейнера полностью поддерживаются <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.  
  
 Дополнительные сведения см. в разделе [Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## <a name="updates-to-parent-properties"></a>Обновление свойств родительского элемента  
 Изменения большинства свойств родительского элемента приводят к уведомлению размещаемых дочерних элементов управления. В следующем списке описываются свойства, которые не вызывают уведомления при изменении их значений.  
  
-   <xref:System.Windows.Controls.Control.Background%2A>  
  
-   <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
-   <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
-   <xref:System.Windows.UIElement.Visibility%2A>  
  
 Например, если изменить значение <xref:System.Windows.Controls.Control.Background%2A> свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент, <xref:System.Windows.Forms.Control.BackColor%2A> свойство размещенного элемента управления не меняется.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Сопоставление свойств с помощью элемента управления ElementHost  
 Следующие свойства предоставляют встроенные уведомления об изменении. Не вызывайте <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> метод при сопоставлении этих свойств:  
  
-   AutoSize  
  
-   Цвет фона  
  
-   BackgroundImage  
  
-   BackgroundImageLayout  
  
-   BindingContext  
  
-   CausesValidation  
  
-   ContextMenu  
  
-   ContextMenuStrip  
  
-   Курсор  
  
-   Закрепить  
  
-   Включено  
  
-   Шрифт  
  
-   Цвет переднего плана  
  
-   Расположение  
  
-   Поля  
  
-   Заполнение  
  
-   Родительский  
  
-   Region  
  
-   RightToLeft  
  
-   Размер  
  
-   TabIndex  
  
-   TabStop  
  
-   Text  
  
-   Показывается  
  
 <xref:System.Windows.Forms.Integration.ElementHost> Управления преобразует по умолчанию [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] свойства, чтобы их [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эквиваленты с помощью следующей таблицы преобразования.  
  
 Дополнительные сведения см. в разделе [Пошаговое руководство: сопоставление свойств с помощью элемента управления ElementHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Размещение в Windows Forms|Windows Presentation Foundation|Возможности взаимодействия|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) размещаемого элемента|Задание этого свойства вызывает перерисовку с <xref:System.Windows.Media.ImageBrush>. Если <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> свойству `false` (значение по умолчанию), это <xref:System.Windows.Media.ImageBrush> зависит от вида <xref:System.Windows.Forms.Integration.ElementHost> управления, включая его <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> свойства и все присоединенные рисования обработчики.<br /><br /> Если <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> свойству `true`, <xref:System.Windows.Media.ImageBrush> зависит от вида <xref:System.Windows.Forms.Integration.ElementHost> родительского элемента управления, включая родительского элемента <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> свойства и все присоединенные рисования обработчики.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) размещаемого элемента|Установка этого свойства приводит к тому же поведение, описанное для <xref:System.Windows.Forms.Control.BackColor%2A> сопоставления.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) размещаемого элемента|Установка этого свойства приводит к тому же поведение, описанное для <xref:System.Windows.Forms.Control.BackColor%2A> сопоставления.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Стандартный курсор преобразуется в соответствующий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] стандартным курсором. Если [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не является стандартным курсором, назначается значение по умолчанию.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Когда <xref:System.Windows.Forms.Control.Enabled%2A> имеет значение <xref:System.Windows.Forms.Integration.ElementHost> задает <xref:System.Windows.UIElement.IsEnabled%2A> свойства размещаемого элемента.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A> Преобразуется в соответствующий набор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства шрифта.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A> размещаемого элемента|Если значение <xref:System.Drawing.Font.Bold%2A> равно `true`, то <xref:System.Windows.Controls.Control.FontWeight%2A> присваивается значение <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Если значение <xref:System.Drawing.Font.Bold%2A> равно `false`, то <xref:System.Windows.Controls.Control.FontWeight%2A> присваивается значение <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A> размещаемого элемента|Если значение <xref:System.Drawing.Font.Italic%2A> равно `true`, то <xref:System.Windows.Controls.Control.FontStyle%2A> присваивается значение <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Если значение <xref:System.Drawing.Font.Italic%2A> равно `false`, то <xref:System.Windows.Controls.Control.FontStyle%2A> присваивается значение <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations> размещаемого элемента|Применяется только при размещении <xref:System.Windows.Controls.TextBlock> элемента управления.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations> размещаемого элемента|Применяется только при размещении <xref:System.Windows.Controls.TextBlock> элемента управления.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> сопоставляется с <xref:System.Windows.FlowDirection.LeftToRight>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> сопоставляется с <xref:System.Windows.FlowDirection.RightToLeft>.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Integration.ElementHost> Задает <xref:System.Windows.UIElement.Visibility%2A> свойства размещаемого элемента с помощью следующих правил:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true` Сопоставляет <xref:System.Windows.Visibility.Visible>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false` Сопоставляет <xref:System.Windows.Visibility.Hidden>.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Взаимодействие WPF и Windows Forms](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)  
 [Пошаговое руководство. Сопоставление свойств с помощью элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)  
 [Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)
