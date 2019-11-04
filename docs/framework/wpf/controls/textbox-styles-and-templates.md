---
title: Стили и шаблоны элемента TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 7c4680a3ea9352e94d628e786fc8e4fd71018d00
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458250"
---
# <a name="textbox-styles-and-templates"></a>Стили и шаблоны элемента TextBox
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.TextBox>. Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="textbox-parts"></a>Части текстового поля  
 В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.TextBox>.  
  
|Отделение|Type|Описание|  
|-|-|-|  
|PART_ContentHost|<xref:System.Windows.FrameworkElement>|Визуальный элемент, который может содержать <xref:System.Windows.FrameworkElement>. Текст <xref:System.Windows.Controls.TextBox> отображается в этом элементе.|  
  
## <a name="textbox-states"></a>Состояния текстового поля  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.TextBox>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|----------------------|---------------------------|-----------------|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен над элементом управления.|  
|Отключено.|CommonStates|Элемент управления отключен.|  
|ReadOnly|CommonStates|Пользователь не может изменить текст в <xref:System.Windows.Controls.TextBox>.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
  
## <a name="textbox-controltemplate-example"></a>Пример ControlTemplate для TextBox  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
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
