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
ms.openlocfilehash: 93735d12426042fd6517c10a55d1a9bd32f906bb
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363059"
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
|`targetTypeName`|Имя открытого [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] типа, определенного в сборке ресурса.|  
|`targetID`|Ключ для ресурса. При поиске `targetID` ресурсов они будут аналогом [директивы x:Key](../../xaml-services/x-key-directive.md) ресурса.|  
  
## <a name="remarks"></a>Примечания  
 Как показано в описании выше, использование расширения разметки {`ComponentResourceKey`} находится в двух местах:  
  
- Определение ключа в словаре ресурсов темы, предоставленное автором элемента управления.  
  
- Доступ к ресурсу темы из сборки при пересоздании шаблона элемента управления, но необходимо использовать значения свойств, полученные из ресурсов, предоставляемых темами элемента управления.  
  
 Для ссылок на ресурсы компонентов, которые поступают из тем, обычно рекомендуется использовать `{DynamicResource}` `{StaticResource}`вместо. Это показано в использовании. `{DynamicResource}`рекомендуется, поскольку пользователь может изменить саму тему. Если требуется, чтобы ресурс компонента, наиболее точно соответствующий намерению разработчика элемента управления, поддерживал тему, следует включить также динамическую ссылку на ресурс компонента.  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> Определяет тип, существующий в целевой сборке, в которой ресурс фактически определен. Можно определить и использовать независимо от того, <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> где определено, но в конечном итоге необходимо разрешить тип с помощью сборок, на которые имеются ссылки. `ComponentResourceKey`  
  
 Распространенный способ использования <xref:System.Windows.ComponentResourceKey> — определение ключей, которые затем предоставляются как члены класса. Для такого использования используется <xref:System.Windows.ComponentResourceKey> конструктор класса, а не расширение разметки. Дополнительные сведения см <xref:System.Windows.ComponentResourceKey>. в разделе или «определение и создание ссылок на ключи для ресурсов темы» раздела [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md)раздела.  
  
 Для установки ключей и ссылок на ресурсы с ключом синтаксис атрибутов обычно используется для `ComponentResourceKey` расширения разметки.  
  
 Синтаксис Compact, показанный в, зависит <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> от сигнатуры конструктора и использования позиционированного параметра для расширения разметки. Порядок, в котором `targetTypeName` задаются и `targetID` , важен. Подробный синтаксис основывается на <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> конструкторе без параметров, а затем <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> устанавливает и <xref:System.Windows.ComponentResourceKey.ResourceId%2A> таким образом, что аналогично истинному синтаксису атрибута для объектного элемента. В подробном синтаксисе порядок, в котором задаются свойства, не важен. Отношения и механизмы этих двух вариантов (компактный и подробный) более подробно описаны в разделе [расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 Технически значением `targetID` параметра может быть любой объект, а не строковый. Однако наиболее распространенным применением в WPF является согласование `targetID` значения с формами, которые являются строками, и если такие строки допустимы в [грамматике имяxaml](../../xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey`может использоваться в синтаксисе объектного элемента. В этом случае для правильной инициализации расширения требуется указать значения <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> свойств <xref:System.Windows.ComponentResourceKey.ResourceId%2A> и.  
  
 В реализации модуля чтения Обработка этого <xref:System.Windows.ComponentResourceKey> расширения разметки определяется классом. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
 `ComponentResourceKey` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md)
- [Общие сведения о языке XAML (WPF)](xaml-overview-wpf.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
