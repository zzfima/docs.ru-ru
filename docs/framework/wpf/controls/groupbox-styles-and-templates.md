---
title: Стили и шаблоны элемента GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 474cda0abc6a18c015836c749c78f4d33aa5abd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187476"
---
# <a name="groupbox-styles-and-templates"></a>Стили и шаблоны элемента GroupBox
<a name="introduction"></a>Эта тема описывает стили и <xref:System.Windows.Controls.GroupBox> шаблоны для управления. Вы можете изменить <xref:System.Windows.Controls.ControlTemplate> значение по умолчанию, чтобы придать элементу управления уникальный внешний вид. Для получения дополнительной информации [см.](../../../desktop-wpf/themes/how-to-create-apply-template.md)  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a>Части GroupBox  
 Элемент <xref:System.Windows.Controls.GroupBox> управления не имеет никаких названных частей.  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a>Государства GroupBox  
 В следующей таблице перечислены <xref:System.Windows.Controls.GroupBox> визуальные состояния для управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Допустимо|ValidationStates|Элемент управления <xref:System.Windows.Controls.Validation> использует класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> `false`прилагаемое свойство находится под контролем.|  
|InvalidFocused|ValidationStates|Прилагаемое <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> `true` свойство имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|Прикрепленное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство `true` имеет элемент управления не имеет фокуса.|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a>Пример Управления GroupBox  
 В следующем примере показано, <xref:System.Windows.Controls.GroupBox> как определить <xref:System.Windows.Controls.ControlTemplate> элемент управления.  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 Используется <xref:System.Windows.Controls.ControlTemplate> один или несколько из следующих ресурсов.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стили и шаблоны элемента управления](control-styles-and-templates.md)
- [Настройка элементов управления](control-customization.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Создание шаблона для управления](../../../desktop-wpf/themes/how-to-create-apply-template.md)
