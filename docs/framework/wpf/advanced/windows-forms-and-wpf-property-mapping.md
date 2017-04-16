---
title: "Сопоставление свойств Windows Forms и WPF | Microsoft Docs"
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
  - "взаимодействие [WPF], Windows Forms"
  - "отображение свойств [взаимодействие с WPF]"
  - "Windows Forms [WPF], взаимодействие с"
  - "Windows Forms, взаимодействие с WPF"
  - "сопоставление свойств с элементом WindowsFormsHost"
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Сопоставление свойств Windows Forms и WPF
Технологии [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обладают двумя схожими, но различными моделями свойств.  *Сопоставление свойств* поддерживает взаимодействие между этими двумя архитектурами и предоставляет следующие возможности:  
  
-   Упрощает сопоставление изменений соответствующего свойства в среде хоста с размещаемым элементом управления или элементом.  
  
-   Предоставляет обработку по умолчанию для сопоставления наиболее часто используемых свойств.  
  
-   Позволяет легко удалять, переопределять или расширять свойства, заданные по умолчанию.  
  
-   Гарантирует, что изменения значения свойства в хосте автоматически обнаруживаются и преобразуются в размещаемом элементе управления или элементе.  
  
> [!NOTE]
>  События изменения свойств не распространяются по иерархии размещающего элемента управления или элемента.  Преобразование свойства не выполняется, если локальное значение свойства не изменилось при прямом задании, применении стилей, наследовании, привязке данных или при других механизмах, изменяющих значение свойства.  
  
 Для доступа к сопоставлению свойств необходимо использовать свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> и свойство <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.  
  
## Сопоставление свойств с элементом WindowsFormsHost  
 Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> преобразует свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по умолчанию в их [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] эквиваленты с помощью следующей таблицы преобразования.  
  
|Размещение Windows Presentation Foundation|Windows Forms|Взаимодействие|  
|------------------------------------------------|-------------------|--------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> задает свойства <xref:System.Windows.Forms.Control.BackColor%2A> и <xref:System.Windows.Forms.Control.BackgroundImage%2A> размещаемого элемента управления.  Сопоставление выполняется по следующим правилам:<br /><br /> -   Если значение свойства <xref:System.Windows.Controls.Control.Background%2A> является сплошным цветом, он преобразуется и используется для задания свойства <xref:System.Windows.Forms.Control.BackColor%2A> размещаемого элемента управления.  Свойство <xref:System.Windows.Forms.Control.BackColor%2A> не задается в размещаемом элементе управления, поскольку размещаемый элемент управления может наследовать значение свойства <xref:System.Windows.Forms.Control.BackColor%2A>. **Note:**  Размещаемый элемент управления не поддерживает прозрачность.  Любой цвет, присваиваемый <xref:System.Windows.Forms.Control.BackColor%2A>, должен быть полностью непрозрачным, со значением альфа 0xFF. <br /><br /> -   Если значение свойства <xref:System.Windows.Controls.Control.Background%2A> не является сплошным цветом, элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> создает точечный рисунок из свойства <xref:System.Windows.Controls.Control.Background%2A>.  Элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> присваивает данному рисунку свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> размещаемого элемента управления.  Это обеспечивает эффект сходный с эффектом прозрачности. **Note:**  Такое поведение можно переопределить или можно удалить сопоставление свойств <xref:System.Windows.Controls.Control.Background%2A>.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Если сопоставление по умолчанию не было назначено заново, элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> ищет вверх по иерархии предков, пока не обнаружит предка с набором свойств <xref:System.Windows.FrameworkElement.Cursor%2A>.  Это значение переводится в ближайший соответствующий курсор [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].<br /><br /> Если сопоставление по умолчанию для свойства <xref:System.Windows.FrameworkElement.ForceCursor%2A> не было назначено заново, поиск завершается на первом предке со свойством <xref:System.Windows.FrameworkElement.ForceCursor%2A>, имеющим значение `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> \(<xref:System.Windows.FlowDirection?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> \(<xref:System.Windows.Forms.RightToLeft?displayProperty=fullName>\)|<xref:System.Windows.FlowDirection> сопоставляется с <xref:System.Windows.Forms.RightToLeft>.<br /><br /> <xref:System.Windows.FlowDirection> сопоставляется с <xref:System.Windows.Forms.RightToLeft>.<br /><br /> <xref:System.Windows.Forms.RightToLeft> не сопоставляется.<br /><br /> <xref:System.Windows.FlowDirection?displayProperty=fullName> сопоставляется <xref:System.Windows.Forms.RightToLeft?displayProperty=fullName>.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A> на размещенном элементе управления <xref:System.Drawing.Font?displayProperty=fullName>|Набор свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] преобразуется в соответствующий <xref:System.Drawing.Font>.  Когда одно из этих свойств изменяется, создается новый объект <xref:System.Drawing.Font>.  Для свойства <xref:System.Windows.FontStyles.Normal%2A> шрифт <xref:System.Drawing.FontStyle> недоступен.  Для <xref:System.Windows.FontStyles.Italic%2A> или <xref:System.Windows.FontStyles.Oblique%2A> <xref:System.Drawing.FontStyle> доступен.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A> на размещенном элементе управления <xref:System.Drawing.Font?displayProperty=fullName>|Набор свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] преобразуется в соответствующий <xref:System.Drawing.Font>.  Когда одно из этих свойств изменяется, создается новый объект <xref:System.Drawing.Font>.  Для свойств <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A> или <xref:System.Windows.FontWeights.UltraBold%2A> функция <xref:System.Drawing.FontStyle> доступна.  Для свойств <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A> или <xref:System.Windows.FontWeights.UltraLight%2A> функция <xref:System.Drawing.FontStyle> недоступна.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> \(<xref:System.Drawing.Font?displayProperty=fullName>\)|Набор свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] преобразуется в соответствующий <xref:System.Drawing.Font>.  Когда одно из этих свойств изменяется, создается новый объект <xref:System.Drawing.Font>.  Размещаемый элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] изменяет размер в соответствии с размером шрифта.<br /><br /> Размер шрифта в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выражается как одна девяносто шестая доля дюйма, а в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] как одна семисекундная доля дюйма.  Соответствующее преобразование:<br /><br /> Размер шрифта [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] \= размер шрифта [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \* 72,0 \/ 96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|Сопоставление свойства <xref:System.Windows.Controls.Control.Foreground%2A> выполняется по следующим правилам:<br /><br /> -   Если <xref:System.Windows.Controls.Control.Foreground%2A> является <xref:System.Windows.Media.SolidColorBrush>, используйте <xref:System.Windows.Media.SolidColorBrush.Color%2A> для <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-   Если <xref:System.Windows.Controls.Control.Foreground%2A> является <xref:System.Windows.Media.GradientBrush>, используйте цвет <xref:System.Windows.Media.GradientStop> с наименьшим значением смещения для <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-   Для любого другого типа <xref:System.Windows.Media.Brush> необходимо оставить <xref:System.Windows.Forms.Control.ForeColor%2A> без изменений.  Это означает использование значения по умолчанию.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Если задано свойство <xref:System.Windows.UIElement.IsEnabled%2A>, элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> задает свойство <xref:System.Windows.Forms.Control.Enabled%2A> размещаемого элемента управления.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Все четыре значения свойства <xref:System.Windows.Forms.Control.Padding%2A> размещаемого элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] задаются тем же значением <xref:System.Windows.Thickness>.<br /><br /> -   Значения, большие <xref:System.Int32.MaxValue>, задаются <xref:System.Int32.MaxValue>.<br />-   Значения, меньшие <xref:System.Int32.MinValue>, задаются <xref:System.Int32.MinValue>.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility> сопоставляется <xref:System.Windows.Forms.Control.Visible%2A> \= `true`.  Размещаемый элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] является видимым.  Явное задание свойства <xref:System.Windows.Forms.Control.Visible%2A> размещаемого элемента управления значением `false` не рекомендуется.<br />-   <xref:System.Windows.Visibility> сопоставляется <xref:System.Windows.Forms.Control.Visible%2A> \= `true` или `false`.  Размещаемый элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не рисуется, и его область свернута.<br />-   <xref:System.Windows.Visibility>: размещаемый элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] занимает место в макете, но не отображается.  В этом случае свойство <xref:System.Windows.Forms.Control.Visible%2A> задается значением `true`.  Явное задание свойства <xref:System.Windows.Forms.Control.Visible%2A> размещаемого элемента управления значением `false` не рекомендуется.|  
  
 Вложенные свойства элементов контейнера полностью поддерживаются элементом <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
 Дополнительные сведения см. в разделе [Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## Обновление свойств родительского элемента  
 Изменения большинства свойств родительского элемента приводят к уведомлению размещаемых дочерних элементов управления.  В следующем списке описываются свойства, которые не приводят к уведомлению при изменении их значений.  
  
-   <xref:System.Windows.Controls.Control.Background%2A>  
  
-   <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
-   <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
-   <xref:System.Windows.UIElement.Visibility%2A>  
  
 Например, если изменяется значение свойства <xref:System.Windows.Controls.Control.Background%2A> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>, свойство <xref:System.Windows.Forms.Control.BackColor%2A> размещаемого элемента управления не изменится.  
  
## Сопоставление свойств с элементом управления ElementHost  
 Следующие свойства предоставляют встроенные уведомления об изменении.  Не следует вызвать метод <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> при сопоставлении этих свойств:  
  
-   AutoSize  
  
-   BackColor  
  
-   BackgroundImage  
  
-   BackgroundImageLayout  
  
-   BindingContext  
  
-   CausesValidation  
  
-   ContextMenu  
  
-   ContextMenuStrip  
  
-   Курсор  
  
-   Dock  
  
-   Enabled  
  
-   Шрифт  
  
-   ForeColor  
  
-   Расположение  
  
-   Margin  
  
-   Заполнение  
  
-   Родительский  
  
-   Region  
  
-   RightToLeft  
  
-   Размер  
  
-   TabIndex  
  
-   TabStop  
  
-   Текст  
  
-   Visible  
  
 Элемент управления <xref:System.Windows.Forms.Integration.ElementHost> преобразует свойства [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] по умолчанию в их [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эквиваленты с помощью следующей таблицы преобразования.  
  
 Дополнительные сведения см. в разделе [Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Размещение Windows Forms|Windows Presentation Foundation \(WPF\)|Взаимодействие|  
|------------------------------|---------------------------------------------|--------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\) на размещенном элементе|Задание этого свойства вызывает принудительную закраску с помощью <xref:System.Windows.Media.ImageBrush>.  Если свойство <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> имеет значение `false` \(значение по умолчанию\), объект <xref:System.Windows.Media.ImageBrush> основан на внешнем виде элемента управления <xref:System.Windows.Forms.Integration.ElementHost>, в том числе на его свойствах <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> и всех присоединенных обработчиках закраски.<br /><br /> Если свойство <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> задано значением `true` \(значением по умолчанию\), этот <xref:System.Windows.Media.ImageBrush> основан на внешнем виде родительского элемента управления <xref:System.Windows.Forms.Integration.ElementHost>, в том числе на свойствах родительского элемента <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> и всех присоединенных обработчиках закраски.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> \(<xref:System.Drawing.Image?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\) на размещенном элементе|Задание этого свойства вызывает такое же поведение, как и описанное для сопоставления <xref:System.Windows.Forms.Control.BackColor%2A>.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\) на размещенном элементе|Задание этого свойства вызывает такое же поведение, как и описанное для сопоставления <xref:System.Windows.Forms.Control.BackColor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> \(<xref:System.Windows.Forms.Cursor?displayProperty=fullName>\)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> \(<xref:System.Windows.Input.Cursor?displayProperty=fullName>\)|Стандартный курсор [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] преобразуется в соответствующий стандартный курсор [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Если [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не является стандартным курсором, назначается значение по умолчанию.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Если задано свойство <xref:System.Windows.Forms.Control.Enabled%2A>, элемент <xref:System.Windows.Forms.Integration.ElementHost> задает свойство <xref:System.Windows.UIElement.IsEnabled%2A> размещаемого элемента.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> \(<xref:System.Drawing.Font?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|Значение <xref:System.Windows.Forms.Control.Font%2A> преобразуется в соответствующий ему набор свойств шрифта [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A> размещаемого элемента|Если значение свойства <xref:System.Drawing.Font.Bold%2A> равно `true`, свойству <xref:System.Windows.Controls.Control.FontWeight%2A> присваивается значение <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Если <xref:System.Drawing.Font.Bold%2A> \- `false`, <xref:System.Windows.Controls.Control.FontWeight%2A> присваивается <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A> размещаемого элемента|Если значение свойства <xref:System.Drawing.Font.Italic%2A> равно `true`, свойству <xref:System.Windows.Controls.Control.FontStyle%2A> присваивается значение <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Если значение свойства <xref:System.Drawing.Font.Italic%2A> равно `false`, свойству <xref:System.Windows.Controls.Control.FontStyle%2A> присваивается значение <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations> размещаемого элемента|Применяется только при размещении элемента управления <xref:System.Windows.Controls.TextBlock>.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations> размещаемого элемента|Применяется только при размещении элемента управления <xref:System.Windows.Controls.TextBlock>.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> \(<xref:System.Windows.Forms.RightToLeft?displayProperty=fullName>\)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> \(<xref:System.Windows.FlowDirection>\)|<xref:System.Windows.Forms.RightToLeft> сопоставляется с <xref:System.Windows.FlowDirection>.<br /><br /> <xref:System.Windows.Forms.RightToLeft> сопоставляется с <xref:System.Windows.FlowDirection>.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|Элемент управления <xref:System.Windows.Forms.Integration.ElementHost> задает свойство <xref:System.Windows.UIElement.Visibility%2A> размещаемого элемента по следующим правилам:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> \= `true` сопоставляется <xref:System.Windows.Visibility>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> \= `false` сопоставляется <xref:System.Windows.Visibility>.|  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Взаимодействие WPF и Windows Forms](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)   
 [Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)   
 [Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)