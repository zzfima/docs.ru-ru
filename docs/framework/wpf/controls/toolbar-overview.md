---
title: Общие сведения о панели инструментов ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 460d4420d5faf849a8d05a94e0170aea384f69b4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452699"
---
# <a name="toolbar-overview"></a>Общие сведения о панели инструментов ToolBar
<xref:System.Windows.Controls.ToolBar> элементы управления — это контейнеры для группы команд или элементов управления, которые обычно связаны в их функции. <xref:System.Windows.Controls.ToolBar> обычно содержит кнопки, которые вызывают команды.  

<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>Элемент управления ToolBar  
 Элемент управления <xref:System.Windows.Controls.ToolBar> принимает свое имя из линейного расположения кнопок или других элементов управления в одну строку или столбец. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> элементы управления предоставляют механизм переполнения, который помещает все элементы, которые не соответствуют естественному размеру, в <xref:System.Windows.Controls.ToolBar> в специальную область переполнения. Кроме того, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементы управления <xref:System.Windows.Controls.ToolBar> обычно используются с соответствующим элементом управления <xref:System.Windows.Controls.ToolBarTray>, который обеспечивает специальное поведение макета, а также поддержку пользовательского изменения размеров и расположения панелей инструментов.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Задание положения элементов управления ToolBar в элементе управления ToolBarTray  
 Используйте свойства <xref:System.Windows.Controls.ToolBar.Band%2A> и <xref:System.Windows.Controls.ToolBar.BandIndex%2A>, чтобы разместить <xref:System.Windows.Controls.ToolBar> в <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.Band%2A> указывает расположение, в котором <xref:System.Windows.Controls.ToolBar> помещается в родительский <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.BandIndex%2A> указывает порядок, в котором <xref:System.Windows.Controls.ToolBar> помещается в полосу. В следующем примере показано, как использовать это свойство для размещения <xref:System.Windows.Controls.ToolBar> элементов управления внутри <xref:System.Windows.Controls.ToolBarTray>.  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>Элементы управления ToolBar с элементами в области переполнения  
 Часто <xref:System.Windows.Controls.ToolBar> элементы управления содержат больше элементов, чем может уместиться в размерах панели инструментов. В этом случае <xref:System.Windows.Controls.ToolBar> отображает кнопку переполнения. Чтобы увидеть элементы переполнения, пользователь нажимает кнопку переполнения, и элементы отображаются во всплывающем окне под <xref:System.Windows.Controls.ToolBar>. На следующем рисунке показана <xref:System.Windows.Controls.ToolBar> с элементами переполнения:  
  
 ![Снимок экрана, на котором показана панель инструментов с элементами переполнения.](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 Можно указать, когда элемент на панели инструментов помещается на панель переполнения, установив для присоединенного свойства <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> значение <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>или <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>. В следующем примере показано, что последние четыре кнопки панели инструментов всегда должны быть в области переполнения.  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 <xref:System.Windows.Controls.ToolBar> использует <xref:System.Windows.Controls.Primitives.ToolBarPanel> и <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> в своем <xref:System.Windows.Controls.ControlTemplate>.  <xref:System.Windows.Controls.Primitives.ToolBarPanel> отвечает за размещение элементов на панели инструментов.  <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> отвечает за размещение элементов, которые не помещаются на <xref:System.Windows.Controls.ToolBar>. Пример <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ToolBar>см. в разделе  
  
 [Стили и шаблоны элемента ToolBar](toolbar-styles-and-templates.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [Определение стиля элементов управления на панели инструментов](how-to-style-controls-on-a-toolbar.md)
- [Пример коллекции элементов управления WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
