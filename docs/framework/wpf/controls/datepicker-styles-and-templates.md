---
title: Стили и шаблоны элемента DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
ms.openlocfilehash: 323768b6221061d46446ab18f85555f5f7415e74
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460368"
---
# <a name="datepicker-styles-and-templates"></a>Стили и шаблоны элемента DatePicker
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.DatePicker>. Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="datepicker-parts"></a>Части DatePicker  
 В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.DatePicker>.  
  
|Отделение|Type|Описание|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|Корень элемента управления.|  
|PART_Button|<xref:System.Windows.Controls.Button>|Кнопка, которая открывает и закрывает <xref:System.Windows.Controls.Calendar>.|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|Текстовое поле, позволяющее ввести дату.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Всплывающее окно для элемента управления <xref:System.Windows.Controls.DatePicker>.|  
  
## <a name="datepicker-states"></a>Состояния DatePicker  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.DatePicker>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|Отключено.|CommonStates|<xref:System.Windows.Controls.DatePicker> отключена.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.|  
  
## <a name="datepickertextbox-parts"></a>Датепиккертекстбокс части  
 В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.  
  
|Отделение|Type|Описание|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|Элемент, содержащий начальный текст в <xref:System.Windows.Controls.DatePicker>.|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|Визуальный элемент, который может содержать <xref:System.Windows.FrameworkElement>. Текст <xref:System.Windows.Controls.TextBox> отображается в этом элементе.|  
  
## <a name="datepickertextbox-states"></a>Состояния Датепиккертекстбокс  
 В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|Отключено.|CommonStates|<xref:System.Windows.Controls.Primitives.DatePickerTextBox> отключена.|  
|MouseOver|CommonStates|Указатель мыши располагается на <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|ReadOnly|CommonStates|Пользователь не может изменить текст в <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|Водяные|ватермаркстатес|Элемент управления отображает исходный текст.  <xref:System.Windows.Controls.Primitives.DatePickerTextBox> находится в состоянии, когда пользователь не вводит текст или не выбрал дату.|  
|Неводяной знак|ватермаркстатес|Пользователь вводит текст в <xref:System.Windows.Controls.Primitives.DatePickerTextBox> или выбрал дату в <xref:System.Windows.Controls.DatePicker>.|  
|Valid|ValidationStates|Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления не имеет фокуса.|  
  
## <a name="datepicker-controltemplate-example"></a>Пример объекта ControlTemplate для DatePicker  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.DatePicker>.  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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
