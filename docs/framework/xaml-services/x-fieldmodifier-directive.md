---
title: "x:FieldModifier Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "FieldModifier attribute in XAML [XAML Services]"
  - "x:FieldModifier attribute [XAML Services]"
  - "XAML [XAML Services], x:FieldModifier attribute"
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
caps.latest.revision: 15
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 14
---
# x:FieldModifier Directive
Изменяет поведение компиляции XAML таким образом, что поля для ссылок на именованные объекты определяются с использованием доступа <xref:System.Reflection.TypeAttributes?displayProperty=fullName>, а не поведения <xref:System.Reflection.TypeAttributes?displayProperty=fullName> по умолчанию.  
  
## Использование атрибута XAML  
  
```  
<object x:FieldModifier="Public".../>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|*Открытый*|Точная строка, передаваемая для указания <xref:System.Reflection.TypeAttributes?displayProperty=fullName> или <xref:System.Reflection.TypeAttributes?displayProperty=fullName>, зависит от используемого языка программирования с выделенным кодом.  См. примечания.|  
  
## Зависимости  
 Если при создании XAML где\-либо используется `x:FieldModifier`, корневой элемент создания XAML должен объявить [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md).  
  
## Заметки  
 `x:FieldModifier` не относится к объявлению общего уровня доступа класса или его членов.  Он относится только к поведению обработки XAML, когда обрабатывается определенный объект XAML, являющийся частью обработки создания XAML, и становится объектом, который потенциально может быть доступен в графе объектов приложения.  По умолчанию ссылка на поле для такого объекта остается закрытой, что не дает потребителям элементов управления изменить граф объектов напрямую.  Вместо этого ожидается, что потребители элементов управления будут изменять граф объектов с помощью стандартных шаблонов, включенных в моделях программирования, например путем получения корня структуры, коллекций дочерних элементов, выделенных открытых свойств и т. д.  
  
 Значение атрибута `x:FieldModifier` зависит от языка программирования, а его назначение зависит от конкретной платформы.  Используемая строка зависит от того, как каждый язык реализует свой <xref:System.CodeDom.Compiler.CodeDomProvider>, от преобразователей типов, возвращаемых для определения значений <xref:System.Reflection.TypeAttributes?displayProperty=fullName> и <xref:System.Reflection.TypeAttributes?displayProperty=fullName>, а также от того, учитывает язык регистр или нет.  
  
-   В [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)] передаваемой строкой для назначения <xref:System.Reflection.TypeAttributes?displayProperty=fullName> является `public`.  
  
-   В [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)] передаваемой строкой для назначения <xref:System.Reflection.TypeAttributes?displayProperty=fullName> является `Public`.  
  
-   Для [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)] в настоящее время не существует целей для XAML, поэтому передаваемая строка не определена.  
  
 Можно также указать <xref:System.Reflection.TypeAttributes?displayProperty=fullName> \(`internal` в [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Friend` в [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]\), но указание <xref:System.Reflection.TypeAttributes?displayProperty=fullName> используется редко, так как `NotPublic` уже является поведением по умолчанию.  
  
 <xref:System.Reflection.TypeAttributes?displayProperty=fullName> является поведением по умолчанию, поскольку доступ к элементу, созданному XAML, нечасто требуется коду вне сборки, которая скомпилировала XAML.  Архитектура безопасности WPF и поведение компилирования XAML не объявляют поля, в которых открыто хранятся экземпляры элементов, если явным образом не задать свойство `x:FieldModifier` и не разрешить тем самым открытый доступ.  
  
 `x:FieldModifier` применяется только для элементов с [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md), поскольку это имя используется для ссылки на открытое поле.  
  
 По умолчанию разделяемый класс для корневого элемента является открытым, но его можно объявить закрытым с помощью [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md) также влияет на уровень доступа к экземпляру класса корневого элемента.  `x:Name` и `x:FieldModifier` можно поместить в корневой элемент, но при этом всего лишь создается открытая копия поля корневого элемента, а действительный уровень доступа класса корневого элемента по\-прежнему контролируется [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
## См. также  
 [Код XAML и пользовательские классы для WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [Код программной части и XAML в WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)   
 [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md)   
 [Построение приложения WPF](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md)