---
title: Расширение разметки DynamicResource
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: 63cac0bcca0d9ce8e9f69aa8c9986cb5fa597a56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590349"
---
# <a name="dynamicresource-markup-extension"></a>Расширение разметки DynamicResource
Предоставляет значение для любого [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] свойства атрибута, отложенной до был ссылкой на определенный ресурс. Поведение подстановки для этого ресурса является аналогом во время выполнения.  
  
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
|`key`|Ключ для запрашиваемого ресурса. Этот ключ была изначально назначена по [директивы x: Key](../../../../docs/framework/xaml-services/x-key-directive.md) Если ресурс был создан в разметке или был предоставлен в виде `key` параметра при вызове <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> Если ресурс был создан в коде.|  
  
## <a name="remarks"></a>Примечания  
 Объект `DynamicResource` создаст временное выражение во время первоначальной компиляции и таким образом, отложит для ресурсов, пока значение запрошенного ресурса не нужен для создания объекта. Потенциально это может быть после [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] загрузки страницы. Значение ресурса будет находиться на основе ключа поиска для всех словарей ресурсов active, начиная с текущей области страницы и заменяется выражением заполнитель из компиляции.  
  
> [!IMPORTANT]
>  С точки зрения приоритет свойств зависимостей `DynamicResource` выражение эквивалентно позицию, где применяется ссылка на динамический ресурс. Если вы задано локальное значение для свойства, которое ранее было `DynamicResource` выражение в качестве локального значения `DynamicResource` полностью удаляется. Дополнительные сведения см. в разделе [Приоритет значений свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Особенно подходит для определенных сценариев доступа к ресурсу `DynamicResource` в отличие от [расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md). См. в разделе [ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) обсуждение относительных достоинствах и последствия для производительности `DynamicResource` и `StaticResource`.  
  
 Указанный <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> должен соответствовать существующего ресурса определяется [директивы x: Key](../../../../docs/framework/xaml-services/x-key-directive.md) на определенном уровне страницы, приложения, доступный элемент управления темы и внешним ресурсам или системных ресурсов и Поиск ресурсов будет происходить в указанном порядке. Дополнительные сведения о поиске ресурсов для статических и динамических ресурсов, см. в разделе [ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Ключ ресурса может быть любой строкой, определенные в [Грамматика XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md). Ключ ресурса также может быть других типов объектов, например <xref:System.Type>. Объект <xref:System.Type> ключ — это основа для как можно применить различные стили элементов управления темы. Дополнительные сведения см. в разделе [Общие сведения о разработке элементов управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] для поиска значений ресурсов таких как <xref:System.Windows.FrameworkElement.FindResource%2A>, выполните ту же логику поиска ресурсов, используемой средой `DynamicResource`.  
  
 Декларативные альтернативные методы ссылкой на ресурс — как [расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `DynamicResource`, присваивается в качестве значения <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> соответствующего класса расширения <xref:System.Windows.DynamicResourceExtension>.  
  
 `DynamicResource` может использоваться в синтаксисе элемента объекта. В этом случае укажите значение параметра <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> свойство является обязательным.  
  
 Излишним может оказаться и использование `DynamicResource` в атрибуте, в котором свойство <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> определено как пара "свойство=значение".  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными. Так как `DynamicResource` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализации обработчика обработка данного расширения разметки определяется <xref:System.Windows.DynamicResourceExtension> класса.  
  
 `DynamicResource` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также
- [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [Ресурсы и код](../../../../docs/framework/wpf/advanced/resources-and-code.md)
- [Директива x:Key](../../../../docs/framework/xaml-services/x-key-directive.md)
- [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)
- [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
