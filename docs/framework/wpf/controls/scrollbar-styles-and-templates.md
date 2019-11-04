---
title: Стили и шаблоны элемента ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: f30a0abb3e4252737e513b531b8d5f49a0d47f0b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458442"
---
# <a name="scrollbar-styles-and-templates"></a>Стили и шаблоны элемента ScrollBar
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>. Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="scrollbar-parts"></a>Элементы полосы прокрутки  
 В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
|Отделение|Type|Описание|  
|-|-|-|  
|PART_Track|<xref:System.Windows.Controls.Primitives.Track>|Контейнер для элемента, указывающий расположение <xref:System.Windows.Controls.Primitives.ScrollBar>.|  
  
## <a name="scrollbar-states"></a>Состояния полосы прокрутки  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|----------------------|---------------------------|-----------------|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен над элементом управления.|  
|Отключено.|CommonStates|Элемент управления отключен.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления не имеет фокуса.|  
  
## <a name="scrollbar-controltemplate-example"></a>Пример элемента ControlTemplate для элемента управления ScrollBar  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 В предыдущем примере используется один или несколько из следующих ресурсов.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стили и шаблоны элемента управления](control-styles-and-templates.md)
- [Настройка элементов управления](control-customization.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
