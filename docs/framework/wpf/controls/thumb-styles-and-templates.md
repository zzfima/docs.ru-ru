---
title: Стили и шаблоны элемента Thumb
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: 0d0d88e3b527beacfa5f879027e696aa75b18147
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283684"
---
# <a name="thumb-styles-and-templates"></a>Стили и шаблоны элемента Thumb

В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Primitives.Thumb>. Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления. Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).

## <a name="thumb-parts"></a>Элементы Thumb

Элемент управления <xref:System.Windows.Controls.Primitives.Thumb> не имеет именованных частей.

## <a name="thumb-states"></a>Состояния Thumb

В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.Thumb>.

|Имя VisualState|Имя VisualStateGroup|Описание|
|-|-|-|
|Норм.|CommonStates|Состояние по умолчанию.|
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|
|Нажато|CommonStates|Элемент управления нажат.|
|Отключено.|CommonStates|Элемент управления отключен.|
|Focused|FocusStates|Элемент управления имеет фокус.|
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|

## <a name="thumb-controltemplate-example"></a>Пример Thumb ControlTemplate

В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Primitives.Thumb>.

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

В предыдущем примере используется один или несколько из следующих ресурсов.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="see-also"></a>См. также

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стили и шаблоны элемента управления](control-styles-and-templates.md)
- [Настройка элементов управления](control-customization.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md)
