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
ms.openlocfilehash: a04e1569f77fed73a480fda3d63cabf6dbc30664
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460517"
---
# <a name="dynamicresource-markup-extension"></a>Расширение разметки DynamicResource
Предоставляет значение для любого атрибута свойства [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], откладывая это значение как ссылку на определенный ресурс. Поведение поиска для этого ресурса аналогично поиску во время выполнения.  
  
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
|`key`|Ключ для запрашиваемого ресурса. Этот ключ изначально был назначен [директивой x:Key](../../xaml-services/x-key-directive.md) , если ресурс был создан в разметке, или был предоставлен в качестве параметра `key` при вызове <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>, если ресурс был создан в коде.|  
  
## <a name="remarks"></a>Заметки  
 `DynamicResource` создаст временное выражение во время начальной компиляции и, таким же, откладывает Поиск ресурсов до тех пор, пока запрошенное значение ресурса не будет действительно необходимо для создания объекта. Это потенциально может быть после загрузки страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Значение ресурса будет найдено на основе поиска по ключу для всех активных словарей ресурсов, начиная с текущей области страницы, и заменяется на выражение заполнителя из компиляции.  
  
> [!IMPORTANT]
> В плане приоритета свойства зависимости `DynamicResource` выражение эквивалентно положению, в котором применяется ссылка на динамический ресурс. Если задать локальное значение для свойства, которое ранее имело `DynamicResource`ное выражение в качестве локального значения, `DynamicResource` будет полностью удалена. Дополнительные сведения см. в разделе [Приоритет значений свойств зависимостей](dependency-property-value-precedence.md).  
  
 Некоторые сценарии доступа к ресурсам особенно подходят для `DynamicResource`, а не [расширения разметки StaticResource](staticresource-markup-extension.md). Сведения о относительных показателях и влиянии `DynamicResource` и `StaticResource`см. в статье [ресурсы XAML](xaml-resources.md) .  
  
 Указанный <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> должен соответствовать существующему ресурсу, определяемому [директивой x:Key](../../xaml-services/x-key-directive.md) на определенном уровне на странице, приложении, доступных темах элементов управления, внешних ресурсах или системных ресурсах, а поиск ресурсов произойдет в Этот порядок. Дополнительные сведения о поиске ресурсов для статических и динамических ресурсов см. в разделе [ресурсы XAML](xaml-resources.md).  
  
 Ключ ресурса может быть любой строкой, определенной в [грамматике имяxaml](../../xaml-services/xamlname-grammar.md). Ключ ресурса также может быть другими типами объектов, например <xref:System.Type>. <xref:System.Type> ключом является фундаментальный способ стиля элементов управления с помощью тем. Дополнительные сведения см. в разделе [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md).  
  
 API для поиска значений ресурсов, таких как <xref:System.Windows.FrameworkElement.FindResource%2A>, следуют той же логике поиска ресурсов, которая используется `DynamicResource`.  
  
 Альтернативные декларативные средства для ссылки на ресурс — это [расширение разметки StaticResource](staticresource-markup-extension.md).  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `DynamicResource`, присваивается в качестве значения <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> соответствующего класса расширения <xref:System.Windows.DynamicResourceExtension>.  
  
 `DynamicResource` можно использовать в синтаксисе объектного элемента. В этом случае необходимо указать значение свойства <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>.  
  
 Излишним может оказаться и использование `DynamicResource` в атрибуте, в котором свойство <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> определено как пара "свойство=значение".  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными. Так как `DynamicResource` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В реализации процессора [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] обработка этого расширения разметки определяется классом <xref:System.Windows.DynamicResourceExtension>.  
  
 `DynamicResource` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также

- [Ресурсы XAML](xaml-resources.md)
- [Ресурсы и код](resources-and-code.md)
- [Директива x:Key](../../xaml-services/x-key-directive.md)
- [Общие сведения о языке XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Расширение разметки StaticResource](staticresource-markup-extension.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
