---
title: "Обзор использования автоматической разметки | Microsoft Docs"
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
  - "автоматический макет"
  - "макет, автоматическая"
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Обзор использования автоматической разметки
В этом разделе представлены рекомендации разработчикам о написании приложений [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] с локализуемыми [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].  В прошлом процесс локализации [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] занимал значительное время.  Каждый язык, для которого адаптировался [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], требовал попиксельного выравнивания.  Сегодня при соблюдении стандартов разработки и кодирования [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] может быть создан таким образом, чтобы локализаторам требовалось выполнять меньше изменений размеров и расположений.  Подход к написанию приложений с более легким изменением размеров и расположения называется автоматической разметкой и может быть достигнут с использованием структуры приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 В этом разделе содержатся следующие подразделы.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Преимущества использования автоматической разметки](#advantages_of_autolayout)  
  
-   [Автоматическая разметка и элементы управления](#autolayout_controls)  
  
-   [Автоматическая разметка и стандарты кодирования](#autolayout_coding)  
  
-   [Автоматическая разметка и сетки](#autolay_grids)  
  
-   [Автоматическая разметка и сетки, использующие свойство IsSharedSizeScope](#autolay_grids_issharedsizescope)  
  
-   [Связанные разделы](#seeAlsoToggle)  
  
<a name="advantages_of_autolayout"></a>   
## Преимущества использования автоматической разметки  
 Поскольку система представления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является мощной и гибкой, она обеспечивает возможность размещения элементов в приложении, которое может быть настроено в соответствии с требованиями различных языков.  В следующем списке отмечены преимущества автоматической разметки.  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] отображается правильно на всех языках.  
  
-   Снижается необходимость перенастраивать расположение и размер элементов управления после перевода текста.  
  
-   Снижается необходимость перенастраивать размер окна.  
  
-   Разметка [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] отображается правильно на любом языке.  
  
-   Локализация может быть сведена не многим более чем к переводу строки.  
  
<a name="autolayout_controls"></a>   
## Автоматическая разметка и элементы управления  
 Автоматическая разметка позволяет приложению устанавливать размер элемента управления автоматически.  Например, элемент управления может измениться, чтобы вместить строку целиком.  Эта возможность позволяет локализаторам перевести строку; больше не требуется изменять размер элемента управления, чтобы полностью отобразить переведенный текст.  В следующем примере создается кнопка с текстом на английском языке.  
  
 [!code-xml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 В этом примере все, что нужно сделать, чтобы подпись кнопки была на испанском языке, — это изменить текст.  Например:  
  
 [!code-xml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показан вывод примеров кода.  
  
 ![Та же кнопка с текстовой подписью на различных языках](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Кнопка с автоматически изменяемым размером  
  
<a name="autolayout_coding"></a>   
## Автоматическая разметка и стандарты кодирования  
 Для использования автоматической разметки требуется набор стандартов и правил разработки и кодирования, которые позволят создать полностью локализуемый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Следующие рекомендации предназначены для помощи в кодировании автоматической разметки.  
  
|Стандарты кодирования|Описание|  
|---------------------------|--------------|  
|Не используйте абсолютное позиционирование.|-   Не используйте элемент управления <xref:System.Windows.Controls.Canvas>, так как он применяет абсолютное позиционирование элементов.<br />-   Для расположения элементов управления используйте элементы управления <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.Grid>.<br />-   Обсуждение различных типов панелей см. в разделе [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md).|  
|Не устанавливайте фиксированный размер окна.|-   Используйте событие <xref:System.Windows.Window.SizeToContent%2A>.<br />-   Примеры.<br /><br /> [!code-xml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]|  
|Добавьте свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A>.|<ul><li>Добавьте свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> к корневому элементу приложения.</li><li>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет удобный способ поддержки горизонтальной, двунаправленной и вертикальной разметки.  Для определения направления в инфраструктуре представления можно использовать свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  Ниже перечислены шаблоны направления текста.<br /><br /> <ul><li><xref:System.Windows.FlowDirection> \(LrTb\) — горизонтальная разметка для латинского языка, восточноазиатских языков и т. д.</li><li><xref:System.Windows.FlowDirection> \(RlTb\) — двунаправленная разметка для арабского, иврита и др. языков.</li></ul></li></ul>|  
|Используйте составные шрифты вместо физических шрифтов.|<ul><li>С составными шрифтами свойство <xref:System.Windows.Controls.Control.FontFamily%2A> не требует локализации.</li><li>Разработчики могут использовать один из следующих шрифтов или создать свой собственный.<br /><br /> <ul><li>Global User Interface</li><li>Global San Serif</li><li>Global Serif</li></ul></li></ul>|  
|Добавление свойства "xml:lang".|-   Добавьте атрибут `xml:lang` в корневом элементе вашего [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], как, например, `xml:lang="en-US"` для приложения на английском языке.<br />-   Поскольку составные шрифты используют `xml:lang` для определения, какой шрифт использовать, установите это свойство для поддержки многоязычных сценариев.|  
  
<a name="autolay_grids"></a>   
## Автоматическая разметка и сетки  
 Элемент <xref:System.Windows.Controls.Grid> полезен для автоматической разметки, поскольку он позволяет разработчику позиционировать элементы.  Элемент управления <xref:System.Windows.Controls.Grid> способен распределять имеющееся пространство среди своих дочерних элементов при помощи упорядочения столбцов и строк.  Элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] могут занимать несколько ячеек, и возможно размещение сетки внутри сетки.  Сетки полезны, поскольку они позволяют создавать и позиционировать сложные [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  В следующем примере демонстрируется использование сетки для размещения нескольких кнопок и текста.  Обратите внимание, что для высоты и ширины ячейки установлено значение <xref:System.Windows.GridUnitType>; таким образом, размер ячейки, содержащей кнопку с изображением, изменяется в соответствии с этим изображением.  
  
 [!code-xml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показана сетка, созданная с помощью предыдущего кода.  
  
 ![Пример сетки](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob\_grid")  
Сетка  
  
<a name="autolay_grids_issharedsizescope"></a>   
## Автоматическая разметка и сетки, использующие свойство IsSharedSizeScope  
 <xref:System.Windows.Controls.Grid> полезен в локализуемых приложениях для создания элементов управления, настраиваемых по размеру содержимого.  Однако иногда требуется, чтобы элемент управления сохранял определенный размер, независимо от содержимого.  Например, если имеются кнопки "ОК", "Отмена" и "Обзор", то, возможно, не требуется выравнивать размер этих кнопок по размеру содержимого.  В этом случае, вложенное свойство элемента <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=fullName> полезно для общего использования одного размера несколькими элементами сетки.  В следующем примере демонстрируется совместное использование столбцов и строк, изменяющихся в размере в зависимости от данных, между несколькими элементами <xref:System.Windows.Controls.Grid>.  
  
 [!code-xml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **Примечание.** Полный код примера см. в разделе [Совместное использование свойств размера между сетками](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)  
  
## См. также  
 [Глобализация для WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)   
 [Использование автоматической разметки для создания кнопки](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)   
 [Использование сетки для автоматической разметки](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)