---
title: "x:Null Markup Extension | Microsoft Docs"
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
  - "NullExtension"
  - "x:NullExtension"
  - "x:Null"
  - "Null"
  - "xNull"
helpviewer_keywords: 
  - "Null markup extension in XAML [XAML Services]"
  - "x:Null markup extension [XAML Services]"
  - "XAML [XAML Services], x:Null markup extension"
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
caps.latest.revision: 20
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 20
---
# x:Null Markup Extension
Задает `null` в качестве значения для свойства XAML.  
  
## Использование атрибута XAML  
  
```  
<object property="{x:Null}" .../>  
```  
  
## Заметки  
 NULL является ключевым словом для пустой ссылки в [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] и [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)].  Ключевое слово [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] для пустой ссылки — `Nothing`, но следует всегда использовать `{x:Null}` в XAML, независимо от того, какой язык кода связан с XAML.  
  
 Расширение разметки `x:Null` имеет неустанавливаемые свойства.  
  
 Использование null часто связано с предоставлением элементов XAML значения <xref:System.Nullable%601> среды CLR.  
  
 Расширение разметки `x:Null`, как и все расширения разметки XAML, использует скобки \(`{,}`\) для преобразования обработки значений атрибутов в значения, отличающиеся от литералов или ссылок обработчиков событий.  Синтаксис атрибута — это синтаксис, наиболее часто используемый с этим расширением разметки.  Синтаксис элемента объекта `<x:Null />` технически возможен, но редко используется, так как расширение разметки `x:Null` не имеет позиционных параметров или аргументов создания.  
  
 Сведения о расширениях разметки см. в разделе [Расширения разметки и XAML WPF](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 В службах XAML .NET Framework обработка этого расширения разметки определяется классом <xref:System.Windows.Markup.NullExtension>.  
  
## Примечания об использовании WPF  
 Обратите внимание, что `null` не обязательно устанавливать в качестве начального значения для свойства зависимостей ссылочного типа.  Начальное значение по умолчанию могут различаться для каждого свойства зависимости и может быть основано на метаданных, относящихся к свойству.  Многие свойства зависимости не принимают `null` в качестве значения, через разметку, или код, из\-за их проверки реализаций обратного вызова.  Дополнительные сведения о свойствах зависимостей см. в разделе [Общие сведения о свойствах зависимости](../../../ocs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## См. также  
 <xref:System.Windows.DependencyProperty.UnsetValue>   
 [Общие сведения о языке XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Расширения разметки и XAML WPF](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)