---
title: Обзор использования автоматической разметки
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: a43b3c0e008025171e3b1fdeba3bc514d01e28c8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542628"
---
# <a name="use-automatic-layout-overview"></a>Обзор использования автоматической разметки
В этом разделе представлены рекомендации разработчикам о написании [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложений с локализуемым [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]. В прошлом, локализация [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] было много времени. Каждый язык, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] адаптирован для требовал попиксельного выравнивания. Сегодня при правом разработки и кодирования стандартов, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] могут создаваться таким образом, чтобы локализаторам требовалось выполнять меньше изменений размеров и расположений для выполнения. Подход к написанию приложений, в которых проще изменять размер и положение элементов называется автоматической разметкой и может осуществляться с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] разработки приложения.  
  
<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a>Преимущества использования автоматической разметки  
 Так как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] систему представления является мощной и гибкой, она предоставляет возможность размещения элементов в приложении, которое может быть настроено в соответствии с требованиями различных языков. В следующем списке отмечены преимущества автоматической разметки.  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] отображается правильно на всех языках.  
  
-   Снижается необходимость перенастраивать расположение и размер элементов управления после перевода текста.  
  
-   Снижается необходимость перенастраивать размер окна.  
  
-   Разметка [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] отображается правильно на любом языке.  
  
-   Локализация может быть сведена не многим более чем к переводу строки.  
  
<a name="autolayout_controls"></a>   
## <a name="automatic-layout-and-controls"></a>Автоматическая разметка и элементы управления  
 Автоматическая разметка позволяет приложению устанавливать размер элемента управления автоматически. Например, элемент управления может измениться, чтобы вместить строку целиком. Эта возможность позволяет локализаторам перевести строку; больше не требуется изменять размер элемента управления, чтобы полностью отобразить переведенный текст. В следующем примере создается кнопка с текстом на английском языке.  
  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 В этом примере все, что нужно сделать, чтобы подпись кнопки была на испанском языке, — это изменить текст. Например, примененная к объекту директива  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показан результат выполнения примеров кода.  
  
 ![Та же кнопка с текстом на разных языках](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Кнопка с автоматически изменяемым размером  
  
<a name="autolayout_coding"></a>   
## <a name="automatic-layout-and-coding-standards"></a>Автоматическая разметка и стандарты кодирования  
 Использование автоматической разметки требуется набор стандартов программирования и проектирования и правила, чтобы создать полностью локализуемый [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Следующие рекомендации предназначены для помощи в кодировании автоматической разметки.  
  
| Стандарты кодирования | Описание |
| ---------------------- | ----------------- |
| Не используйте абсолютное позиционирование. | <ul><li>Не используйте <xref:System.Windows.Controls.Canvas> так, как он применяет абсолютное позиционирование элементов.</li><li>Используйте <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, и <xref:System.Windows.Controls.Grid> для размещения элементов управления.</li><li>Обсуждение различных типов панелей, см. в разделе [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md).</li></ul> |
| Не устанавливайте фиксированный размер окна. | — Используйте <xref:System.Windows.Window.SizeToContent%2A>.<br />Пример:<br /><br /> [!code-xaml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)] |
| Добавьте элемент <xref:System.Windows.FrameworkElement.FlowDirection%2A>. | <ul><li>Добавить <xref:System.Windows.FrameworkElement.FlowDirection%2A> к корневому элементу приложения.</li><li>WPF предоставляет удобный способ поддержки горизонтальной, двунаправленной и вертикальной разметки. В инфраструктуре представления <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойство может использоваться для определения макета. Ниже перечислены шаблоны направления текста.<br /><br /> <ul><li><xref:System.Windows.FlowDirection.LeftToRight> (LrTb) — горизонтальная разметка для латиницы, восточноазиатских языков и т. д.</li><li><xref:System.Windows.FlowDirection.RightToLeft> (RlTb) — двунаправленная разметка для арабского, иврита и т. д.</li></ul></li></ul> |
| Используйте составные шрифты вместо физических шрифтов. | <ul><li>С составными шрифтами <xref:System.Windows.Controls.Control.FontFamily%2A> свойство необходимо локализовать.</li><li>Разработчики могут использовать один из следующих шрифтов или создать свой собственный.<br /><br /> <ul><li>Глобальный пользовательский интерфейс</li><li>Global San Serif</li><li>Global Serif</li></ul></li></ul> |
| Добавление свойства xml:lang. | <ul><li>Добавить `xml:lang` атрибут в корневом элементе вашего [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], такие как `xml:lang="en-US"` для приложения на английском языке.</li><li>Поскольку составные шрифты используют `xml:lang` для определения того, какой шрифт использовать, установите это свойство для поддержки многоязычных сценариев.</li></ul> |
  
<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a>Автоматическая разметка и сетки  
 <xref:System.Windows.Controls.Grid> Элемент, полезен для автоматической разметки, так как он позволяет разработчику позиционировать элементы. Объект <xref:System.Windows.Controls.Grid> способен распределять имеющееся пространство среди своих дочерних элементов при помощи упорядочения столбцов и строк элемента управления. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Элементы могут занимать несколько ячеек, и возможно размещение сетки внутри сетки. Сетки полезны, поскольку они позволяют создавать и позиционировать сложные [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. В следующем примере демонстрируется использование сетки для размещения нескольких кнопок и текста. Обратите внимание на то, что высоты и ширины ячейки установлено значение <xref:System.Windows.GridUnitType.Auto>; таким образом, ячейка, содержащая кнопку с изображением, изменяется в соответствии изображение.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показана сетка, созданная с помощью предыдущего кода.  
  
 ![Пример сетки](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Grid  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>Автоматическая разметка и сетки, использующие свойство IsSharedSizeScope  
 Объект <xref:System.Windows.Controls.Grid> полезен в локализуемых приложениях для создания элементов управления, чтобы вместить содержимое. Однако иногда требуется, чтобы элемент управления сохранял определенный размер, независимо от содержимого. Например, если имеются кнопки ОК, "Отмена" и "Обзор", то, возможно, не требуется выравнивать размер этих кнопок по размеру содержимого. В этом случае <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> присоединенное свойство полезно для общего использования одного размера несколькими элементами сетки. В следующем примере демонстрируется совместное использование столбцов и строк, изменение размера данных между несколькими <xref:System.Windows.Controls.Grid> элементов.  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **Примечание** полный пример кода, см. в разделе [общей папки свойств размера между сетками](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)  
  
## <a name="see-also"></a>См. также  
 [Глобализация для WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)  
 [Использование автоматической разметки для создания кнопки](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)  
 [Использование сетки для автоматической разметки](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
