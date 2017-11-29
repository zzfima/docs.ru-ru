---
title: "Обзор использования автоматической разметки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c9f5b9a6665778bc313febb039aeeeb2e484a6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="use-automatic-layout-overview"></a>Обзор использования автоматической разметки
В этом разделе представлены рекомендации для разработчиков по написанию [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложений с локализуемыми [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]. В прошлом локализации [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] было много времени. Каждый язык, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] адаптирован для обязательного корректировку размера x. Сегодня при правом разработки и кодирования стандартов, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] могут создаваться таким образом, что локализаторам меньше изменений размеров и положения делать. Подход к написанию приложений, которые могут быть легко изменять размер и положение называется автоматической разметкой и может осуществляться с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] разработки приложения.  
  
<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a>Преимущества использования автоматической разметки  
 Поскольку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] система представления — мощная и гибкая, он предоставляет возможность размещения элементов в приложении, которое может быть настроено в соответствии с требованиями различных языков. В следующем списке отмечены преимущества автоматической разметки.  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] отображается правильно на всех языках.  
  
-   Снижается необходимость перенастраивать расположение и размер элементов управления после перевода текста.  
  
-   Снижается необходимость перенастраивать размер окна.  
  
-   Разметка [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] отображается правильно на любом языке.  
  
-   Локализация может быть сведена не многим более чем к переводу строки.  
  
<a name="autolayout_controls"></a>   
## <a name="automatic-layout-and-controls"></a>Автоматическая разметка и элементы управления  
 Автоматическая разметка позволяет приложению устанавливать размер элемента управления автоматически. Например, элемент управления может измениться, чтобы вместить строку целиком. Эта возможность позволяет локализаторам перевести строку; больше не требуется изменять размер элемента управления, чтобы полностью отобразить переведенный текст. В следующем примере создается кнопка с текстом на английском языке.  
  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 В этом примере все, что нужно сделать, чтобы подпись кнопки была на испанском языке, — это изменить текст. Например:  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показан результат выполнения примеров кода.  
  
 ![Та же кнопка с текстовой подписью на различных языках](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Кнопка с автоматически изменяемым размером  
  
<a name="autolayout_coding"></a>   
## <a name="automatic-layout-and-coding-standards"></a>Автоматическая разметка и стандарты кодирования  
 С помощью автоматического макета требуется набор стандартов программирования и проектирования и правила для создания полностью локализуемый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Следующие рекомендации предназначены для помощи в кодировании автоматической разметки.  
  
|Стандарты кодирования|Описание|  
|----------------------|-----------------|  
|Не используйте абсолютное позиционирование.|-Не используйте <xref:System.Windows.Controls.Canvas> , так как он применяет абсолютное позиционирование элементов.<br />-Используйте <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, и <xref:System.Windows.Controls.Grid> для размещения элементов управления.<br />-Обсуждение различных типов панелей см. в разделе [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md).|  
|Не устанавливайте фиксированный размер окна.|-Используйте <xref:System.Windows.Window.SizeToContent%2A>.<br />— Пример.<br /><br /> [!code-xaml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]|  
|Добавьте элемент <xref:System.Windows.FrameworkElement.FlowDirection%2A>.|<ul><li>Добавить <xref:System.Windows.FrameworkElement.FlowDirection%2A> к корневому элементу приложения.</li><li>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет удобный способ поддержки горизонтальной, двунаправленной и вертикальной разметки. В инфраструктуре представления <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойство может использоваться для определения макета. Ниже перечислены шаблоны направления текста.<br /><br /> <ul><li><xref:System.Windows.FlowDirection.LeftToRight>(LrTb) — горизонтальная разметка для латиницы, восточноазиатских языков и т. д.</li><li><xref:System.Windows.FlowDirection.RightToLeft>(RlTb) — двунаправленная для арабского языка, иврита и т. д.</li></ul></li></ul>|  
|Используйте составные шрифты вместо физических шрифтов.|<ul><li>С составные шрифты <xref:System.Windows.Controls.Control.FontFamily%2A> свойство не требуется локализовать.</li><li>Разработчики могут использовать один из следующих шрифтов или создать свой собственный.<br /><br /> <ul><li>Глобальный пользовательский интерфейс</li><li>Global San Serif</li><li>Global Serif</li></ul></li></ul>|  
|Добавление свойства xml:lang.|-Добавьте `xml:lang` атрибут в корневом элементе вашего [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], такие как `xml:lang="en-US"` для приложения на английском языке.<br />— Поскольку составные шрифты используют `xml:lang` для определения шрифт, используемый, установите это свойство для поддержки многоязычных сценариев.|  
  
<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a>Автоматическая разметка и сетки  
 <xref:System.Windows.Controls.Grid> Элемент, полезен для автоматической разметки, поскольку он позволяет разработчику для размещения элементов. Объект <xref:System.Windows.Controls.Grid> способен распределять имеющееся пространство среди своих дочерних элементов при помощи упорядочения столбцов и строк элемента управления. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Элементы могут занимать несколько ячеек, и возможно размещение сетки внутри сетки. Сетки полезны, поскольку они позволяют создавать и позиционировать сложные [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. В следующем примере демонстрируется использование сетки для размещения нескольких кнопок и текста. Обратите внимание, что высоты и ширины ячейки установлено значение <xref:System.Windows.GridUnitType.Auto>, поэтому ячейку, содержащую кнопку с изображением подстраивается под этим изображением.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показана сетка, созданная с помощью предыдущего кода.  
  
 ![Пример сетки](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Grid  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>Автоматическая разметка и сетки, использующие свойство IsSharedSizeScope  
 Объект <xref:System.Windows.Controls.Grid> полезен в локализуемых приложениях для создания элементов управления, настраиваемых по размеру содержимого. Однако иногда требуется, чтобы элемент управления сохранял определенный размер, независимо от содержимого. Например, если имеются кнопки ОК, "Отмена" и "Обзор", то, возможно, не требуется выравнивать размер этих кнопок по размеру содержимого. В этом случае <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> вложенное свойство полезно для совместного использования одного размера несколькими элементами сетки. Следующий пример демонстрирует совместное использование столбцов и строк, изменение размера данных между несколькими <xref:System.Windows.Controls.Grid> элементов.  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **Примечание** полный образец кода, в разделе [папки изменения размера свойства между сетки](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)  
  
## <a name="see-also"></a>См. также  
 [Глобализация для WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)  
 [Использование автоматической разметки для создания кнопки](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)  
 [Использование сетки для автоматической разметки](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
