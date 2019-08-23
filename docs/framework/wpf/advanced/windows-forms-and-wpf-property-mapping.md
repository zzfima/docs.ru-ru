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
ms.openlocfilehash: ae4a97bc96a4f9e93942b4995f488c427fda3134
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917499"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Сопоставление свойств Windows Forms и WPF
Технологии [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют две аналогичные, но разные модели свойств. *Сопоставление свойств* поддерживает взаимодействие между двумя архитектурами и предоставляет следующие возможности:  
  
- Позволяет легко сопоставлять соответствующие изменения свойств в среде размещения с размещаемым элементом управления или элементом.  
  
- Обеспечивает обработку по умолчанию для сопоставления наиболее часто используемых свойств.  
  
- Позволяет легко удалять, переопределять или расширять свойства по умолчанию.  
  
- Гарантирует, что изменения значений свойств на узле автоматически обнаруживаются и преобразуются в размещенный элемент управления или элемент.  
  
> [!NOTE]
> События изменения свойства не распространяются на элемент управления размещения или иерархию элементов. Перевод свойства не выполняется, если локальное значение свойства не меняется из-за прямого задания, стилей, наследования, привязки данных или других механизмов, изменяющих значение свойства.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> Используйте свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементаи<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> свойство элементауправлениядлядоступаксопоставлениюсвойств.<xref:System.Windows.Forms.Integration.ElementHost>  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Сопоставление свойств с элементом WindowsFormsHost  
 Элемент преобразует свойства по умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в их [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] эквиваленты с помощью следующей таблицы преобразования. <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
  
|Размещение Windows Presentation Foundation|Windows Forms|Поведение взаимодействия|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Элемент задает свойство размещенного элемента управления и <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство размещенного элемента управления. <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Integration.WindowsFormsHost> Сопоставление выполняется с помощью следующих правил.<br /><br /> — Если <xref:System.Windows.Controls.Control.Background%2A> является сплошным цветом, он преобразуется и используется для <xref:System.Windows.Forms.Control.BackColor%2A> задания свойства размещаемого элемента управления. Свойство не задано для размещенного элемента управления, поскольку размещаемый элемент управления может наследовать значение <xref:System.Windows.Forms.Control.BackColor%2A> свойства. <xref:System.Windows.Forms.Control.BackColor%2A> **Примечание.**  Размещенный элемент управления не поддерживает прозрачность. Любой цвет, назначенный <xref:System.Windows.Forms.Control.BackColor%2A> , должен быть полностью непрозрачным с альфа-значением 0xFF. <br /><br /> — Если <xref:System.Windows.Controls.Control.Background%2A> не является сплошным цветом <xref:System.Windows.Forms.Integration.WindowsFormsHost> , элемент управления <xref:System.Windows.Controls.Control.Background%2A> создает точечный рисунок из свойства. Элемент управления присваивает это изображение <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойству размещаемого элемента управления. <xref:System.Windows.Forms.Integration.WindowsFormsHost> Это дает эффект, аналогичный прозрачности. **Примечание.**  Это поведение можно переопределить, или можно удалить <xref:System.Windows.Controls.Control.Background%2A> сопоставление свойства.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Если сопоставление по умолчанию не было переназначено, <xref:System.Windows.Forms.Integration.WindowsFormsHost> управление проходит по иерархии предков до тех пор, пока не найдет предка <xref:System.Windows.FrameworkElement.Cursor%2A> с установленным свойством. Это значение преобразуется в ближайший соответствующий [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] курсор.<br /><br /> Если сопоставление по умолчанию для <xref:System.Windows.FrameworkElement.ForceCursor%2A> свойства не было переназначено, обход для первого предка останавливается с <xref:System.Windows.FrameworkElement.ForceCursor%2A> `true`параметром.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight>сопоставляется <xref:System.Windows.Forms.RightToLeft.No>с.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft>сопоставляется <xref:System.Windows.Forms.RightToLeft.Yes>с.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit>не сопоставлен.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType>сопоставляется <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>с.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A>для размещенного элемента управления<xref:System.Drawing.Font?displayProperty=nameWithType>|Набор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойств преобразуется в соответствующий <xref:System.Drawing.Font>объект. При изменении одного из этих свойств создается новое <xref:System.Drawing.Font> . Для <xref:System.Windows.FontStyles.Normal%2A> :<xref:System.Drawing.FontStyle.Italic> отключено. Для <xref:System.Windows.FontStyles.Italic%2A> или <xref:System.Windows.FontStyles.Oblique%2A> :<xref:System.Drawing.FontStyle.Italic> включен.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A>для размещенного элемента управления<xref:System.Drawing.Font?displayProperty=nameWithType>|Набор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойств преобразуется в соответствующий <xref:System.Drawing.Font>объект. При изменении одного из этих свойств создается новое <xref:System.Drawing.Font> . Для <xref:System.Windows.FontWeights.Black%2A> ,<xref:System.Windows.FontWeights.Bold%2A>, ,<xref:System.Windows.FontWeights.ExtraBold%2A>, ,<xref:System.Windows.FontWeights.Medium%2A>,или: включено<xref:System.Drawing.FontStyle.Bold> . <xref:System.Windows.FontWeights.DemiBold%2A> <xref:System.Windows.FontWeights.Heavy%2A> <xref:System.Windows.FontWeights.SemiBold%2A> <xref:System.Windows.FontWeights.UltraBold%2A> Для <xref:System.Windows.FontWeights.ExtraLight%2A> ,<xref:System.Windows.FontWeights.Light%2A>, ,<xref:System.Windows.FontWeights.Regular%2A>, или<xref:System.Windows.FontWeights.Thin%2A>: отключено<xref:System.Drawing.FontStyle.Bold> . <xref:System.Windows.FontWeights.Normal%2A> <xref:System.Windows.FontWeights.UltraLight%2A>|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|Набор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойств преобразуется в соответствующий <xref:System.Drawing.Font>объект. При изменении одного из этих свойств создается новое <xref:System.Drawing.Font> . Размер размещаемого [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления изменяется в зависимости от размера шрифта.<br /><br /> Размер шрифта в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выражается в виде одной 90-шестой дюйма и в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] виде одной севентиной секунды дюйма. Соответствующее преобразование:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]Размер шрифта = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] размер шрифта * 72,0/96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Сопоставление <xref:System.Windows.Controls.Control.Foreground%2A> свойств выполняется с помощью следующих правил.<br /><br /> Если <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Media.SolidColorBrush.Color%2A> параметр имеет значение <xref:System.Windows.Forms.Control.ForeColor%2A>, используется для. <xref:System.Windows.Media.SolidColorBrush><br />Если <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Media.GradientStop> <xref:System.Windows.Forms.Control.ForeColor%2A>параметр имеет значение ,используйтецветснаименьшимзначениемсмещениядля.<xref:System.Windows.Media.GradientBrush><br />— Для любого другого <xref:System.Windows.Media.Brush> типа оставьте <xref:System.Windows.Forms.Control.ForeColor%2A> без изменений. Это означает, что используется значение по умолчанию.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Если <xref:System.Windows.UIElement.IsEnabled%2A> задано, <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент задает <xref:System.Windows.Forms.Control.Enabled%2A> свойство размещаемого элемента управления.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Всем четырем значениям <xref:System.Windows.Forms.Control.Padding%2A> свойства размещенного [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления присваивается одно и то <xref:System.Windows.Thickness> же значение.<br /><br /> -Значения больше <xref:System.Int32.MaxValue> имеют <xref:System.Int32.MaxValue>значение.<br />— Значения меньше, <xref:System.Int32.MinValue> чем, устанавливаются в <xref:System.Int32.MinValue>значение.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible>сопоставляется <xref:System.Windows.Forms.Control.Visible%2A>с  =  .`true` Размещенный [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемент управления является видимым. Явное присвоение <xref:System.Windows.Forms.Control.Visible%2A> свойству размещенного `false` элемента управления значение не рекомендуется.<br />-   <xref:System.Windows.Visibility.Collapsed>сопоставляется <xref:System.Windows.Forms.Control.Visible%2A>  =  с или`true` . `false` Размещенный [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемент управления не рисуется, и его область сворачивается.<br />-   <xref:System.Windows.Visibility.Hidden>: Размещенный [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемент управления занимает место в макете, но не является видимым. В этом случае <xref:System.Windows.Forms.Control.Visible%2A> свойство имеет `true`значение. Явное присвоение <xref:System.Windows.Forms.Control.Visible%2A> свойству размещенного `false` элемента управления значение не рекомендуется.|  
  
 Вложенные свойства элементов контейнера полностью поддерживаются <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементом.  
  
 Дополнительные сведения см. в разделе [Пошаговое руководство: Сопоставление свойств с помощью элемента](walkthrough-mapping-properties-using-the-windowsformshost-element.md)WindowsFormsHost.  
  
## <a name="updates-to-parent-properties"></a>Обновления свойств родительского элемента  
 Изменения большинства родительских свойств приводят к размещению уведомлений в размещаемом дочернем элементе управления. В следующем списке описываются свойства, которые не вызывают уведомления при изменении их значений.  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 Например, если изменить значение <xref:System.Windows.Controls.Control.Background%2A> свойства <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента, <xref:System.Windows.Forms.Control.BackColor%2A> свойство размещенного элемента управления не изменится.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Сопоставление свойств с элементом управления ElementHost  
 Следующие свойства предоставляют встроенные уведомления об изменениях. Не вызывайте <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> метод при сопоставлении этих свойств:  
  
- AutoSize  
  
- BackColor  
  
- BackgroundImage  
  
- BackgroundImageLayout  
  
- BindingContext  
  
- CausesValidation  
  
- ContextMenu  
  
- ContextMenuStrip  
  
- Cursor (Курсор)  
  
- Закрепить  
  
- Включено  
  
- Шрифт  
  
- ForeColor  
  
- Местоположение  
  
- Поля  
  
- Заполнение  
  
- Родительский  
  
- Район  
  
- RightToLeft  
  
- Size  
  
- TabIndex  
  
- TabStop  
  
- Текст  
  
- Видимый  
  
 Элемент управления преобразует свойства по умолчанию [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в их [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эквиваленты с помощью следующей таблицы преобразования. <xref:System.Windows.Forms.Integration.ElementHost>  
  
 Дополнительные сведения см. в разделе [Пошаговое руководство: Сопоставление свойств с помощью элемента управления](walkthrough-mapping-properties-using-the-elementhost-control.md)ElementHost.  
  
|Размещение Windows Forms|Windows Presentation Foundation|Поведение взаимодействия|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) на размещенном элементе|Установка этого свойства приводит к принудительной перерисовке <xref:System.Windows.Media.ImageBrush>с помощью. <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Forms.Control.BackgroundImage%2A> <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> Если свойство имеет `false` значение (по умолчанию), это зависит от внешнего вида элемента управления, в том числе его свойств,, свойства и любой присоединенной заливки <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> соответствующих.<br /><br /> <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> Если свойство имеет `true`значение, то основано на внешнем виде родителя элемента управления, включая родительский элемент, <xref:System.Windows.Forms.Control.BackgroundImage%2A>свойства и все присоединенные заливки <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> соответствующих.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) на размещенном элементе|Задание этого свойства приводит к тому же поведению, <xref:System.Windows.Forms.Control.BackColor%2A> описанному для сопоставления.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) на размещенном элементе|Задание этого свойства приводит к тому же поведению, <xref:System.Windows.Forms.Control.BackColor%2A> описанному для сопоставления.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|Стандартный курсор преобразуется в соответствующий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] стандартный курсор. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Если не [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] является стандартным курсором, назначается значение по умолчанию.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Если <xref:System.Windows.Forms.Control.Enabled%2A> задано <xref:System.Windows.Forms.Integration.ElementHost> , элемент управления задает <xref:System.Windows.UIElement.IsEnabled%2A> свойство размещаемого элемента.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|Значение преобразуется в соответствующий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] набор свойств шрифта. <xref:System.Windows.Forms.Control.Font%2A>|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A>в размещенном элементе|Если значение <xref:System.Drawing.Font.Bold%2A> равно `true`, то <xref:System.Windows.Controls.Control.FontWeight%2A> присваивается значение <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Если значение <xref:System.Drawing.Font.Bold%2A> равно `false`, то <xref:System.Windows.Controls.Control.FontWeight%2A> присваивается значение <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A>в размещенном элементе|Если значение <xref:System.Drawing.Font.Italic%2A> равно `true`, то <xref:System.Windows.Controls.Control.FontStyle%2A> присваивается значение <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Если значение <xref:System.Drawing.Font.Italic%2A> равно `false`, то <xref:System.Windows.Controls.Control.FontStyle%2A> присваивается значение <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations>в размещенном элементе|Применяется только при размещении <xref:System.Windows.Controls.TextBlock> элемента управления.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations>в размещенном элементе|Применяется только при размещении <xref:System.Windows.Controls.TextBlock> элемента управления.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No>сопоставляется <xref:System.Windows.FlowDirection.LeftToRight>с.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes>сопоставляется <xref:System.Windows.FlowDirection.RightToLeft>с.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Integration.ElementHost> Элемент управления <xref:System.Windows.UIElement.Visibility%2A> задает свойство размещенного элемента, используя следующие правила.<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true`сопоставляется <xref:System.Windows.Visibility.Visible>с.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false`сопоставляется <xref:System.Windows.Visibility.Hidden>с.|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
- [Взаимодействие WPF и Windows Forms](wpf-and-windows-forms-interoperation.md)
- [Пошаговое руководство: Сопоставление свойств с помощью элемента WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [Пошаговое руководство: Сопоставление свойств с помощью элемента управления ElementHost](walkthrough-mapping-properties-using-the-elementhost-control.md)
