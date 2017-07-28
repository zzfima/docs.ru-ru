---
title: "Расширение разметки TemplateBinding | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TemplateBinding"
  - "TemplateBindingExtension"
helpviewer_keywords: 
  - "TemplateBinding - расширения разметки"
  - "XAML, TemplateBinding - расширение разметки"
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Расширение разметки TemplateBinding
Связывает значение свойства в шаблоне элемента управления со значением другого свойства элемента управления\-шаблона.  
  
## Использование атрибута XAML  
  
```  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## Использование атрибута XAML \(для свойства Setter в шаблоне или стиле\)  
  
```  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`propertyName`|<xref:System.Windows.DependencyProperty.Name%2A?displayProperty=fullName> для свойства задается в синтаксисе метода задания значения.|  
|`sourceProperty`|Другое свойство зависимостей для типа, который используется в качестве шаблона, задается с помощью <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=fullName>.<br /><br /> – либо –<br /><br /> "Краткое" имя свойства, которое определяется типом, отличным от целевого шаблонного типа.  Фактически это <xref:System.Windows.PropertyPath>.  См. раздел [Синтаксис PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## Заметки  
 `TemplateBinding` является оптимизированной формой [Binding](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) для сценариев шаблонов, аналогичных расширению `Binding`, созданному с помощью `{Binding RelativeSource={RelativeSource TemplatedParent}}`.  `TemplateBinding` всегда является односторонней привязкой, даже если используемые свойства по умолчанию используют двустороннюю привязку.  Оба используемых свойства должны быть свойствами зависимостей.  
  
 [RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) является еще одним расширением разметки, которое иногда используется в сочетании с `TemplateBinding` или вместо него для выполнения относительной привязки свойства в шаблоне.  
  
 Шаблоны элементов управления в данном разделе не рассматриваются. Дополнительные сведения см. в разделе [Стили и шаблоны элемента Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.  Строковая лексема, указываемая после строки идентификатора `TemplateBinding`, присваивается в качестве значения <xref:System.Windows.TemplateBindingExtension.Property%2A> соответствующего класса расширения <xref:System.Windows.TemplateBindingExtension>.  
  
 Синтаксис элемента объекта возможен, но он не рассматривается из\-за отсутствия практического применения.  `TemplateBinding` используется для заполнения значений в методах установки значений с помощью вычисленных выражений. Использование синтаксиса элемента объекта для `TemplateBinding` для заполнения синтаксиса элемента свойства `<Setter.Property>` является излишним.  
  
 Излишним может оказаться и использование `TemplateBinding` в атрибуте, в котором свойство <xref:System.Windows.TemplateBindingExtension.Property%2A> определено как пара "свойство\=значение".  
  
```  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными.  Так как `TemplateBinding` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В реализации обработчика XAML [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обработка данного расширения разметки определяется классом <xref:System.Windows.TemplateBindingExtension>.  
  
 `TemplateBinding` является расширением разметки.  Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.  Все расширения разметки в XAML используют знаки `{` и `}` в синтаксисе их атрибутов, который является соглашением, по которому обработчик XAML узнает, что расширение разметки должно обработать атрибут.  Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## См. также  
 <xref:System.Windows.Style>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Расширение разметки RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)   
 [Привязка расширения разметки](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)