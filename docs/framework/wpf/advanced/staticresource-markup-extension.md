---
title: "Расширение разметки StaticResource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 821cd152ccb7a02dda5338d6a3ec44d6625c0097
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="staticresource-markup-extension"></a>Расширение разметки StaticResource
Предоставляет значение для любого [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] атрибут свойства путем поиска ссылки на уже определенный ресурс. Поведение подстановки для этого ресурса является аналогом Уточняющий запрос во время загрузки, который будет искать ресурсы, которые были ранее загружены из разметки текущего [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы, а также других источников приложения и автоматически создаст как значение ресурса значение свойства в объектах во время выполнения.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`key`|Ключ для запрашиваемого ресурса. Этот ключ был изначально присвоенный [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md) Если ресурс был создан в разметке или был предоставлен в виде `key` параметра при вызове <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> Если ресурс был создан в коде.|  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
>  Объект `StaticResource` не должен пытаться сделать прямую ссылку на ресурс, который определен лексически далее в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла. Попытка сделать это не поддерживается, и даже если эта ссылка не завершается ошибкой, попытка прямой ссылки повлечет за собой снижение производительности во время загрузки при внутренней хэш-таблиц, представляющих <xref:System.Windows.ResourceDictionary> производится поиск. Для получения наилучших результатов настройте композицию словарей ресурсов таким образом, можно избежать прямых ссылок. Если не удается избежать прямая ссылка, используйте [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) вместо него.  
  
 Указанный <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> должны соответствовать существующий ресурс, определенный с [директива x: Key](../../../../docs/framework/xaml-services/x-key-directive.md) на некотором уровне в страницу, приложения, доступный элемент управления темы и внешние ресурсы или системных ресурсов. Поиск ресурсов происходит в указанном порядке. Дополнительные сведения о поведении подстановки ресурсов для статических и динамических ресурсов см. в разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Ключ ресурса может быть любая строка, определенная в [Грамматика XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md). Ключ ресурса может также быть другие типы объектов, например <xref:System.Type>. Объект <xref:System.Type> ключ — это основа для элементов управления можно стилями темы, через ключ неявный стиль. Дополнительные сведения см. в разделе [Общие сведения о разработке элементов управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 — Альтернативный декларативным образом ссылки на ресурс в виде [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `StaticResource`, присваивается в качестве значения <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> соответствующего класса расширения <xref:System.Windows.StaticResourceExtension>.  
  
 `StaticResource`может использоваться в синтаксисе элемента объекта. В этом случае укажите значение параметра <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> свойство является обязательным.  
  
 Излишним может оказаться и использование `StaticResource` в атрибуте, в котором свойство <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> определено как пара "свойство=значение".  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными. Так как `StaticResource` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализации процессора обработки для данного расширения разметки определяется <xref:System.Windows.StaticResourceExtension> класса.  
  
 `StaticResource` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Ресурсы и код](../../../../docs/framework/wpf/advanced/resources-and-code.md)
