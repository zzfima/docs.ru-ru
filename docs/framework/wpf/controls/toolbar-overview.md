---
title: Общие сведения о панели инструментов ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: b5498b8b88c7403ffe51256a57544261de3ace08
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186614"
---
# <a name="toolbar-overview"></a>Общие сведения о панели инструментов ToolBar
<xref:System.Windows.Controls.ToolBar>элементы управления являются контейнерами для группы команд или элементов управления, которые обычно связаны в их функции. Обычно <xref:System.Windows.Controls.ToolBar> содержит кнопки, которые вызывают команды.  

<a name="ToolBarControl"></a>
## <a name="toolbar-control"></a>Элемент управления ToolBar  
 Элемент <xref:System.Windows.Controls.ToolBar> управления берет свое название от бароподобного расположения кнопок или других элементов управления в одну строку или столбец. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.ToolBar> элементы управления обеспечивают механизм переполнения, который помещает любые элементы, которые не вписываются естественно в пределах ограниченного <xref:System.Windows.Controls.ToolBar> размера, в специальную область переполнения. Кроме [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> того, элементы управления <xref:System.Windows.Controls.ToolBarTray> обычно используются с соответствующим элементом управления, который обеспечивает специальное поведение макета, а также поддержку инициированных пользователем размеров и организации панели инструментов.  
  
<a name="Creating_ToolBars"></a>
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Задание положения элементов управления ToolBar в элементе управления ToolBarTray  
 Используйте <xref:System.Windows.Controls.ToolBar.Band%2A> <xref:System.Windows.Controls.ToolBar.BandIndex%2A> и свойства, <xref:System.Windows.Controls.ToolBar> чтобы <xref:System.Windows.Controls.ToolBarTray>позиционировать в . <xref:System.Windows.Controls.ToolBar.Band%2A>указывает положение, в <xref:System.Windows.Controls.ToolBar> котором находится <xref:System.Windows.Controls.ToolBarTray>в пределах родительского. <xref:System.Windows.Controls.ToolBar.BandIndex%2A>указывает порядок, <xref:System.Windows.Controls.ToolBar> в котором находится внутри его полосы. Ниже приводится следующий <xref:System.Windows.Controls.ToolBar> <xref:System.Windows.Controls.ToolBarTray>пример, как использовать это свойство для размещения элементов управления внутри .  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>
## <a name="toolbars-with-overflow-items"></a>Элементы управления ToolBar с элементами в области переполнения  
 Часто <xref:System.Windows.Controls.ToolBar> элементы управления содержат больше элементов, чем может вписаться в размер панели инструментов. Когда это происходит, отображается кнопка <xref:System.Windows.Controls.ToolBar> переполнения. Чтобы увидеть элементы переполнения, пользователь нажимает кнопку переполнения, и <xref:System.Windows.Controls.ToolBar>элементы отображаются во всплывающем окне под . На следующем графике показаны <xref:System.Windows.Controls.ToolBar> элементы переполнения:  
  
 ![Скриншот, на который отображается панель инструментов с элементами переполнения.](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 Вы можете указать, когда элемент на панели инструментов помещается на панель переполнения, установив <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> прилагаемое свойство <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>к, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>или <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>. В следующем примере показано, что последние четыре кнопки панели инструментов всегда должны быть в области переполнения.  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 <xref:System.Windows.Controls.ToolBar> Использует a <xref:System.Windows.Controls.Primitives.ToolBarPanel> и <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> a <xref:System.Windows.Controls.ControlTemplate>в своем .  Отвечает <xref:System.Windows.Controls.Primitives.ToolBarPanel> за расположение элементов на панели инструментов.  Отвечает <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> за расположение элементов, которые не подходят <xref:System.Windows.Controls.ToolBar>на . Для примера <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ToolBar>для, см.  
  
 [Стили и шаблоны ToolBar](toolbar-styles-and-templates.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [Определение стиля элементов управления на панели инструментов](how-to-style-controls-on-a-toolbar.md)
- [Пример коллекции элементов управления WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
