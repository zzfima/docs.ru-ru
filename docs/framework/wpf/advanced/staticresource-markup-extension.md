---
title: "Расширение разметки StaticResource | Microsoft Docs"
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
  - "StaticResource"
  - "StaticResourceExtension"
helpviewer_keywords: 
  - "StaticResource - расширения разметки"
  - "XAML, StaticResource - расширение разметки"
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Расширение разметки StaticResource
Предоставляет значение для любого атрибута свойства [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] путем поиска ссылки на уже определенный ресурс.  Поведение подстановки для этого ресурса является аналогом подстановки во время загрузки, которая будет осуществлять поиск ресурсов, ранее загруженных из разметки текущей страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и из других источников приложения, и выдаст значение ресурса в качестве значения свойства в объектах во время выполнения.  
  
## Использование атрибута XAML  
  
```  
<object property="{StaticResource key}" .../>  
```  
  
## Использование элемента объекта XAML  
  
```  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`key`|Ключ для запрашиваемого ресурса.  Этот ключ был изначально присвоен атрибутом [Директива x:Key](../../../../docs/framework/xaml-services/x-key-directive.md), если ресурс был создан в разметке, или был предоставлен в качестве параметра `key` при вызове метода <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=fullName>, если ресурс создавался в коде.|  
  
## Заметки  
  
> [!IMPORTANT]
>  `StaticResource` не должен пытаться сделать прямую ссылку на ресурс, который определен лексически далее в файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Попытки выполнить это не поддерживаются, и даже в том случае, если такая ссылка не привела к неудаче, попытка прямой ссылки будет вызывать снижение производительности во время загрузки, когда производится поиск внутренних хэш\-таблиц, представляющих <xref:System.Windows.ResourceDictionary>.  Для достижения наилучших результатов настройте композицию словарей ресурсов таким образом, чтобы можно было избежать прямых ссылок.  Если не удается избежать прямых ссылок, используйте расширение разметки [Расширение разметки DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
 Указанное свойство <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> должно соответствовать существующему ресурсу, идентифицированному с [Директива x:Key](../../../../docs/framework/xaml-services/x-key-directive.md) на некотором уровне в странице, приложении, доступных темах элементов управления и внешних или системных ресурсах.  Подстановка ресурса происходит в таком порядке.  Дополнительные сведения о поведении подстановки ресурсов для статических и динамических ресурсов см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Ключ ресурса может быть любой строкой, определенной в [Грамматика XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md).  Ключ ресурса может также быть и другим типом объекта, например, <xref:System.Type>.  Ключ <xref:System.Type> является основой управления стилями элементов управления с помощью тем, являясь неявным ключом стиля.  Дополнительные сведения см. в разделе [Общие сведения о разработке управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Альтернативным декларативным средством ссылки на ресурс является [Расширение разметки DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
 Синтаксис атрибута является наиболее распространенным синтаксисом, который используется с этим расширением разметки.  Лексема строки, указанная после строки идентификатора `StaticResource`, присваивается как значение <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> базового класса расширения <xref:System.Windows.StaticResourceExtension>.  
  
 В синтаксисе элемента объекта может использоваться `StaticResource`.  В этом случае указание значения свойства <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> является обязательным.  
  
 Излишним может оказаться использование `StaticResource` в атрибуте, в котором свойство <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> определено как пара «свойство\=значение».  
  
```  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными.  Поскольку `StaticResource` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.  
  
 В реализации процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обработка данного расширения разметки определяется классом <xref:System.Windows.StaticResourceExtension>.  
  
 `StaticResource` является расширением разметки.  Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.  Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы { and } в синтаксисе их атрибутов, который является соглашением, по которому процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут.  Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## См. также  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Ресурсы и код](../../../../docs/framework/wpf/advanced/resources-and-code.md)