---
title: "x:ClassModifier Directive | Microsoft Docs"
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
  - "xClassModifier"
  - "x:ClassModifier"
  - "ClassModifier"
helpviewer_keywords: 
  - "XAML [XAML Services], x:ClassModifier attribute"
  - "x:ClassModifier attribute [XAML Services]"
  - "ClassModifier attribute in XAML [XAML Services]"
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
caps.latest.revision: 22
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 21
---
# x:ClassModifier Directive
Изменяет поведение компиляции XAML, когда также предоставляется `x:Class`.  В частности, вместо создания частичного класса `class` с уровнем доступа `Public` \(по умолчанию\), предоставленный `x:Class` создается со уровнем доступа `NotPublic`.  Это поведение влияет на уровень доступа для класса в генерированных сборках.  
  
## Использование атрибута XAML  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|*NotPublic*|Точная строка, передаваемая для указания <xref:System.Reflection.TypeAttributes?displayProperty=fullName> или <xref:System.Reflection.TypeAttributes?displayProperty=fullName>, зависит от используемого языка программирования с выделенным кодом.  См. примечания.|  
  
## Зависимости  
 [x:Class](../../../docs/framework/xaml-services/x-class-directive.md) также должен быть указан в том же элементе, а этот элемент должен быть корневым элементом страницы.  Дополнительные сведения см. в разделе [\[MS\-XAML\] Раздел 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## Заметки  
 Значение `x:ClassModifier` в службах XAML на платформе .NET Framework различается в зависимости от языка программирования.  Используемая строка зависит от того, как каждый язык реализует свой <xref:System.CodeDom.Compiler.CodeDomProvider>, от преобразователей типов, возвращаемых для определения значений <xref:System.Reflection.TypeAttributes?displayProperty=fullName> и <xref:System.Reflection.TypeAttributes?displayProperty=fullName>, а также от того, учитывает язык регистр или нет.  
  
-   В [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)] передаваемой строкой для назначения <xref:System.Reflection.TypeAttributes?displayProperty=fullName> является `internal`.  
  
-   В [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)] передаваемой строкой для назначения <xref:System.Reflection.TypeAttributes?displayProperty=fullName> является `Friend`.  
  
-   Для [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)] не существует целей, поддерживающих компиляцию XAML, поэтому передаваемое значение не указано.  
  
 Можно также указать <xref:System.Reflection.TypeAttributes?displayProperty=fullName> \(`public` в [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Public` в [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]\), но указание <xref:System.Reflection.TypeAttributes?displayProperty=fullName> используется редко, так как <xref:System.Reflection.TypeAttributes?displayProperty=fullName> уже является поведением по умолчанию.  
  
 Другие значения с эквивалентными ограничениями на уровне доступа к пользовательскому коду, например `private` в [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], не относятся к `x:ClassModifier`, поскольку ссылки на вложенные классы не поддерживаются в XAML, и, таким образом, модификатор <xref:System.Reflection.TypeAttributes?displayProperty=fullName> оказывает тот же эффект.  
  
## Примечания относительно безопасности  
 Уровень доступа согласно объявлению в `x:ClassModifier` по\-прежнему должен интерпретироваться по конкретным платформам и их возможностям.  WPF включает возможности для загрузки и создания экземпляров типов, в которых `x:ClassModifier` равно `internal`, если на этот класс ссылается ресурс WPF с помощью ссылки URI типа "pack".  Вследствие этого случая \(и потенциально других подобных случаях, реализованных в других платформах\), не следует полагаться исключительно на `x:ClassModifier` для блокирования всех возможных попыток создания экземпляров.  
  
## См. также  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [Код программной части и XAML в WPF](../../../ocs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)   
 [x:FieldModifier Directive](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)   
 [Безопасность \(WPF\)](../../../ocs/framework/wpf/security-wpf.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)