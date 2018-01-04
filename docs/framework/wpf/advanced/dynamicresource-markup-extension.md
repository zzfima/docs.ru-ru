---
title: "Расширение разметки DynamicResource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f6c8500f9b9cd6d617789a2da3444519971ae81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="dynamicresource-markup-extension"></a>Расширение разметки DynamicResource
Предоставляет значение для любого [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] атрибут property, отложенной должен указывать определенный ресурс. Поведение подстановки для этого ресурса является аналогом во время выполнения.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>Использование элемента свойства XAML  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`key`|Ключ для запрашиваемого ресурса. Этот ключ был изначально присвоенный [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md) Если ресурс был создан в разметке или был предоставлен в виде `key` параметра при вызове <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> Если ресурс был создан в коде.|  
  
## <a name="remarks"></a>Примечания  
 Объект `DynamicResource` создаст временное выражение во время начальной компиляции и таким образом, отложит для ресурсов, пока значение запрошенного ресурса фактически требуется для создания объекта. Потенциально это может быть после [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] загрузки страницы. Значение ресурса будет найдено на основе ключа поиска по всем словарям активных ресурсов, начиная с текущей области страницы и заменяется замещающим выражением из компиляции.  
  
> [!IMPORTANT]
>  С точки зрения приоритета свойств зависимостей `DynamicResource` выражение эквивалентно позиции, где применяется ссылка на динамический ресурс. Если вы установите локальное значение для свойства, которое ранее было `DynamicResource` выражение в качестве локального значения `DynamicResource` полностью удаляется. Дополнительные сведения см. в разделе [Приоритет значений свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Для некоторых сценариев доступа к ресурсу особенно подходят `DynamicResource` в отличие от [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md). В разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) обсуждение относительный плюсы и влияние на производительность `DynamicResource` и `StaticResource`.  
  
 Указанный <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> должны соответствовать существующий ресурс определяется [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md) на некотором уровне в страницу, приложения, доступный элемент управления темы и внешние ресурсы или системных ресурсов и Поиск ресурсов будет происходить в указанном порядке. Дополнительные сведения о поиске ресурса для статических и динамических ресурсов см. в разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Ключ ресурса может быть любая строка, определенная в [Грамматика XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md). Ключ ресурса может также быть другие типы объектов, например <xref:System.Type>. Объект <xref:System.Type> ключ — это основа стилями элементов управления темы. Дополнительные сведения см. в разделе [Общие сведения о разработке элементов управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]для поиска значений ресурсов таких как <xref:System.Windows.FrameworkElement.FindResource%2A>, выполните ту же логику поиска ресурсов, используемый в `DynamicResource`.  
  
 — Альтернативный декларативным образом ссылки на ресурс в виде [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `DynamicResource`, присваивается в качестве значения <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> соответствующего класса расширения <xref:System.Windows.DynamicResourceExtension>.  
  
 `DynamicResource`может использоваться в синтаксисе элемента объекта. В этом случае укажите значение параметра <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> свойство является обязательным.  
  
 Излишним может оказаться и использование `DynamicResource` в атрибуте, в котором свойство <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> определено как пара "свойство=значение".  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными. Так как `DynamicResource` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализации процессора обработки для данного расширения разметки определяется <xref:System.Windows.DynamicResourceExtension> класса.  
  
 `DynamicResource` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Ресурсы и код](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [Директива x:Key](../../../../docs/framework/xaml-services/x-key-directive.md)  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
