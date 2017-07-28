---
title: "Расширение разметки ComponentResourceKey | Microsoft Docs"
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
  - "ComponentResourceKey"
  - "ComponentResourceKeyExtension"
helpviewer_keywords: 
  - "ComponentResourceKey - расширение разметки"
  - "XAML, ComponentResourceKey - расширение разметки"
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Расширение разметки ComponentResourceKey
Определения и ключи ссылок ресурсов, загружаемых из внешних сборок.  Это расширение позволяет при поиске ресурса указать целевой тип в сборке, вместо явного словаря ресурса в сборке или в классе.  
  
## Использование атрибута XAML \(установка ключа, компактный\)  
  
```  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## Использование атрибута XAML \(установка ключа, подробный\)  
  
```  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## Использование атрибута XAML \(запрос ресурса, компактный\)  
  
```  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## Использование атрибута XAML \(запрос ресурса, подробный\)  
  
```  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`targetTypeName`|Имя открытого типа [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], определенного в сборке ресурсов.|  
|`targetID`|Ключ ресурса.  При поиске ресурсов код `targetID` будет аналогом атрибута [Директива x:Key](../../../../docs/framework/xaml-services/x-key-directive.md) ресурса.|  
  
## Заметки  
 Как показано выше, расширение разметки {`ComponentResourceKey`} находится в двух местах:  
  
-   Определения ключа в словаре ресурсов тем, предоставляемое автор элемента управления.  
  
-   Обращение к ресурсу темы из сборки при создании нового шаблона элемента управления, если при этом требуется использовать значения свойств из ресурсов, предоставленных темами элемента управления.  
  
 Для ссылок на ресурсы компонента, полученные из тем, обычно рекомендуется использовать `{DynamicResource}` вместо `{StaticResource}`.  Это показано в вариантах применения.  `{DynamicResource}` рекомендуется, поскольку тема сама по себе не может быть изменена пользователем.  Если требуется ресурс компонента, который наиболее точно соответствует цели автора элемента управления для поддержки темы, следует включить ссылку на ресурс компонента, чтобы он также был динамическим.  
  
 Класс <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> определяет тип, существующий в целевой сборке, в которой фактически определен ресурс.  Расширение `ComponentResourceKey` может быть определено и использовано независимо от того, где определена сборка <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>, но со временем оно должен распознать тип через сборки, на которые имеются ссылки.  
  
 Типичное использование класса <xref:System.Windows.ComponentResourceKey> заключается в определении ключей, которые затем представляются как члены класса.  Для этой сферы применения следует использовать конструктор класса <xref:System.Windows.ComponentResourceKey>, а не расширение разметки.  Дополнительные сведения см в разделе <xref:System.Windows.ComponentResourceKey> или в подразделе "Определение и содержащие ссылки ключи для ресурсов тем" раздела [Общие сведения о разработке управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Для установки ключей и ссылок на ресурсы с ключом синтаксис атрибута обычно используется для расширения разметки `ComponentResourceKey`.  
  
 Приведенный компактный синтаксис основан на сигнатуре конструктора <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=fullName> и использовании позиционных параметров расширения разметки.  Порядок, в котором перечислены `targetTypeName` и `targetID`, имеет значение.  Подробный синтаксис основан на конструкторе по умолчанию <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=fullName>. Затем устанавливаются классы <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> и <xref:System.Windows.ComponentResourceKey.ResourceId%2A> способом, который соответствует истинному синтаксису атрибута элемента объекта.  В подробном синтаксисе не важен порядок, в котором устанавливаются значения свойств.  Связь и механизмы из этих двух вариантов \(компактный и подробный синтаксис\) описаны более подробно в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 С технической точки зрения значением `targetID` может быть любой объект; это не обязательно должна быть строка.  Однако наиболее общим использованием WPF является выравнивание значения `targetID` с формами, которые представляют собой строки, и случаи, когда такие строки являются допустимыми в [Грамматика XamlName](../../../../docs/framework/xaml-services/xamlname-grammar.md).  
  
 В синтаксисе элемента объекта может использоваться `ComponentResourceKey`.  В этом случае указание значения свойств <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> и <xref:System.Windows.ComponentResourceKey.ResourceId%2A> необходимо для правильной инициализации расширения.  
  
 В реализации средства чтения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обработка данного расширения разметки определяется классом <xref:System.Windows.ComponentResourceKey>.  
  
 `ComponentResourceKey` является расширением разметки.  Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.  Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы { and } в синтаксисе их атрибутов, который является соглашением, по которому процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут.  Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## См. также  
 <xref:System.Windows.ComponentResourceKey>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Общие сведения о разработке управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)