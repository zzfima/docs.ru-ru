---
title: Расширение разметки ComponentResourceKey
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: 2ccc4f3154996a4e442a4092833f5c9ed9c8938a
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559465"
---
# <a name="componentresourcekey-markup-extension"></a>Расширение разметки ComponentResourceKey
Определяет и ссылается на ключи для ресурсов, загружаемых из внешних сборок. Это позволяет подстановке ресурсов указывать целевой тип в сборке, а не явный словарь ресурсов в сборке или классе.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Использование атрибута XAML (ключ Setting, компактный)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Использование атрибута XAML (параметр key, verbose)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Использование атрибута XAML (запрос ресурса, компактный)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Использование атрибута XAML (запрос ресурса, подробный)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`targetTypeName`|Имя общедоступного типа общеязыковой среды выполнения (CLR), определенного в сборке ресурсов.|  
|`targetID`|Ключ для ресурса. При поиске ресурсов `targetID` будет аналогом [директивы x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) ресурса.|  
  
## <a name="remarks"></a>Заметки  
 Как показано в описании выше, использование расширения разметки {`ComponentResourceKey`} находится в двух местах:  
  
- Определение ключа в словаре ресурсов темы, предоставленное автором элемента управления.  
  
- Доступ к ресурсу темы из сборки при пересоздании шаблона элемента управления, но необходимо использовать значения свойств, полученные из ресурсов, предоставляемых темами элемента управления.  
  
 Для ссылок на ресурсы компонентов, которые поступают из тем, обычно рекомендуется использовать `{DynamicResource}`, а не `{StaticResource}`. Это показано в использовании. рекомендуется использовать `{DynamicResource}`, так как пользователь может изменить саму тему. Если требуется, чтобы ресурс компонента, наиболее точно соответствующий намерению разработчика элемента управления, поддерживал тему, следует включить также динамическую ссылку на ресурс компонента.  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> определяет тип, существующий в целевой сборке, в которой ресурс фактически определен. `ComponentResourceKey` можно определить и использовать независимо от того, где определено <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>, но в конечном итоге необходимо разрешить тип с помощью сборок, на которые имеются ссылки.  
  
 Распространенным применением <xref:System.Windows.ComponentResourceKey> является определение ключей, которые затем предоставляются как члены класса. Для такого использования используется конструктор класса <xref:System.Windows.ComponentResourceKey>, а не расширение разметки. Дополнительные сведения см. в разделе <xref:System.Windows.ComponentResourceKey>или "определение и создание ссылок на ключи для ресурсов темы" раздела [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md)раздела.  
  
 Для установки ключей и ссылок на ресурсы с ключом синтаксис атрибутов обычно используется для расширения разметки `ComponentResourceKey`.  
  
 Приведенный синтаксис Compact основан на сигнатуре конструктора <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> и использовании позиционированного параметра для расширения разметки. Порядок, в котором задаются `targetTypeName` и `targetID`, важен. Подробный синтаксис основан на <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> конструкторе без параметров, а затем задает <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> и <xref:System.Windows.ComponentResourceKey.ResourceId%2A> способом, аналогичным синтаксису атрибута true для объектного элемента. В подробном синтаксисе порядок, в котором задаются свойства, не важен. Отношения и механизмы этих двух вариантов (компактный и подробный) более подробно описаны в разделе [расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 Технически, значение для `targetID` может быть любым объектом, оно не обязательно должно быть строкой. Однако наиболее распространенным применением в WPF является согласование `targetID` значения с формами, которые являются строками, и если такие строки допустимы в [грамматике имяxaml](../../../desktop-wpf/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey` можно использовать в синтаксисе объектного элемента. В этом случае для правильной инициализации расширения требуется указать значения свойств <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> и <xref:System.Windows.ComponentResourceKey.ResourceId%2A>.  
  
 В реализации модуля чтения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] обработка этого расширения разметки определяется классом <xref:System.Windows.ComponentResourceKey>.  
  
 `ComponentResourceKey` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md)
- [Общие сведения о языке XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
