---
title: "x:Type Markup Extension | Microsoft Docs"
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
  - "x:TypeExtension"
  - "Type"
  - "x:Type"
  - "xType"
  - "TypeExtension"
helpviewer_keywords: 
  - "x:Type markup extension [XAML Services]"
  - "XAML [XAML Services], x:Type markup extension"
  - "XAML [XAML Services], TargetType attribute"
  - "TargetType attribute [XAML Services]"
  - "Type markup extension in XAML [XAML Services]"
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
caps.latest.revision: 27
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 27
---
# x:Type Markup Extension
Предоставляет объект <xref:System.Type> среды CLR, который является базовым типом для указанного типа XAML.  
  
## Использование атрибута XAML  
  
```  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## Использование элемента объекта XAML  
  
```  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`prefix`|Необязательный.  Префикс, который сопоставляет пространство имен XML, не являющееся пространством имен по умолчанию.  Указание префикса зачастую необязательно.  См. примечания.|  
|`typeNameValue`|Обязательный.  Имя типа, которое разрешается в текущее пространство имен XAML по умолчанию или в указанный сопоставленный префикс, если предоставляется `prefix`.|  
  
## Заметки  
 Расширение разметки `x:Type` имеет функцию, аналогичную оператору `typeof()` в [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] или оператору `GetType` в [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)].  
  
 Расширение разметки `x:Type` выполняет преобразование из строки для свойств, принимающих тип <xref:System.Type>.  На входе используется тип XAML.  Связь между типом входных данных XAML и <xref:System.Type> вывода CLR заключается в том, что выходные данные <xref:System.Type> являются свойством <xref:System.Xaml.XamlType.UnderlyingType%2A> входного <xref:System.Xaml.XamlType>, после поиска необходимых <xref:System.Xaml.XamlType> на основе контекста схемы XAML и службы <xref:System.Windows.Markup.IXamlTypeResolver>, предоставляемых контекстом.  
  
 В службах XAML .NET Framework обработка этого расширения разметки определяется классом <xref:System.Windows.Markup.TypeExtension>.  
  
 В конкретных реализациях платформы некоторые свойства, принимающие <xref:System.Type> в качестве значения, способны принять имя типа напрямую \(строковое значение типа `Name`\).  Тем не менее реализация такого поведения является сложным сценарием.  Примеры см. ниже в подразделе "Примечания об использовании WPF".  
  
 Синтаксис атрибута является наиболее распространенным синтаксисом, который используется с этим расширением разметки.  маркер строки, указанный после идентификатора строки `x:Type`, получает значение <xref:System.Windows.Markup.TypeExtension.TypeName%2A> базового класса расширения <xref:System.Windows.Markup.TypeExtension>.  В контексте схемы XAML по умолчанию для служб XAML .NET Framework, которая основана на типах среды CLR, значение этого атрибута равно <xref:System.Reflection.MemberInfo.Name%2A> требуемого типа или содержит <xref:System.Reflection.MemberInfo.Name%2A>, которому предшествует префикс для сопоставления пространства имен XAML не по умолчанию.  
  
 Расширение разметки `x:Type` можно использовать в синтаксисе элементов объекта.  В этом случае для правильной инициализации расширения требуется указать значение свойства <xref:System.Windows.Markup.TypeExtension.TypeName%2A>.  
  
 Расширение разметки `x:Type` может также использоваться как подробный атрибут; однако такое использование не является типичным: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`  
  
## Примечания об использовании WPF  
  
### Сопоставление типов и пространства имен XAML по умолчанию  
 Пространства имен XAML по умолчанию для программирования WPF содержит большинство типов XAML, необходимых для типичных сценариев XAML, поэтому часто можно не указывать префиксы при ссылке на значения типов XAML.  Сопоставление префикса может потребоваться при ссылке на тип из пользовательской сборки, а также для типов, существующих в сборке WPF, но происходящих из пространства имен CLR, которое не было сопоставлено как пространство имен XAML по умолчанию.  Дополнительные сведения о префиксах, пространствах имен XAML и сопоставлении пространств имен среды CLR см. в разделе [Пространства имен XAML и сопоставление пространств имен для WPF XAML](../../../ocs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### Свойства типов, поддерживающие имя типа в виде строки  
 WPF поддерживает методы, позволяющие указывать значения некоторых свойств типа <xref:System.Type> без необходимости использования расширения разметки `x:Type`.  Вместо этого можно указать значение в виде строки с именем типа.  К подобным примерам относятся <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=fullName> и <xref:System.Windows.Style.TargetType%2A?displayProperty=fullName>.  Поддержка этого поведения не обеспечивается через преобразователи типов или расширения разметки.  Вместо этого это поведение откладывания реализуется через <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight поддерживает аналогичную конвенцию  Фактически Silverlight в настоящее время не поддерживает `{x:Type}` в поддержке языка XAML и не принимает вхождения `{x:Type}` за исключением некоторых случаев, которые предусмотрены для поддержки миграции XAML между WPF и Silverlight.  Следовательно, поведение "имя типа в виде строки" присуще всем оценкам внутренних свойств Silverlight, где значением является <xref:System.Type>.  
  
## XAML 2009  
 XAML 2009 обеспечивает дополнительную поддержку универсальных типов и изменяет поведение `x:TypeArguments` и `x:Type` для предоставления этой поддержки.  
  
-   `x:TypeArguments` и элемент связанного объекта для создания экземпляра универсального объекта могут быть в элементах, отличных от корневого.  Дополнительные сведения см. в подразделе "XAML 2009" раздела [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
-   XAML 2009 поддерживает синтаксис для указания ограничения универсального типа в разметке.  Это может использоваться `x:TypeArguments`, `x:Type` или двумя компонентами в сочетании.  
  
-   Реализация WPF XAML при обработке XAML 2009 для загрузки также добавляет эту возможность при неявном преобразовании типов для определенных свойств платформы, которые используют тип <xref:System.Type>.  
  
 В WPF можно использовать возможности XAML 2009, но только для свободного XAML \(XAML без компилированной разметки\).  XAML с компилированной разметкой для WPF и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и возможности XAML 2009.  
  
## См. также  
 <xref:System.Windows.Style>   
 [Стилизация и использование шаблонов](../../../ocs/framework/wpf/controls/styling-and-templating.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Расширения разметки и XAML WPF](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)