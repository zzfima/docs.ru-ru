---
title: "Расширение разметки DynamicResource | Microsoft Docs"
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
  - "DynamicResource"
  - "DynamicResourceExtension"
helpviewer_keywords: 
  - "DynamicResource - расширения разметки"
  - "XAML, DynamicResource - расширение разметки"
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Расширение разметки DynamicResource
Предоставляет значение для любого атрибута свойства [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], исходя из того, что это значение будет ссылкой на уже определенный ресурс.  Механизм поиска этого ресурса аналогичен поиску во время выполнения.  
  
## Использование атрибута XAML  
  
```  
<object property="{DynamicResource key}" .../>  
```  
  
## Использование элемента свойства XAML  
  
```  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`key`|Ключ для запрашиваемого ресурса.  Этот ключ был изначально присвоен атрибутом [Директива x:Key](../../../../docs/framework/xaml-services/x-key-directive.md), если ресурс был создан в разметке, или был предоставлен в качестве параметра `key` при вызове метода <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=fullName>, если ресурс создавался в коде.|  
  
## Заметки  
 `DynamicResource` создаст временное выражение во время начальной компиляции и, таким образом, отложит поиск ресурсов до тех пор, пока значение запрошенного ресурса действительно не понадобится для создания объекта.  Потенциально это может быть после загрузки страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Значение ресурса будет найдено на основе ключа поиска по всем словарям активных ресурсов, начиная с текущей области страницы, и заменено замещающим выражением из компиляции.  
  
> [!IMPORTANT]
>  В терминах приоритета свойства зависимости, выражение `DynamicResource` эквивалентно позиции, в которой применяется динамическая ссылка на ресурс.  В случае задания локального значения для свойства, которое ранее имело в качестве локального значения выражение `DynamicResource`, `DynamicResource` полностью удаляется.  Дополнительные сведения см. в разделе [Приоритет значения свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Определенные сценарии доступа к ресурсу особенно подходят для `DynamicResource`, в отличие от [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  Обсуждение относительных достоинств и влияния `DynamicResource` и `StaticResource` на производительность см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Указанный <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> должен соответствовать существующему ресурсу, определяемому [Директива x:Key](../../../../docs/framework/xaml-services/x-key-directive.md) на некотором уровне в странице, приложении, доступных темах элементов управления, внешних или системных ресурсах; поиск ресурса будет выполняться в указанном порядке.  Дополнительные сведения о поиске ресурса для статических и динамических ресурсов см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Ключ ресурса может быть любой строкой, определенной в [Грамматика XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md).  Ключ ресурса также может быть и другим типом объекта, таким как <xref:System.Type>.  Ключ <xref:System.Type> является основой управления стилями элементов управления при помощи тем.  Дополнительные сведения см. в разделе [Общие сведения о разработке управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] для поиска значений ресурсов, например <xref:System.Windows.FrameworkElement.FindResource%2A>, следуют той же логике поиска ресурса, которая используется `DynamicResource`.  
  
 Альтернативным декларативным средством ссылки на ресурс является [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
 Синтаксис атрибута является наиболее распространенным синтаксисом, который используется с этим расширением разметки.  Лексема строки, указанная после строки идентификатора `DynamicResource`, присваивается как значение <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> базового класса расширения <xref:System.Windows.DynamicResourceExtension>.  
  
 В синтаксисе элемента объекта может использоваться `DynamicResource`.  В этом случае указание значения свойства <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> является обязательным.  
  
 Излишним может оказаться использование `DynamicResource` в атрибуте, в котором свойство <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> определено как пара «свойство\=значение».  
  
```  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными.  Поскольку `DynamicResource` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В реализации процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обработка данного расширения разметки определяется классом <xref:System.Windows.DynamicResourceExtension>.  
  
 `DynamicResource` является расширением разметки.  Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.  Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы { and } в синтаксисе их атрибутов, который является соглашением, по которому процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут.  Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## См. также  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Ресурсы и код](../../../../docs/framework/wpf/advanced/resources-and-code.md)   
 [Директива x:Key](../../../../docs/framework/xaml-services/x-key-directive.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)   
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)