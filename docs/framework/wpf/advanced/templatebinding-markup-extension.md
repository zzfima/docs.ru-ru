---
title: Расширение разметки TemplateBinding
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: 6d89978b907c8f124b5162c97de5edc034cf1e95
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976674"
---
# <a name="templatebinding-markup-extension"></a>Расширение разметки TemplateBinding
Связывает значение свойства в шаблоне элемента управления со значением другого свойства элемента управления-шаблона.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a>Использование атрибута XAML (для свойства Setter в шаблоне или стиле)  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`propertyName`|<xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> для свойства задается в синтаксисе метода задания значения.|  
|`sourceProperty`|Другое свойство зависимостей для типа, который используется в качестве шаблона, задается с помощью <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.<br /><br /> -или-<br /><br /> "Краткое" имя свойства, которое определяется типом, отличным от целевого шаблонного типа. Фактически это <xref:System.Windows.PropertyPath>. См. раздел [синтаксис языка XAML PropertyPath](propertypath-xaml-syntax.md).|  
  
## <a name="remarks"></a>Заметки  
 `TemplateBinding` — это оптимизированная форма [привязки](binding-markup-extension.md) для сценариев шаблонов, аналогичная `Binding`, созданной с помощью `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`. `TemplateBinding` всегда является односторонней привязкой, даже если используемые свойства по умолчанию используют двустороннюю привязку. Оба используемых свойства должны быть свойствами зависимостей. Чтобы обеспечить двустороннюю привязку к шаблонному родителю, вместо этого используйте следующую инструкцию привязки `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`. 
  
 [RelativeSource](relativesource-markupextension.md) — это еще одно расширение разметки, которое иногда используется вместе с или вместо `TemplateBinding` для выполнения относительной привязки свойства в шаблоне.  
  
 Описание шаблонов элементов управления в качестве концепции не рассматривается здесь. Дополнительные сведения см. в разделе [стили и шаблоны элемента управления](../controls/control-styles-and-templates.md).  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `TemplateBinding`, присваивается в качестве значения <xref:System.Windows.TemplateBindingExtension.Property%2A> соответствующего класса расширения <xref:System.Windows.TemplateBindingExtension>.  
  
 Синтаксис элемента объекта возможен, но он не рассматривается из-за отсутствия практического применения. `TemplateBinding` используется для заполнения значений в методах установки значений с помощью вычисленных выражений. Использование синтаксиса элемента объекта для `TemplateBinding` для заполнения синтаксиса элемента свойства `<Setter.Property>` является излишним.  
  
 Излишним может оказаться и использование `TemplateBinding` в атрибуте, в котором свойство <xref:System.Windows.TemplateBindingExtension.Property%2A> определено как пара "свойство=значение".  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными. Так как `TemplateBinding` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализации процессора XAML обработка этого расширения разметки определяется классом <xref:System.Windows.TemplateBindingExtension>.  
  
 `TemplateBinding` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в XAML используют `{` и `}` символов в синтаксисе атрибутов, который является соглашением, по которому обработчик XAML распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стилизация и использование шаблонов](../controls/styling-and-templating.md)
- [Общие сведения о языке XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Расширение разметки RelativeSource](relativesource-markupextension.md)
- [Привязка расширения разметки](binding-markup-extension.md)
