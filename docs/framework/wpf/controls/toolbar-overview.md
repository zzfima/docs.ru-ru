---
title: Общие сведения о панели инструментов ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 0c66867ce4d86a11424d7a7a859817d603b4227e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557398"
---
# <a name="toolbar-overview"></a>Общие сведения о панели инструментов ToolBar
<xref:System.Windows.Controls.ToolBar> элементы управления являются контейнерами для группы команд или элементов управления, которые обычно связаны по функциональности. Объект <xref:System.Windows.Controls.ToolBar> обычно содержит кнопки, которые вызывают команды.  
  
  
<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>Элемент управления ToolBar  
 <xref:System.Windows.Controls.ToolBar> Управления планка как строки в одной строке или столбце ряд кнопок и других элементов управления. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> элементы управления предоставляют механизм переполнения, который помещает все элементы, не попадающие в ограничения по размеру объекта <xref:System.Windows.Controls.ToolBar> в специальную область переполнения. Кроме того [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> обычно используются элементы управления со связанным <xref:System.Windows.Controls.ToolBarTray> элемента управления, который предоставляет специальное поведение макета, а также поддержку для пользователь запустил размеры и расположение панели инструментов.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Задание положения элементов управления ToolBar в элементе управления ToolBarTray  
 Используйте <xref:System.Windows.Controls.ToolBar.Band%2A> и <xref:System.Windows.Controls.ToolBar.BandIndex%2A> свойства для размещения <xref:System.Windows.Controls.ToolBar> в <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.Band%2A> указывает положение, где <xref:System.Windows.Controls.ToolBar> помещается в его родительском элементе <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.BandIndex%2A> Указывает порядок, в котором <xref:System.Windows.Controls.ToolBar> помещается расположения элементов. В следующем примере показан как данное свойство используется для размещения <xref:System.Windows.Controls.ToolBar> элементы управления внутри <xref:System.Windows.Controls.ToolBarTray>.  
  
 [!code-xaml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>Элементы управления ToolBar с элементами в области переполнения  
 Часто <xref:System.Windows.Controls.ToolBar> элементов управления содержит больше элементов, чем может поместиться в размер панели инструментов. В этом случае <xref:System.Windows.Controls.ToolBar> отображает кнопки переполнения. Для просмотра элементов переполнения, пользователь нажимает кнопку переполнения, и элементы отображаются во всплывающем окне ниже <xref:System.Windows.Controls.ToolBar>. Показано на следующем рисунке <xref:System.Windows.Controls.ToolBar> с элементами в области переполнения.  
  
 ![Панель инструментов с перекрытием](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")  
Панель инструментов с элементами в области переполнения  
  
 Можно указать при помещении элемент на панели инструментов на панели переполнения, задав <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> присоединенному свойству <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>, или <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>. В следующем примере показано, что последние четыре кнопки панели инструментов всегда должны быть в области переполнения.  
  
 [!code-xaml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 <xref:System.Windows.Controls.ToolBar> Использует <xref:System.Windows.Controls.Primitives.ToolBarPanel> и <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> в его <xref:System.Windows.Controls.ControlTemplate>.  <xref:System.Windows.Controls.Primitives.ToolBarPanel> Отвечает за размещение элементов на панели инструментов.  <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> Отвечает за макета элементов, которые не помещаются на <xref:System.Windows.Controls.ToolBar>. Пример <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ToolBar>, см.  
  
 [Стили и шаблоны элемента ToolBar](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
 [Определение стиля элементов управления на панели инструментов](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)  
 [Пример коллекции элементов управления WPF](http://go.microsoft.com/fwlink/?LinkID=160053)
