---
title: "x:TypeArguments Directive | Microsoft Docs"
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
  - "x:TypeArguments"
  - "xTypeArguments"
  - "TypeArguments"
helpviewer_keywords: 
  - "x:TypeArguments attribute [XAML Services]"
  - "TypeArguments attribute in XAML [XAML Services]"
  - "XAML [XAML Services], x:TypeArguments attribute"
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
caps.latest.revision: 18
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 18
---
# x:TypeArguments Directive
Передает аргументы типов ограничений универсального шаблона в конструктор универсального типа.  
  
## Использование атрибута XAML  
  
```  
<object x:TypeArguments="typeString" .../>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`object`|Объявление элемента объекта типа XAML, который реализуется универсальным типом среды CLR.  Если `object` относится к типу XAML не из пространства имен XAML, для `object` требуется префикс, чтобы указать пространство имен XAML, где `object` существует.|  
|`typeString`|Строка, объявляющая одно или несколько имен типов XAML в виде строк, предоставляя аргументы типа для универсального типа среды CLR.  Дополнительные заметки по синтаксису см. в разделе "Примечания".|  
  
## Заметки  
 Как правило, типы XAML, используемые в качестве элемента сведений в строке `typeString`, сопровождаются префиксом.  Типичные типы универсальных ограничений среды CLR \(например, <xref:System.Int32> и <xref:System.String>\) берутся из библиотек базовых классов среды CLR.  Эти библиотеки не сопоставляются с типичными, связанными с конкретной платформой, пространствами имен XAML по умолчанию и поэтому требуют сопоставления префиксов для использования XAML.  
  
 Используя разделитель в виде запятой, можно указать более одного имени типа XAML.  
  
 Если универсальные ограничения сами используют универсальные типы, аргументы типа вложенного ограничения могут заключаться в скобки \(\).  
  
 Обратите внимание, что это определение `x:TypeArguments` связано только со службами XAML .NET Framework и использует резервную среду CLR.  Определение уровня языка см. в [\[MS\-XAML\] Раздел 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## Примеры использования  
 В этих примерах предполагается, что объявлены следующие определения пространств имен XAML:  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### List\<String\>  
 `<scg:List x:TypeArguments="sys:String" ...>` создает новый <xref:System.Collections.Generic.List%601> с аргументом типа <xref:System.String>.  
  
### Dictionary\<String,String\>  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` создает новый <xref:System.Collections.Generic.Dictionary%602> с двумя аргументами типа <xref:System.String>.  
  
### Queue\<KeyValuePair\<String,String\>\>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` создает новый объект <xref:System.Collections.Generic.Queue%601>, который имеет ограничение <xref:System.Collections.Generic.KeyValuePair%602> с аргументами типа внутреннего ограничения <xref:System.String> и <xref:System.String>.  
  
## Универсальное использование XAML в XAML 2006 и WPF  
 Для использования XAML 2006 г. и XAML, используемого для приложений WPF, действуют следующие ограничения на `x:TypeArguments` и использование универсальных типов из XAML в целом:  
  
-   Только корневой элемент файла XAML может поддерживать универсальное использование XAML, ссылающееся на универсальный тип.  
  
-   Корневой элемент должен сопоставляться с универсальным типом хотя бы одним аргументом типа.  Например, <xref:System.Windows.Navigation.PageFunction%601>.  Функции страницы являются основным сценарием для поддержки универсального использования XAML в WPF.  
  
-   Элемент объекта корневого элемента XAML для универсального типа также должен объявить разделяемый класс с помощью `x:Class`.  Это верно даже при определении действия построения WPF.  
  
-   `x:TypeArguments` не может ссылаться на вложенные универсальные ограничения.  
  
## XAML 2009 или XAML 2006 без зависимости от WPF 3.0 или WPF 3.5  
 В службах XAML .NET Framework для XAML 2006 и XAML 2009 снимаются связанные с WPF ограничения на универсальное использование XAML.  Можно создать экземпляр универсального объектного элемента в любом месте разметки XAML, которая поддерживаются системой резервных типов и объектной моделью.  
  
 Если для получения типов XAML для общих примитивов языка вместо сопоставления базовых типов CLR используется XAML 2009, можно использовать [Встроенные типы для общих примитивов языка XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) в качестве элементов сведений в `typeString`.  Например, можно объявить следующее \(сопоставление типов не показано, но x является пространством имен XAML языка XAML для XAML 2009\):  
  
```  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 В WPF и при использовании в качестве целевой платформы [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] можно использовать возможности XAML 2009 вместе с `x:TypeArguments`, но только для свободного XAML \(XAML, не компилированного разметкой\).  XAML с компилированной разметкой для WPF и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и возможности XAML 2009.  При необходимости компиляции разметки XAML нужно следовать ограничениям, указанным в разделе "Использование XAML 2006 и универсального XAML WPF".  
  
## См. также  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [x:Type Markup Extension](../../../docs/framework/xaml-services/x-type-markup-extension.md)   
 [Встроенные типы для общих примитивов языка XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)   
 [Generics in XAML](../../../docs/framework/xaml-services/generics-in-xaml.md)