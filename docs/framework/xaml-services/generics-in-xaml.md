---
title: "Generics in XAML | Microsoft Docs"
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
  - "generics [XAML Services]"
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# Generics in XAML
Службы XAML платформы .NET Framework, реализованные в System.Xaml, обеспечивают поддержку использования универсальных типов среды CLR.  В эту поддержку входят указание ограничений универсальных типов в качестве аргумента типа и обеспечение соблюдения ограничений путем вызова соответствующего метода `Add` для универсальных коллекций.  В этом разделе описываются различные аспекты использования универсальных типов в XAML и создания ссылок на них.  
  
## Атрибут x:TypeArguments  
 `x:TypeArguments` является директивой, определенной языком XAML.  При использовании в качестве члена типа XAML, зарезервированного универсальным типом, `x:TypeArguments` передает ограничительные аргументы универсального типа резервному конструктору.  Сведения о синтаксисе, относящемся к использованию службами XAML платформы .NET Framework атрибута `x:TypeArguments`, включая примеры синтаксиса, см. в разделе [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
 Поскольку атрибут `x:TypeArguments` принимает строку и обладает резервированием преобразователя типов, обычно он объявляется в употреблении XAML в качестве атрибута.  
  
 В потоке узлов XAML сведения, объявленные атрибутом `x:TypeArguments`, могут быть получены из свойства <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=fullName> на позиции `StartObject` в потоке узлов.  Возвращаемое значение свойства <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=fullName> представляет собой перечень значений <xref:System.Xaml.XamlType>.  Определить, представляет ли тип XAML универсальный тип, можно путем вызова <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=fullName>.  
  
## Соглашения и правила и синтаксиса для универсальных типов в XAML  
 В XAML универсальный тип всегда должен быть представлен как универсальный тип с ограничениями; универсальный тип без ограничений никогда не представлен в системе типов XAML или потоке узлов XAML и не может быть представлен в разметке XAML.  На универсальный тип может быть сделана ссылка в пределах синтаксиса атрибутов XAML в тех случаях, где на ограничение вложенного типа универсального типа ссылается директива `x:TypeArguments`, а также в случаях, где расширение разметки `x:Type` предоставляет ссылку на тип CLR для универсального типа.  Это поддерживается при помощи класса <xref:System.Xaml.Schema.XamlTypeTypeConverter>, определенного службами XAML платформы .NET Framework.  
  
 Форма синтаксиса атрибутов XAML, включенная классом <xref:System.Xaml.Schema.XamlTypeTypeConverter>, изменяет типовое соглашение синтаксиса MSIL \/ CLR, которое использует угловые скобки для типов и ограничений универсальных типов, а вместо этого заменяет круглые скобки контейнером ограничения.  Пример см. в разделе [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
## Универсальные типы и возможности XAML 2009  
 При использовании XAML 2009 вместо сопоставления базовых типов CLR для получения типов XAML для общих языковых примитивов можно использовать [Встроенные типы XAML 2009](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) в качестве информационных элементов в `x:TypeArguments`.  Например, можно объявить следующее \(сопоставления префиксов не показаны, но `x` является пространством имен XAML языка XAML для XAML 2009\):  
  
```  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## Поддержка универсальных типов в WPF и других платформах версии 3.5  
 Для использования XAML 2006 при нацеливании конкретно на WPF необходимо также предоставлять директиву [x:Class](../../../docs/framework/xaml-services/x-class-directive.md) на том же элементе, что и директиву `x:TypeArguments`, причем этот элемент должен быть корневым элементом в документе XAML.  Корневой элемент должен сопоставляться с универсальным типом хотя бы одним аргументом типа.  Например, <xref:System.Windows.Navigation.PageFunction%601>.  
  
 К возможным способам поддержки использований универсальных типов относятся определение пользовательского расширения разметки, которое может возвращать универсальные типы, а также предоставление определения класса оболочки, которое является производным от универсального типа, но смягчает универсальное ограничение в своем собственном определении класса.  
  
 В WPF и при нацеливании на [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] можно использовать возможности XAML 2009 вместе с директивой `x:TypeArguments`, но только для свободного XAML \(кода XAML, не являющегося компилированной разметкой\).  XAML с компилированной разметкой для WPF и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и возможности XAML 2009.  
  
 Пользовательские рабочие процессы в [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] для [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] не поддерживают универсальное использование XAML.  
  
## См. также  
 [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md)   
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [Built\-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)