---
title: Стили и шаблоны элемента ProgressBar
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 3a1bea39ba9b6d2cff9937a3fee1d1de41daf16b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459880"
---
# <a name="progressbar-styles-and-templates"></a>Стили и шаблоны элемента ProgressBar
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ProgressBar>. Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="progressbar-parts"></a>Части ProgressBar  
 В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.ProgressBar>.  
  
|Отделение|Type|Описание|  
|-|-|-|  
|PART_Indicator|<xref:System.Windows.FrameworkElement>|Объект, указывающий ход выполнения.|  
|PART_Track|<xref:System.Windows.FrameworkElement>|Объект, определяющий путь индикатора хода выполнения.|  
|PART_GlowRect|<xref:System.Windows.FrameworkElement>|Объект, надстрочные индикатор выполнения.|  
  
## <a name="progressbar-states"></a>Состояния ProgressBar  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.ProgressBar>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|----------------------|---------------------------|-----------------|  
|Завершение работы|CommonStates|<xref:System.Windows.Controls.ProgressBar> отчет о ходе выполнения на основе свойства <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.|  
|Неопределенному|CommonStates|<xref:System.Windows.Controls.ProgressBar> сообщает об общем ходе выполнения с повторяющимся шаблоном.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
  
## <a name="progressbar-controltemplate-example"></a>Пример объекта ControlTemplate для элемента ProgressBar  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ProgressBar>.  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
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
